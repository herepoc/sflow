# Schema do Banco de Dados (PostgreSQL)

Este documento detalha a estrutura do banco de dados relacional projetado para a solução de análise de chamadas.

---

### Tabela: `recording_batch`

Representa um lote de upload, que pode conter um ou mais arquivos de áudio.

| Coluna             | Tipo          | Chave           | Descrição                                                                     |
| :----------------- | :------------ | :-------------- | :---------------------------------------------------------------------------- |
| `id`               | `SERIAL`      | PK              | Identificador único do lote.                                                  |
| `upload_timestamp` | `TIMESTAMPTZ` |                 | Data e hora do upload.                                                        |
| `status`           | `VARCHAR(20)` |                 | Status do processamento do lote (`pending`, `processing`, `completed`, `error`). |
| `uploaded_by_id`   | `INTEGER`     | FK (`user.id`)  | ID do usuário que realizou o upload.                                          |

---

### Tabela: `record`

Armazena os metadados de uma única gravação de áudio, junto com sua transcrição.

| Coluna                | Tipo           | Chave                      | Descrição                                                                                   |
| :-------------------- | :------------- | :------------------------- | :------------------------------------------------------------------------------------------ |
| `id`                  | `SERIAL`       | PK                         | Identificador único da gravação.                                                            |
| `recording_batch_id`  | `INTEGER`      | FK (`recording_batch.id`)  | ID do lote ao qual a gravação pertence.                                                     |
| `original_filename`   | `VARCHAR(255)` |                            | Nome original do arquivo de áudio.                                                          |
| `file_path`           | `VARCHAR(512)` |                            | Caminho do arquivo de áudio no sistema de arquivos.                                         |
| `duration_seconds`    | `INTEGER`      |                            | Duração do áudio em segundos.                                                               |
| `status`              | `VARCHAR(20)`  |                            | Status do processamento (`pending`, `transcribing`, `analyzing`, `completed`, `error`).     |
| `error_message`       | `TEXT`         |                            | Mensagem de erro, caso o processamento falhe.                                               |
| `raw_diarized_json`   | `JSONB`        |                            | Resultado bruto da transcrição e diarização, com timestamps e identificação de falantes.    |
| `full_text_content`   | `TEXT`         |                            | Conteúdo completo da transcrição em texto puro, para buscas.                                |

**Índice Sugerido:**
*   Índice de Full-Text Search na coluna `full_text_content` para otimizar as pesquisas.

---

### Tabela: `analysis`

Armazena o resultado de uma execução do motor de análise sobre uma gravação. Uma gravação pode ter múltiplas análises.

| Coluna               | Tipo          | Chave           | Descrição                                                                                     |
| :------------------- | :------------ | :-------------- | :-------------------------------------------------------------------------------------------- |
| `id`                 | `SERIAL`      | PK              | Identificador único da análise.                                                               |
| `record_id`          | `INTEGER`     | FK (`record.id`) | ID da gravação que foi analisada.                                                             |
| `analysis_timestamp` | `TIMESTAMPTZ`   |                 | Data e hora em que a análise foi executada.                                                   |
| `analysis_data`      | `JSONB`       |                 | Campo flexível contendo todos os dados da análise (sentimento, motivo, palavras-chave, etc.). |

**Exemplo de `analysis_data`:**
```json
{
  "sentiment": "negative",
  "sentiment_score": 0.98,
  "call_reason": "Dúvida de Fatura",
  "matched_keywords": [
    {"term": "atraso", "list": "Problemas"},
    {"term": "juros", "list": "Problemas"}
  ]
}
```

---

### Tabela: `call_reason`

Tabela de configuração para os possíveis motivos das chamadas.

| Coluna        | Tipo          | Chave    | Descrição                                         |
| :------------ | :------------ | :------- | :------------------------------------------------ |
| `id`          | `SERIAL`      | PK       | Identificador único do motivo.                    |
| `name`        | `VARCHAR(100)`| UNIQUE   | Nome do motivo (ex: "Suporte Técnico").         |
| `description` | `TEXT`        |          | Descrição opcional do motivo.                     |
| `is_active`   | `BOOLEAN`     |          | Indica se o motivo está ativo para classificação. |

---

### Tabela: `keyword_list`

Agrupa um conjunto de palavras-chave a serem monitoradas.

| Coluna      | Tipo          | Chave  | Descrição                                  |
| :---------- | :------------ | :----- | :----------------------------------------- |
| `id`        | `SERIAL`      | PK     | Identificador único da lista.              |
| `name`      | `VARCHAR(100)`| UNIQUE | Nome da lista (ex: "Concorrentes").        |
| `is_active` | `BOOLEAN`     |        | Indica se a lista está ativa para monitoramento. |

---

### Tabela: `keyword`

Armazena uma única palavra-chave ou expressão pertencente a uma `keyword_list`.

| Coluna          | Tipo           | Chave                  | Descrição                                  |
| :-------------- | :------------- | :--------------------- | :----------------------------------------- |
| `id`            | `SERIAL`       | PK                     | Identificador único do termo.              |
| `keyword_list_id` | `INTEGER`      | FK (`keyword_list.id`) | ID da lista à qual o termo pertence.       |
| `term`          | `VARCHAR(100)` |                        | A palavra-chave ou expressão a ser monitorada. |

**Índice Sugerido:**
*   Índice composto em `(keyword_list_id, term)` para garantir unicidade e otimizar buscas.

---

*Este schema não inclui as tabelas padrão do Django (`auth_user`, `auth_group`, etc.), que serão criadas automaticamente pelo framework.*
