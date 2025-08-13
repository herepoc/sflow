# Macro Flow - Processo de Desenvolvimento de Apps Fullstack com Agentes Especialistas

## Visão Geral

Processo estruturado para desenvolvimento de aplicações fullstack web, utilizando agentes especialistas para guiar questionamentos estratégicos em cada etapa. O processo é baseado em validação contínua com o cliente e aprovação consensual antes de avançar entre etapas.

## Metodologia

- **Input Inicial**: Conversa gravada entre consultor e cliente
- **Validação**: Consenso e aprovação do cliente para avançar etapas
- **Especialização**: Um agente especialista por etapa
- **Iteração**: Loops de refinamento em pontos críticos

---

## Etapa de Planejamento

### 1. Descoberta da Ideia
**Agente Especialista**: Discovery Agent
- **Input**: Conversa gravada inicial (cliente + consultor)
- **Objetivos**: Capturar intenção, contexto e expectativas
- **Questionamentos do Agente**:
  - **Validação**: "A ideia está clara e bem definida?"
  - **Coleta**: "Quais são os principais problemas que o sistema deve resolver?"
  - **Desafio**: "Existem soluções similares no mercado? Como se diferenciará?"
- **Deliverables**: Documento de intenção validado
- **Critério de Passagem**: Cliente aprova o entendimento da ideia

### 2. Protótipo Conceitual
**Agente Especialista**: UX Strategy Agent
- **Input**: Documento de intenção + nova conversa (se necessário)
- **Objetivos**: Visualizar conceito através de protótipo/wireframes
- **Questionamentos do Agente**:
  - **Validação**: "O protótipo representa fielmente a ideia?"
  - **Coleta**: "Quais fluxos de usuário são mais críticos?"
  - **Desafio**: "Este design atende aos diferentes tipos de usuários?"
- **Deliverables**: Protótipo conceitual/wireframes
- **Critério de Passagem**: Cliente valida que o protótipo ilustra sua visão

### 3. Detalhamento de Intenções
**Agente Especialista**: Requirements Agent
- **Input**: Protótipo aprovado + feedback do cliente
- **Objetivos**: Criar requisitos funcionais e não funcionais
- **Questionamentos do Agente**:
  - **Validação**: "Os requisitos cobrem todas as funcionalidades do protótipo?"
  - **Coleta**: "Quais regras de negócio específicas devem ser consideradas?"
  - **Desafio**: "Existe algum requisito conflitante ou ambíguo?"
- **Deliverables**: Documento de requisitos funcionais
- **Critério de Passagem**: Cliente confirma completude dos requisitos
- **Loop**: Pode retornar à Etapa 1 se surgirem inconsistências

### 4. Definição de Requisitos Não Funcionais
**Agente Especialista**: Quality Assurance Agent
- **Input**: Requisitos funcionais validados
- **Objetivos**: Definir performance, segurança, escalabilidade
- **Questionamentos do Agente**:
  - **Validação**: "Os requisitos não funcionais são mensuráveis?"
  - **Coleta**: "Quantos usuários simultâneos o sistema deve suportar?"
  - **Desafio**: "Existe trade-off entre performance e funcionalidade?"
- **Deliverables**: Documento de requisitos não funcionais
- **Critério de Passagem**: Cliente aprova critérios de qualidade

### 5. Definição da Arquitetura
**Agente Especialista**: Solution Architecture Agent
- **Input**: Requisitos funcionais e não funcionais
- **Objetivos**: Desenhar arquitetura técnica da solução
- **Questionamentos do Agente**:
  - **Validação**: "A arquitetura atende todos os requisitos?"
  - **Coleta**: "Existem integrações com sistemas externos?"
  - **Desafio**: "Esta arquitetura é escalável e maintível?"
- **Deliverables**: Diagrama de arquitetura + documentação
- **Critério de Passagem**: Aprovação técnica e de negócio

### 6. Definição do Stack Tecnológico
**Agente Especialista**: Tech Stack Agent
- **Input**: Arquitetura definida
- **Objetivos**: Selecionar tecnologias, frameworks e ferramentas
- **Questionamentos do Agente**:
  - **Validação**: "O stack escolhido suporta a arquitetura?"
  - **Coleta**: "Há preferências ou restrições tecnológicas?"
  - **Desafio**: "Este stack tem comunidade ativa e manutenção?"
- **Deliverables**: Documento de stack tecnológico
- **Critério de Passagem**: Cliente aprova escolhas tecnológicas

### 7. Definição de Boas Práticas
**Agente Especialista**: Code Quality Agent
- **Input**: Stack tecnológico definido
- **Objetivos**: Estabelecer padrões de código, testes e deployment
- **Questionamentos do Agente**:
  - **Validação**: "As práticas são adequadas ao stack escolhido?"
  - **Coleta**: "Qual nível de cobertura de testes é esperado?"
  - **Desafio**: "Como garantir qualidade sem impactar velocidade?"
- **Deliverables**: Guia de boas práticas e padrões
- **Critério de Passagem**: Acordo sobre padrões de qualidade

