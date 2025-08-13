# Requisitos Não-Funcionais

Este documento detalha os requisitos não-funcionais da solução de análise de chamadas, servindo como guia para decisões de arquitetura e tecnologia.

---

### **1. Performance e Escalabilidade**
*   **RFN-01 (Volume de Processamento):** Suportar o processamento de aproximadamente **1.000 chamadas/dia**.
*   **RFN-02 (Modo de Processamento):** Operar em modo **batch (lote)**, sem necessidade de análise em tempo real. O início do processo será manual.
*   **RFN-03 (Tempo de Resposta do Dashboard):** As buscas e filtros no dashboard devem responder em no máximo **3 segundos**.

### **2. Confiabilidade e Resiliência**
*   **RFN-04 (Tratamento de Falhas):** Falhas no processamento de um áudio devem isolar o arquivo problemático e **não interromper** o restante do lote.
*   **RFN-05 (Retomada de Processamento):** O sistema deve ser capaz de **retomar um lote interrompido** do ponto onde parou, sem reprocessar arquivos já concluídos.

### **3. Armazenamento e Ciclo de Vida dos Dados**
*   **RFN-06 (Retenção de Áudio):** Arquivos de áudio originais serão **retidos por 1 semana** e depois descartados.
*   **RFN-07 (Retenção de Dados Analíticos):** As transcrições e os dados gerados pela análise serão mantidos para consulta histórica.

### **4. Segurança e Acesso**
*   **RFN-08 (Autenticação):** O acesso à plataforma será controlado por um sistema de **autenticação simples** (usuário/senha).
*   **RFN-09 (Autorização):** **Não haverá distinção de perfis de acesso**. Todos os usuários terão as mesmas permissões.

### **5. Usabilidade**
*   **RFN-10 (Atualização do Dashboard):** Os dados do dashboard serão **atualizados sob demanda**, quando a página for carregada pelo usuário.

### **6. Observabilidade**
*   **RFN-11 (Painel de Acompanhamento):** O sistema deve possuir um painel para **acompanhar o status** dos lotes de áudio enviados (ex: em fila, processando, concluído, erro).
*   **RFN-12 (Métricas de Processamento):** O painel deve exibir métricas como total de arquivos, percentual de conclusão e tempo estimado para o término do lote.
*   **RFN-13 (Log de Erros):** O sistema deve registrar e permitir a consulta de **logs de erros** para os arquivos que falharam durante o processamento.
