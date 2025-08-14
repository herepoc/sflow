# sFlow — Framework de Trabalho Orientado por Prompts

## Visão Geral
sFlow é um framework de trabalho orientado por prompts para conceber, especificar e planejar sistemas de software. Ele organiza a colaboração entre pessoas e agentes de IA por meio de workflows versionados, do entendimento do problema até a arquitetura e planejamento de entrega.

- Status: Em elaboração (definição e consolidação do processo)
- Foco: Processo e artefatos, pré implementação

## Objetivos do sFlow
- Padronizar a jornada de ideação → especificação → arquitetura → planejamento.
- Tornar os prompts e decisões auditáveis e reprodutíveis (rastreabilidade).
- Produzir artefatos claros, verificáveis e prontos para desenvolvimento.
- Acelerar entregas, mantendo qualidade e alinhamento com stakeholders.

## Princípios do Framework
- Gates de validação a cada etapa com aprovação explícita.
- Neutralidade tecnológica (o framework não impõe stack).
- Versionamento de artefatos em `docs/` e revisão por PR.
- Linguagem simples, centrada em valor para o usuário.

## Workflows e Artefatos
Os workflows residem em `.windsurf/workflows/` e guiam a criação de artefatos em `docs/`.

1) Descoberta e definição
- 1. Capturar detalhes da ideia → `.windsurf/workflows/1. capturar-detalhes-da-ideia.md`
  - Output: `docs/intencao.md`
- 3. Detalhar requisitos funcionais → `.windsurf/workflows/3. detalhar-requisitos-funcionais.md`
  - Output: `docs/features.md`
- 5. Detalhar requisitos não‑funcionais → `.windsurf/workflows/5. detalhar-requisitos-nao-funcionais.md`
  - Output: `docs/non-funct.md`

2) Arquitetura e padrões
- 6. Definir arquitetura da solução → `.windsurf/workflows/6. definir-arquitetura-solucao.md`
  - Outputs: `docs/arquitetura-componentes.md`, `docs/arquitetura-diagrama.md` (Mermaid)
- 8. Definir padrões e boas práticas → `.windsurf/workflows/8.definir-padroes-e-boas-praaticas.md`
  - Output: `docs/guia-de-boas-praticas.md` (pode ser movido para `./.windsurf/rules` quando aplicável)

3) Planejamento de entrega
- 10. Escrever histórias funcionais → `.windsurf/workflows/10.escrever-historias-funcionais copy.md`
  - Output: `docs/user-stories.md`

Observação: execute os workflows na ordem, validando os outputs com as partes interessadas a cada etapa.

## Como Usar o sFlow
- Selecione o workflow correspondente à etapa atual.
- Conduza a interação por prompts conforme o arquivo do workflow.
- Gere o artefato no formato solicitado e salve em `docs/`.
- Submeta via PR para revisão/validação; somente avance após aprovação.
- Reitere conforme necessário; mantenha histórico de decisões no Git.


## Exemplo de Uso no Windsurf

### Passo a passo (rápido)
- Abra o chat do Windsurf no repositório.
- Informe a ideia inicial do projeto e “/” para listar os workflows e escolha o desejado.

```text
    Preciso de um sistema que para fazer pedidos de um cardapio pelo celular, 
    para acelerar o processo de pedido.

    /1. capturar-detalhes-da-ideia
```
- Siga as instruções do workflow, respondendo às perguntas no chat.
- Ao final, confirme a criação do arquivo proposto em `docs/`.
- Para a proxima etapa, e continue a cadeia (validando a cada etapa).

Observações:
- Use os artefatos anteriores como contexto ao iniciar o próximo workflow.
- Você pode referenciar arquivos com @ com as respostas das perguntas feitas pela LLM.
- Se necessário, ajuste os arquivos gerados e reexecute o workflow para iterar.


## Estrutura de Pastas Recomendada para a documentação
```
docs/
  intencao.md
  features.md
  non-funct.md
  arquitetura-componentes.md
  arquitetura-diagrama.md
  guia-de-boas-praticas.md
  user-stores/  
    us-001-ingestao-de-informacao.md
.windsurf/
  workflows/
```

## Evolução do Framework
- Itere a partir de feedback dos usuários do processo.
- Adicione novos workflows quando necessário (ex.: descoberta técnica, riscos, segurança).
- Mantenha exemplos mínimos de artefatos para referência rápida.

## Licença
Accenture Song