### 8. Criação de Diagramas Adicionais
**Agente Especialista**: Technical Documentation Agent
- **Input**: Arquitetura + stack + boas práticas
- **Objetivos**: Fluxos de dados, infra de alto nível, integrações
- **Questionamentos do Agente**:
  - **Validação**: "Os diagramas são claros e completos?"
  - **Coleta**: "Quais são os fluxos críticos de dados?"
  - **Desafio**: "Existe algum ponto de falha não documentado?"
- **Deliverables**: Conjunto completo de diagramas técnicos
- **Critério de Passagem**: Documentação técnica aprovada

### 9. Histórias Fundacionais
**Agente Especialista**: Product Strategy Agent
- **Input**: Toda documentação técnica
- **Objetivos**: Criar épicos e histórias de alto nível
- **Questionamentos do Agente**:
  - **Validação**: "As histórias cobrem toda a funcionalidade?"
  - **Coleta**: "Qual é a prioridade de cada épico?"
  - **Desafio**: "Existe dependência crítica entre histórias?"
- **Deliverables**: Backlog de épicos e histórias fundacionais
- **Critério de Passagem**: Priorização aprovada pelo cliente

### 10. Histórias Funcionais Detalhadas
**Agente Especialista**: Product Owner Agent
- **Input**: Histórias fundacionais priorizadas
- **Objetivos**: Detalhar histórias com critérios de aceitação
- **Questionamentos do Agente**:
  - **Validação**: "Os critérios de aceitação são claros?"
  - **Coleta**: "Quais são os cenários de teste para cada história?"
  - **Desafio**: "Existe alguma história muito complexa para ser dividida?"
- **Deliverables**: Backlog detalhado com critérios de aceitação
- **Critério de Passagem**: Histórias prontas para desenvolvimento
- **Loop**: Pode retornar à Etapa 4 se estimativas não forem viáveis

### 11. Modelos de Dados
**Agente Especialista**: Data Architecture Agent
- **Input**: Histórias funcionais + requisitos
- **Objetivos**: Desenhar estrutura de dados e relacionamentos
- **Questionamentos do Agente**:
  - **Validação**: "O modelo suporta todas as funcionalidades?"
  - **Coleta**: "Existem dados legados para migração?"
  - **Desafio**: "O modelo é normalizado e performático?"
- **Deliverables**: Diagrama ER + documentação de dados
- **Critério de Passagem**: Modelo de dados aprovado

### 12. Design de Interfaces
**Agente Especialista**: UI/UX Design Agent
- **Input**: Protótipo conceitual + histórias funcionais
- **Objetivos**: Criar designs finais e sistema de design
- **Questionamentos do Agente**:
  - **Validação**: "As interfaces seguem as melhores práticas de UX?"
  - **Coleta**: "Existe alguma preferência visual ou guideline?"
  - **Desafio**: "O design é responsivo e acessível?"
- **Deliverables**: Designs finais + componentes reutilizáveis
- **Critério de Passagem**: Cliente aprova interfaces finais

### 13. Plano de Trabalho
**Agente Especialista**: Project Management Agent
- **Input**: Todos os entregáveis anteriores
- **Objetivos**: Criar cronograma, estimativas e plano de entrega
- **Questionamentos do Agente**:
  - **Validação**: "O plano é realista e executável?"
  - **Coleta**: "Existem restrições de prazo ou orçamento?"
  - **Desafio**: "Como mitigar riscos identificados?"
- **Deliverables**: Cronograma + plano de riscos + estimativas
- **Critério de Passagem**: Plano aprovado para iniciar desenvolvimento
- **Loop**: Pode retornar à Etapa 4 se estimativas não forem viáveis

---

## Etapa de Build

### 14. Preparação do Ambiente
**Agente Especialista**: DevOps Agent
- **Input**: Plano de trabalho aprovado
- **Objetivos**: Setup de repositórios, CI/CD e ambientes
- **Questionamentos do Agente**:
  - **Validação**: "Todos os ambientes estão funcionais?"
  - **Coleta**: "Quais são os requisitos de segurança para deploy?"
  - **Desafio**: "A pipeline suporta rollback automático?"
- **Deliverables**: Ambientes configurados + pipelines ativas
- **Critério de Passagem**: Ambiente pronto para desenvolvimento

### 15. Desenvolvimento Iterativo
**Agente Especialista**: Development Coach Agent
- **Input**: Histórias priorizadas + ambiente preparado
- **Objetivos**: Acompanhar desenvolvimento seguindo boas práticas
- **Questionamentos do Agente**:
  - **Validação**: "O código segue os padrões estabelecidos?"
  - **Coleta**: "Existem bloqueios ou dependências não resolvidas?"
  - **Desafio**: "A cobertura de testes está adequada?"
- **Deliverables**: Software funcionando em iterações
- **Critério de Passagem**: Entrega contínua com qualidade

---

## Diagramas do Processo

### Fluxo Principal das Etapas

