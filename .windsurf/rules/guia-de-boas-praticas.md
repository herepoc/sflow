---
trigger: always_on
---

### **Guia de Boas Práticas e Padrões de Desenvolvimento**

Este documento servirá como a nossa "constituição" para o desenvolvimento do projeto, garantindo consistência, qualidade e manutenibilidade.

#### **1. Princípios Fundamentais de Código**

*   **KISS (Keep It Simple, Stupid):** Prefira sempre a solução mais simples e legível. Evite complexidade e abstrações desnecessárias.
*   **DRY (Don't Repeat Yourself):** Reutilize lógica de negócio através de funções, classes de serviço ou helpers. Nunca copie e cole código.
*   **YAGNI (You Ain't Gonna Need It):** Implemente apenas o que é estritamente necessário para a funcionalidade atual. Não adicione código "pensando no futuro".

#### **2. Estrutura e Organização do Projeto (Django)**

*   **Organização por Módulos:** O projeto será dividido em `apps` do Django agrupadas por responsabilidade funcional. Ex:
    *   `core`: Configurações base, usuários, etc.
    *   `ingestion`: Lógica de upload e gerenciamento de arquivos.
    *   `analysis`: Orquestração das tarefas de IA e armazenamento dos resultados.
    *   `dashboard`: Views e lógica para a interface de visualização.
*   **Services Layer:** Lógicas de negócio complexas ou que orquestram múltiplas ações (ex: iniciar um pipeline de análise) devem ser encapsuladas em uma camada de serviço (um arquivo `services.py` dentro da app correspondente). Isso mantém os `views` e `models` limpos.
*   **Fat Models, Thin Views:** A lógica de negócio e as regras de domínio devem estar nos `models` ou na camada de serviço. As `views` devem ser "magras", responsáveis apenas por receber a requisição, chamar os serviços/models e retornar a resposta.

#### **3. Qualidade e Estilo de Código (Python)**

*   **Ferramentas:**
    *   **Formatação:** `Black` será usado para formatação automática do código.
    *   **Linting:** `Ruff` será usado para identificar erros, bugs e problemas de estilo.
    *   **Automação:** As checagens serão automatizadas via `pre-commit hooks`.
*   **Nomenclatura:** Seguir o padrão **PEP 8**. Nomes de variáveis e funções devem ser explícitos e em `snake_case` (ex: `process_audio_file`). Nomes de classes em `CamelCase` (ex: `AudioProcessingService`).
*   **Type Hinting:** Todas as funções e métodos devem ter `type hints` para aumentar a clareza e permitir a verificação estática de tipos.
*   **Docstrings:** Todos os módulos, classes e funções públicas devem ter `docstrings` explicando seu propósito, parâmetros (`Args`) e o que retornam (`Returns`).

#### **4. Padrões Específicos**

*   **Tarefas Assíncronas (Celery):**
    *   **Idempotência:** As tarefas devem ser desenhadas para serem idempotentes. Se uma tarefa for executada múltiplas vezes com os mesmos argumentos, o resultado final deve ser o mesmo.
    *   **Atomicidade:** Cada tarefa deve ter uma única responsabilidade (ex: `transcrever_audio`, `analisar_sentimento`).
    *   **Tratamento de Falhas:** Usar o sistema de `retry` do Celery para falhas temporárias. Para falhas definitivas, a tarefa deve capturar a exceção, registrar um log detalhado do erro associado ao dado de origem (ex: ID do áudio) e finalizar de forma limpa, sem quebrar o worker.
*   **Gerenciamento de Dependências:**
    *   Usaremos `uv` com um arquivo `requirements.txt` para gerenciar as dependências do projeto.
*   **Configurações e Segredos:**
    *   Dados sensíveis (senhas, chaves de API) e configurações de ambiente devem ser gerenciados via **variáveis de ambiente**, com um arquivo `.env` para desenvolvimento local.

#### **5. Testes e Commits**

*   **Estratégia de Testes:** Foco em **testes de unidade** para a lógica de negócio (em `services` e `models`) e **testes de integração** para validar o fluxo completo do pipeline. A meta de cobertura é de **80%**.
*   **Padrão de Commits:** Adotar o padrão **Conventional Commits** para um histórico de versionamento claro e semântico.
    *   Exemplos: `feat(analysis): Adiciona modelo de análise de sentimento`
    *   `fix(ingestion): Corrige erro de upload de arquivos .zip`
    *   `docs(readme): Atualiza instruções de setup`
