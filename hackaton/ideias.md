# Hackaton sFlow — Catálogo de Ideias

Este documento reúne ideias sugeridas para o hackaton. Cada time deve escolher uma ideia distinta e reduzir o escopo para um MVP utilizável em 1 semana.

Como usar:
- Selecione uma ideia e valide o recorte com o time (o que cabe entregar em 1 semana).
- Caso use o sFlow (opcional), gere artefatos em `docs/` para apoiar decisões e comunicação.
- Documente no README do time: objetivo, como rodar e principais decisões.

---

## 1) Auxiliar de lista de compras de supermercado
- Problema: pessoas perdem tempo planejando compras e esquecem itens.
- Público-alvo: consumidores finais (famílias/indivíduos).
- Proposta de valor: agilizar criação e manutenção de listas com sugestões inteligentes.
- MVP (1 semana):
  - Criar lista por texto livre (ex.: “semana low-carb p/ 2 pessoas”).
  - Itens sugeridos com categorias; marcar como comprado/não comprado.
  - Exportar/compartilhar (link ou CSV simples).
- Uso de LLM (opcional):
  - Gerar lista a partir de objetivos/receitas; normalizar itens ("tomate" → "Tomate, 1kg").
  - Substituições inteligentes (se indisponível, sugerir alternativa).
- Métricas: tempo para criar lista, número de itens ajustados, NPS.
- Riscos: variação regional de produtos; dados de preços não disponíveis.

### Observações do proponente
- Histórico via foto da nota fiscal (OCR) para inferir reposição.
- Lista compartilhada entre moradores com pedidos incrementais/decrementais.
- Foco em itens genéricos (ex.: “sabão em pó”), não em marcas específicas.
- Sugestões de receitas para orientar compras.
## 2) Lista de compras para empresas (restaurantes)
- Problema: compras recorrentes sem padronização aumentam custo/desperdício.
- Público-alvo: restaurantes/bares pequenos.
- Proposta de valor: padronizar listas por receita e período.
- MVP (1 semana):
  - Catálogo básico de insumos com unidade padrão.
  - Listas por receita e por semana; totalizador por unidade.
  - Exportação para pedido ao fornecedor.
- Uso de LLM: cálculo de insumos por porção/volume com base em receitas em texto.
- Métricas: tempo por pedido, redução de erros, satisfação do gestor.
- Riscos: unidades/medidas inconsistentes; ausência de integração com ERPs.

### Observações do proponente
- App por colaborador com permissões na empresa.
- Colaboradores sinalizam necessidades no dia a dia; o sistema consolida a lista para o responsável por compras.
- Lembretes automáticos baseados nas interações e frequência de consumo.


## 3) Pedido por QR Code (mesa/quarto)
- Problema: espera por atendimento e erros de pedido em mesas/quartos.
- Público-alvo: restaurantes e hotéis.
- Proposta de valor: autoatendimento por QR com status do pedido.
- MVP (1 semana):
  - Cardápio simples (texto + preço), QR por mesa/quarto.
  - Fluxo: abrir cardápio → adicionar itens → confirmar pedido.
  - Painel operador: ver fila de pedidos e marcar status.
- Uso de LLM: organizar/sugerir combos a partir de preferências em texto.
- Métricas: tempo médio de pedido, taxa de erro, feedback do operador.
- Riscos: pagamento online fora do escopo em 1 semana; impressão fiscal.

### Observações do proponente
- Fluxo: ler QR → escolher itens → escrever observações → enviar → acompanhar status.
- Objetivo: reduzir fricção sem intermediação de garçom/telefone (estilo “iFood privado” no local).



## 4) Agendador online para autônomos (com calendário)
- Problema: agendamentos via chat causam conflito e retrabalho.
- Público-alvo: prestadores autônomos (consultas, aulas, estética).
- Proposta de valor: agenda pública com slots disponíveis e confirmação.
- MVP (1 semana):
  - Definição de serviços e durações; janela de atendimento.
  - Link público para clientes marcarem; e-mail de confirmação.
  - Integração simples: exportar .ics (ou orientação manual de integração).
- Uso de LLM: redigir mensagens de confirmação/políticas e FAQ a partir de texto do profissional.
- Métricas: no-show, tempo para agendar, taxa de ocupação.
- Riscos: integrações nativas com Google/Microsoft podem exceder a semana.

## 5) Reservas para salões/barbearias
- Problema: encaixes manuais e falhas de comunicação.
- Público-alvo: salões de beleza, barbearias pequenas.
- Proposta de valor: agenda por profissional/serviço com confirmação.
- MVP (1 semana):
  - Cadastro de serviços, profissionais e horários.
  - Página pública de reserva com confirmação simples.
  - Painel interno para gerenciar reservas.
