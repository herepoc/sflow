# Arquitetura da Solução: Lista de Componentes

Este documento descreve os componentes de software que formarão a solução de análise de chamadas, com base nas decisões tomadas. A arquitetura foi projetada para ser executada em uma única máquina (on-premises) equipada com GPU.

---

### **1. Aplicação Web (Backend e Frontend)**
*   **Tecnologia:** **Django (Python)**
*   **Descrição:** O núcleo da solução. Será responsável por:
    *   Fornecer a interface de usuário através do **Django Admin**, que será customizado para incluir a tela de upload de arquivos, o dashboard de resultados e a visualização de transcrições.
    *   Gerenciar a autenticação de usuários.
    *   Receber os arquivos de áudio e iniciar as tarefas de processamento.
    *   Servir os dados analíticos para o dashboard.

### **2. Motor de Processamento Assíncrono**
*   **Tecnologia:** **Celery**
*   **Descrição:** Framework que orquestrará um pipeline de tarefas assíncronas, dividido em duas etapas para permitir o reprocessamento:
    1.  **Tarefa de Transcrição:** Executa o WhisperX e salva a transcrição bruta no banco de dados.
    2.  **Tarefa de Análise:** Executa os modelos da biblioteca Transformers sobre o texto já transcrito.

### **3. Fila de Mensagens (Message Broker)**
*   **Tecnologia:** **Redis**
*   **Descrição:** Atuará como intermediário (broker) para o Celery. O Django enviará uma mensagem para o Redis quando um novo áudio precisar ser processado, e o worker do Celery consumirá essa mensagem para iniciar a tarefa.

### **4. Motor de IA (Processamento de Áudio e Texto)**
*   **Descrição:** O coração analítico do sistema, executado pelo worker do Celery em um pipeline. Utilizará a GPU para máxima performance.
*   **Componentes:**
    *   **Processamento de Áudio (WhisperX):** Para a transcrição do áudio e diarização (identificação de oradores).
    *   **Análise de Texto (Biblioteca Transformers):** Após a transcrição, um modelo de linguagem realizará a análise de sentimento e a classificação do motivo da chamada (via "zero-shot classification").

### **5. Banco de Dados**
*   **Tecnologia:** **PostgreSQL**
*   **Descrição:** Sistema de gerenciamento de banco de dados relacional que irá armazenar:
    *   Os dados da aplicação Django (usuários, logs, etc.).
    *   A **transcrição bruta diarizada** (formato JSON), para fins de reprocessamento.
    *   Os dados analíticos finais (sentimento, motivo da chamada, etc.).
    *   Será configurado com **índices de Full-Text Search** para otimizar as buscas no dashboard.

### **6. Ambiente de Execução**
*   **Plataforma:** **Máquina Única (On-Premises)**
*   **Descrição:** Todos os componentes acima (Django, Redis, PostgreSQL, Celery Worker) serão executados na mesma máquina, simplificando a comunicação entre eles e o acesso aos arquivos, além de atender aos requisitos de segurança.
