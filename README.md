# sFlow — Framework de Trabalho Orientado por Prompts

## Visão Geral
sFlow é um framework de trabalho orientado por prompts para conceber, especificar e planejar sistemas de software. Ele organiza a colaboração entre consultores, clientes e agentes de IA por meio de workflows estruturados, do entendimento do problema até a arquitetura e planejamento de entrega.

**Contexto de Uso:**
- **Público-alvo**: Consultores que conduzem projetos de software para clientes diversos
- **Duração típica**: Projetos de curtos e de média duração (4 meses)
- **Tipos de projeto**: Web apps, mobile, sistemas enterprise, plataformas digitais
- **Modelo de trabalho**: Consultor atua como facilitador entre IA e cliente

**Status**: Em elaboração (definição e consolidação do processo)

## Objetivos do sFlow
- **Proporcionar** um exemplo de jornada de ideação → especificação → arquitetura → planejamento
- **Acelerar** o processo de discovery e especificação (< 1h para etapas 01-06)
- **Tornar auditável** prompts, decisões e artefatos gerados (rastreabilidade)
- **Produzir artefatos** claros, verificáveis e prontos para desenvolvimento
- **Manter alinhamento** contínuo entre stakeholders e equipe técnica

## Princípios do Framework
- **Gates de validação** a cada etapa com aprovação explícita do cliente
- **Neutralidade tecnológica** (o framework não impõe stack específica)
- **Prompt-based** nas etapas iniciais para agilidade e consistência
- **Versionamento** de artefatos em `docs/` e revisão por PR
- **Linguagem simples** centrada em valor para o usuário final

## Fluxo de Workflows

### 🚀 Fase 1: Discovery Rápido (~1 hora)
*Etapas conduzidas via prompts com validação imediata do cliente*

**01.** Capturar detalhes da ideia → `docs/intencao.md`
**02.** Gerar prompt para protótipo → `docs/prompt-prototipo.md`
**03.** Detalhar requisitos funcionais → `docs/features.md`
**04.** Mapear fluxo de navegação → `docs/fluxos-navegacao.md`
**05.** Detalhar requisitos não-funcionais → `docs/requisitos-nao-funcionais.md`
**06.** Definir arquitetura da solução → `docs/arquitetura-componentes.md`, `docs/arquitetura-diagrama.md`

### ⏸️ Gate Principal de Validação

### 🔧 Fase 2: Especificação Técnica 

**07.** Definir stack tecnológica → `docs/stack-tecnologica.md`
**08.** Definir padrões e boas práticas → `docs/guia-de-boas-praticas.md`
**09.** Compilar diagramas → `docs/diagramas/` (por contexto)

### ⏸️ Gate de Revisão

### 🔧 Fase 3: Especificação de Requisitos

**10.** Escrever histórias funcionais → `docs/historias/`
**11.** Escrever histórias não-funcionais → `docs/historias/`
**12.** Desenhar modelo de dados → `docs/modelo-de-dados.md`

### ⏸️ Gate de Revisão

### 🔧 Fase 4: Especificação de Design / UX

**13.** Desenhar interfaces → `docs/interfaces/`

### ⏸️ Gate de Aprovação Final

### 🔧 Fase 5: Especificação de Planejamento

**14.** Criar plano de trabalho → `docs/plano.md`

## Como Usar o sFlow

### Modelo de Trabalho
1. **Consultor** atua como facilitador entre IA e cliente
2. **IA** faz perguntas estruturadas via workflows 
3. **Cliente** responde às perguntas através do consultor
4. **Consultor** escreve as respostas e valida os artefatos gerados

### Processo por Etapa
1. **Executar workflow**: Use `/[número-nome-do-workflow]` no chat
2. **Facilitar diálogo**: Faça as perguntas da IA para o cliente
3. **Documentar respostas**: Escreva as respostas do cliente no chat
4. **Validar artefato**: Revise o documento gerado com o cliente
5. **Aprovar/iterar**: Aprove ou solicite ajustes antes de prosseguir

## Exemplo Prático no Windsurf

### Cenário: App de Delivery
```text
Cliente: "Preciso de um sistema para fazer pedidos de cardápio pelo celular"

Consultor inicia:
/01.capturar-detalhes-da-ideia
```

**IA pergunta:** "1. Qual problema específico o sistema vai resolver?"
**Consultor pergunta ao cliente e escreve:** "Reduzir tempo de espera no restaurante..."
**IA pergunta:** "2. Quem são os usuários principais?"
**Consultor pergunta ao cliente e escreve:** "Clientes do restaurante e garçons..."
**Resultado:** IA gera `docs/intencao.md` → Cliente aprova → Continua para `/02.prompt-prototipo`

### Dicas de Uso
- **Referencie contexto**: Use `@docs/intencao.md` ao iniciar novos workflows
- **Itere quando necessário**: Re-execute workflows se cliente solicitar mudanças
- **Valide sempre**: Não prossiga sem aprovação explícita do cliente
- **Use gates**: Pausas importantes para a consolidação de artefatos