- Uso de LLM: geração de descrições de serviços e políticas a partir de rascunhos.
- Métricas: taxa de ocupação, cancelamentos, tempo para marcar.
- Riscos: pagamentos/integrações podem extrapolar.

### Observações do proponente
- Cenário coworking: profissionais de estética/barbearia/consultórios reservam posição/box por diária.
- Reserva do espaço e notificação quando abrir vaga; possibilidade de efetuar pagamento da diária.
## 6) Check-in de hospital/clínica
- Problema: filas e retrabalho na recepção.
- Público-alvo: clínicas de pequeno porte.
- Proposta de valor: pré-check-in digital para reduzir tempo presencial.
- MVP (1 semana):
  - Coleta de dados básicos e anexos (RG/convênio) antes da visita.
  - Geração de protocolo de atendimento.
  - Painel recepção: ver/confirmar chegadas.
- Uso de LLM: validar consistência de formulários e sugerir correções.
- Métricas: tempo médio de atendimento, retrabalho, satisfação.
- Riscos: dados sensíveis exigem cuidado; limitar a dados fictícios no evento.

### Observações do proponente
- Upload prévio de dados e comprovantes de plano de saúde; acompanhar status sem deixar documentos no balcão.
- Meta: acelerar check-in, reduzir filas e transparência para o paciente.
## 7) Programa de fidelidade para pequenos negócios
- Problema: baixa recorrência por falta de incentivo.
- Público-alvo: cafeterias, lanchonetes, lojas locais.
- Proposta de valor: pontuação simples e recompensas.
- MVP (1 semana):
  - Registro de compras por cliente (e-mail/telefone).
  - Regras simples de pontos e resgate.
  - Painel operador: lançar pontos/validar resgates.
- Uso de LLM: mensagens personalizadas e campanhas a partir de diretrizes.
- Métricas: frequência de compra, número de clientes ativos.
- Riscos: fraudes/duplicidades exigem cautela.

### Observações do proponente
- Capturar contato (telefone/e-mail) e solicitar feedback via WhatsApp/integrações.
- Gerar relatórios e dashboard com apoio de IA.
- Nota: escopo aproxima-se de “Análise de feedback de clientes”; considerar sinergia com a ideia 9.
## 9) Análise de feedback de clientes
- Problema: feedback disperso (planilhas, formulários) sem análise.
- Público-alvo: pequenos negócios B2C.
- Proposta de valor: agrupar, classificar e extrair insights acionáveis.
- MVP (1 semana):
  - Importar CSV/planilha de feedback.
  - Classificação por tema/sentimento e dashboard simples.
  - Exportar relatório executivo.
- Uso de LLM: categorização, resumo e geração de insights.
- Métricas: tempo de análise, qualidade dos insights (avaliação do dono).
- Riscos: qualidade dos dados; vieses na classificação.

## 10) Controle de cobranças para diaristas
- Problema: difícil acompanhar clientes, valores e recebimentos.
- Público-alvo: diaristas e prestadores semelhantes.
- Proposta de valor: agenda + cobrança simples (registro manual).
- MVP (1 semana):
  - Cadastro de clientes/serviços; agenda de visitas.
  - Registro de cobranças e status (pago/em aberto).
  - Resumo mensal.
- Uso de LLM: gerar mensagens de cobrança educadas a partir de tom desejado.
- Métricas: inadimplência, tempo de controle, satisfação do prestador.
- Riscos: integrações de pagamento fora do escopo.

### Observações do proponente
- Registrar agendamentos e alterações combinadas (hoje feitas por WhatsApp) de forma rastreável.
- Gerar cobrança com chave PIX e controlar recebimento (pago/em aberto) por cliente.
- Histórico por cliente e lembretes de reagendamento/cobrança.

---

## Modelo de submissão por time (copie e preencha no README do seu time)
```md
# [Nome da ideia]

## Problema
[Descreva o problema real do usuário]

## Público-alvo
[Quem é impactado]

## Proposta de valor (MVP 1 semana)
[O que exatamente será entregue em 1 semana]

## Fluxo básico do usuário
[Passo a passo simples da jornada]

## Uso de LLM (se aplicável)
[Onde a IA entra: geração de listas, normalização, textos, classificação, etc.]

## Métricas de sucesso
[2–4 métricas simples para acompanhar]

## Riscos e limitações
[O que pode impedir a entrega ou reduzir o valor]
```

## Critérios de escolha rápida (guia)
- Valor em 1 semana: é demonstrável e útil?
- Complexidade técnica: cabe no tempo com o time disponível?
- Disponibilidade de dados: dá para testar com dados sintéticos?
- Clareza do escopo: backlog do MVP é curto e priorizado?