```mermaid
flowchart TD
    A[1 Descoberta da Ideia] --> B[2 Protótipo Conceitual]
    B --> C[3 Detalhamento de Intenções]
    C --> D[4 Requisitos Não Funcionais]
    D --> E[5 Arquitetura]
    E --> F[6 Stack Tecnológico]
    F --> G[7 Boas Práticas]
    G --> H[8 Diagramas Adicionais]
    H --> I[9 Histórias Fundacionais]
    I --> J[10 Histórias Funcionais]
    J --> K[11 Modelos de Dados]
    K --> L[12 Design de Interfaces]
    L --> M[13 Plano de Trabalho]
    M --> N[14 Preparação do Ambiente]
    N --> O[15 Desenvolvimento Iterativo]
    
    %% Loops
    C -.->|inconsistências| A
    J -.->|inviabilidade| D
    M -.->|estimativas irreais| D
    
    %% Styling
    classDef planning fill:#e1f5fe
    classDef build fill:#f3e5f5
    
    class A,B,C,D,E,F,G,H,I,J,K,L,M planning
    class N,O build
```

### Interação entre Agentes, Cliente e Consultor

```mermaid
sequenceDiagram
    participant C as Cliente
    participant CO as Consultor
    participant A as Agente Especialista
    participant S as Sistema
    
    Note over C,S: Início de uma Etapa
    
    C->>CO: Conversa inicial/feedback
    CO->>S: Grava conversa
    S->>A: Input da conversa gravada
    
    Note over A: Processamento e Análise
    
    A->>CO: Questionamentos estratégicos
    CO->>C: Apresenta perguntas do agente
    C->>CO: Respostas e esclarecimentos
    CO->>A: Fornece respostas
    
    Note over A: Validação e Síntese
    
    A->>S: Gera deliverable da etapa
    S->>CO: Apresenta resultado
    CO->>C: Valida com cliente
    
    alt Cliente Aprova
        C->>CO: Aprovação
        CO->>S: Avança para próxima etapa
    else Cliente Solicita Ajustes
        C->>CO: Feedback de ajustes
        CO->>A: Nova iteração
    end
```

### Fluxo de Decisão por Etapa

```mermaid
flowchart TD
    START([Início da Etapa]) --> INPUT[Recebe Input]
    INPUT --> AGENT[Agente Processa]
    AGENT --> QUESTIONS[Gera Questionamentos]
    QUESTIONS --> COLLECT[Coleta Respostas]
    COLLECT --> VALIDATE{Informações Suficientes?}
    
    VALIDATE -->|Não| QUESTIONS
    VALIDATE -->|Sim| GENERATE[Gera Deliverable]
    
    GENERATE --> REVIEW[Cliente Revisa]
    REVIEW --> APPROVE{Cliente Aprova?}
    
    APPROVE -->|Não| FEEDBACK[Feedback de Ajustes]
    FEEDBACK --> AGENT
    
    APPROVE -->|Sim| NEXT{Última Etapa?}
    NEXT -->|Não| ADVANCE[Avança Próxima Etapa]
    NEXT -->|Sim| END([Processo Completo])
    
    %% Styling
    classDef decision fill:#fff2cc
    classDef process fill:#d5e8d4
    classDef terminal fill:#f8cecc
    
    class VALIDATE,APPROVE,NEXT decision
    class INPUT,AGENT,QUESTIONS,COLLECT,GENERATE,REVIEW,ADVANCE process
    class START,END,FEEDBACK terminal
```

### Mapa de Loops e Iterações

```mermaid
flowchart LR
    subgraph "Etapa de Planejamento"
        E1[1 Ideia]
        E3[3 Detalhamento]
        E4[4 Req. Não Funcionais]
        E10[10 Histórias Funcionais]
        E13[13 Plano de Trabalho]
        
        E1 -.->|Loop 1: Inconsistências| E3
        E3 -.->|Loop 1: Refinamento| E1
        
        E4 -.->|Loop 2: Inviabilidade| E13
        E13 -.->|Loop 2: Ajuste Requisitos| E4
        
        E10 -.->|Loop 3: Estimativas| E4
    end
    
    subgraph "Etapa de Build"
        E14[14 Prep. Ambiente]
        E15[15 Desenvolvimento]
    end
    
    E13 --> E14
    
    %% Styling
    classDef loop stroke:#ff6b6b,stroke-width:3px,stroke-dasharray: 5 5
    class E1,E3,E4,E10,E13 loop
```

---

## Benefícios do Processo

- **Qualidade**: Questionamentos especializados em cada etapa
- **Validação**: Cliente sempre no centro das decisões
- **Rastreabilidade**: Histórico completo de decisões e aprovações
- **Flexibilidade**: Loops permitem refinamento quando necessário
- **Especialização**: Cada agente focado em sua área de expertise

---

## Observações de Implementação

- **Conversas Gravadas**: Sempre que necessário para coletar mais contexto
- **Documentação**: Cada etapa gera artifacts específicos
- **Aprovação**: Cliente deve aprovar explicitamente cada etapa
- **Iteração**: Loops só ocorrem quando há inconsistências detectadas pelos agentes