Evolua para a próxima etapa apenas quando validar o conteudo gerado pelo LLM, faça ajustes sempre que necessário.

## Estrutura de Documentação Gerada

```
docs/
├── intencao.md                    # Etapa 01
├── prompt-prototipo.md            # Etapa 02  
├── features.md                    # Etapa 03
├── fluxos-navegacao.md             # Etapa 04
├── requisitos-nao-funcionais.md   # Etapa 05
├── arquitetura-componentes.md     # Etapa 06
├── arquitetura-diagrama.md        # Etapa 06
├── stack-tecnologica.md           # Etapa 07
├── guia-de-boas-praticas.md       # Etapa 08
├── modelo-de-dados.md             # Etapa 12
├── plano.md                       # Etapa 14
├── diagramas/                     # Etapa 09
│   ├── geral-do-projeto.md
│   ├── autenticacao.md
│   └── checkout.md
├── historias/                     # Etapas 10-11
│   ├── funcionais/
│   │   ├── us-001-login.md
│   │   └── us-002-pedido.md
│   └── nao-funcionais/
│       ├── nfr-001-performance.md
│       └── nfr-002-seguranca.md
└── interfaces/                    # Etapa 13
    ├── wireframes/
    └── especificacoes/
```

## Templates e Apresentação para Clientes

### Template de Apresentação dos Resultados
Para stakeholders e clientes, organize os artefatos em:

1. **Executive Summary** (20 min)
   - Resumo da `docs/intencao.md`
   - Principais features de `docs/features.md`
   - Visão da arquitetura de `docs/arquitetura-componentes.md`

2. **Demonstração Visual** (20 min)
   - Fluxos de `docs/fluxos-navegacao.md`
   - Diagramas de `docs/diagramas/`
   - Protótipo baseado em `docs/prompt-prototipo.md`

3. **Planejamento** (30 min)
   - Stack proposta de `docs/stack-tecnologica.md`
   - Cronograma de `docs/plano.md`
   - Próximos passos

### Checklist de Validação por Etapa
- [ ] **Gate Principal (após 01-06)**: Cliente aprovou intenção, features, fluxos e arquitetura?
- [ ] **Gate de Revisão (após 07-09)**: Stack e padrões técnicos validados? Diagramas aprovados?
- [ ] **Gate de Revisão (após 10-12)**: Histórias priorizadas? Modelo de dados validado?
- [ ] **Gate de Aprovação Final (após 13)**: Interfaces e experiência aprovadas pelo cliente?
- [ ] **Entrega Final (após 14)**: Plano de trabalho acordado e cronograma aprovado?

## Métricas Sugeridas

### Eficiência do Processo
- **Tempo de discovery**: Etapas 01-06 em < 1 hora?
- **Ciclo de feedback**: Tempo entre geração e aprovação de artefatos
- **Taxa de retrabalho**: % de workflows re-executados por mudanças

### Qualidade dos Artefatos
- **Completude**: % de seções preenchidas nos documentos gerados
- **Precisão**: Quantos ajustes manuais foram necessários pós-geração?
- **Alinhamento**: Cliente aprovou na primeira revisão?

### Impacto no Projeto
- **Redução de tempo**: Comparativo com processo anterior
- **Clareza de requisitos**: Menos dúvidas na fase de desenvolvimento
- **Satisfação**: Feedback do cliente sobre o processo

## Adaptação para Diferentes Clientes

### Clientes Mais Técnicos
- Detalhe mais a etapa 07 (stack tecnológica)
- Inclua mais diagramas técnicos na etapa 09
- Considere workshops técnicos no gate de validação

### Clientes de Negócio
- Foque nas etapas 01-06 com linguagem menos técnica
- Enfatize ROI e benefícios de negócio
- Use mais protótipos visuais (etapa 02)

### Projetos Complexos/Enterprise
- Considere quebrar a etapa 03 em sub-módulos
- Adicione requisitos de compliance na etapa 05
- Detalhe mais a governança na etapa 08

## Evolução do Framework

### Próximas Melhorias
- [ ] Templates específicos por tipo de projeto (web, mobile, enterprise)
- [ ] Integração com ferramentas de prototipação
- [ ] Biblioteca de exemplos por indústria
- [ ] Métricas automatizadas de qualidade dos artefatos

### Como Contribuir
1. Use o framework em projetos reais
2. Documente lições aprendidas
3. Proponha melhorias via PR
4. Compartilhe casos de sucesso/fracasso

### Feedback e Iteração
- Colete feedback a cada projeto finalizado
- Revise workflows baseado em problemas recorrentes  
- Mantenha exemplos atualizados com casos reais
- Evolua templates baseado em melhores práticas identificadas

## Licença
Accenture Song