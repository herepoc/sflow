# Diagrama da Arquitetura da Solução

Este documento contém o diagrama da arquitetura da solução, mostrando o fluxo de dados e a interação entre os componentes. O diagrama foi criado usando a sintaxe Mermaid.

---

```mermaid
graph TD
    subgraph "Máquina Única (On-Premises)"
        subgraph "Aplicação Django"
            A[Django Admin UI] --> B{Servidor Django};
        end

        subgraph "Fila de Processamento"
            C[Redis];
        end

        subgraph "Processamento (Celery Worker)"
            D[Worker]
            subgraph "Pipeline de IA (GPU)"
                E[WhisperX]:::ia;
                H[Transformers]:::ia;
            end
        end

        subgraph "Armazenamento"
            F[Diretório Local];
            G[Banco de Dados PostgreSQL];
        end
    end

    %% Fluxo de Interação
    U[Usuário] -- Acessa --> A;
    B -- 1 Upload --> F[Áudio Salvo];
    B -- 2 Cria Tarefa de Transcrição --> C;
    
    D -- 3 Pega Tarefa de Transcrição --> C;
    D -- 4 Executa WhisperX --> E;
    E -- 5 Salva Transcrição Bruta --> G;
    E -- 6 Cria Tarefa de Análise --> C;

    D -- 7 Pega Tarefa de Análise --> C;
    D -- 8 Lê Transcrição Bruta --> G;
    D -- 9 Executa Transformers --> H;
    H -- 10 Salva Análise Final --> G;

    A -- 11 Exibe Dashboard --> G;

    %% Estilização
    classDef django fill:#092E20,stroke:#2BA977,stroke-width:2px,color:#fff;
    classDef celery fill:#3E0075,stroke:#BF5FFF,stroke-width:2px,color:#fff;
    classDef data fill:#4A1E1E,stroke:#FF5A5A,stroke-width:2px,color:#fff;
    classDef ia fill:#003366,stroke:#0066CC,stroke-width:2px,color:#fff;

    class A,B django;
    class D celery;
    class C,F,G data;
    class E,H ia;
```
