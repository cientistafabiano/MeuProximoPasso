# Meu Próximo Passo — Critérios de Sucesso

## 1. Objetivo deste documento

Este documento define **como saberemos se o MVP cumpriu sua função**.

Ele responde à pergunta:

> **O que precisa ser verdade para considerarmos a hipótese do produto validada?**

Os critérios de sucesso avaliam o produto como um todo. Eles não substituem os critérios de aceite de cada funcionalidade.

| Documento | Pergunta que responde |
| --- | --- |
| `success-criteria.md` | O produto cumpre sua função? |
| `acceptance-criteria.md` | Este comportamento foi implementado corretamente? |
| `scenarios.md` | Em quais situações cada comportamento deve ser verificado? |

---

## 2. Princípio: o critério avalia o sistema, não o usuário

Todo critério deste documento mede a **qualidade do sistema**, e nunca o desempenho da pessoa que o utiliza.

Exemplo:

```text
Muitas sugestões rejeitadas
        ↓
NÃO significa: o usuário falhou
        ↓
PODE significar: o Planner está sugerindo passos inadequados
```

Da mesma forma, um dia sem nenhuma atividade iniciada não é um fracasso do usuário. É uma informação que pode indicar que o sistema não conseguiu oferecer um próximo passo possível naquele contexto.

### Regra

> Quando um indicador for desfavorável, a primeira pergunta é "o que o sistema poderia ter feito diferente?", e não "o que o usuário deixou de fazer?".

---

## 3. Hipótese a ser validada

Conforme definido em `problem.md`:

> **Se o sistema conseguir transformar objetivos e tarefas em próximos passos pequenos, concretos e adaptáveis ao contexto atual, o usuário terá uma experiência mais clara para iniciar, executar e retomar suas atividades.**

Os critérios abaixo decompõem essa hipótese em comportamentos verificáveis.

---

## 4. Critérios de sucesso do MVP

### 4.1 Clareza do próximo passo

**CS-01 — Próximo passo visível ao abrir**

Ao abrir o sistema, o usuário consegue identificar o próximo passo principal sem precisar navegar para outra tela.

**CS-02 — Próximo passo concreto**

O próximo passo apresentado responde, no mínimo:

```text
O quê?          → qual ação realizar
Onde?           → em qual categoria / projeto / tarefa
Quanto tempo?   → duração da categoria (fixa, intervalo ou "até concluir")
```

Um próximo passo que não responde a essas perguntas ainda é uma tarefa abstrata (ver `problem.md`, seção 3).

---

### 4.2 Decisão e autonomia

**CS-03 — Escolha sem atrito**

O usuário consegue aceitar, rejeitar ou escolher uma alternativa dentro do próprio contexto do chat.

**CS-04 — Rejeição nunca é um beco sem saída**

Após uma rejeição, o sistema sempre apresenta outra opção disponível ou informa com clareza que não há outras opções no momento.

A rejeição não gera mensagem de cobrança.

---

### 4.3 Execução

**CS-05 — Ciclo curto de execução**

Uma tarefa pode ser iniciada e encerrada sem navegar por várias telas.

**CS-06 — Todos os resultados são registráveis**

Ao encerrar uma execução, o usuário consegue registrar qualquer um dos resultados previstos: concluída, parcialmente concluída ou adiada.

---

### 4.4 Adaptação

**CS-07 — O plano pode mudar**

Quando o próximo passo original não é viável (por contexto informado ou tempo disponível), o sistema consegue oferecer uma alternativa: menor, de outra tarefa ou de outra categoria.

---

### 4.5 Continuidade e retomada

**CS-08 — Nada desaparece**

Uma tarefa adiada ou parcialmente concluída continua disponível como opção em ciclos posteriores, enquanto estiver em aberto.

**CS-09 — Retomada registrada**

Quando uma atividade adiada ou interrompida é iniciada novamente, o sistema registra essa retomada.

**CS-10 — Saber onde parou**

Ao retomar uma tarefa, o usuário consegue ver o que foi registrado anteriormente sobre ela.

---

### 4.6 Histórico e dados

**CS-11 — Reconstrução de um dia**

A partir do histórico, é possível reconstruir o que aconteceu em um dia: o que foi sugerido, o que foi escolhido, o que foi executado e qual foi o resultado.

**CS-12 — Visualizações com dados reais**

A visualização semanal utiliza exclusivamente dados registrados pelo sistema.

---

### 4.7 Linguagem e princípios

**CS-13 — Ausência de julgamento**

Nenhuma tela ou mensagem do sistema apresenta:

* nota ou pontuação de produtividade;
* percentual de "aproveitamento" do usuário;
* linguagem de culpa ("você não cumpriu", "você falhou", "de novo?");
* comparação do usuário com um ideal.

Os dados são apresentados como fatos: "X atividades de Programação, Y de Inglês, 1 retomada".

---

### 4.8 Arquitetura

**CS-14 — Funcionamento sem LangGraph e sem LLM**

O ciclo completo (sugerir → escolher → executar → registrar → histórico) funciona sem LangGraph e sem modelo de linguagem.

**CS-15 — Próximo passo com tag de origem**

Quando um próximo passo já foi adiado ou rejeitado antes, ele é apresentado com uma **tag** que informa isso (ex.: "adiado em 05/10", "sugerido antes").

A tag é registrada junto com o evento da sugestão. Assim, na revisão, é possível saber se as rejeições se concentram em passos novos ou em passos que já haviam sido adiados.

A tag usa linguagem neutra: informa o fato, sem contagem acusatória (evitar "adiado 4 vezes").

---

## 5. Indicadores de validação

Os indicadores abaixo são calculados a partir dos eventos registrados. Eles avaliam o **funcionamento do produto**.

| Indicador | O que revela sobre o sistema |
| --- | --- |
| Tempo entre abrir o sistema e iniciar um passo | Se o próximo passo está claro o suficiente para começar |
| Aceitação da primeira sugestão | Se o Planner acerta a sugestão principal |
| Rejeições até iniciar um passo | Se as alternativas são adequadas |
| Execuções iniciadas que recebem resultado registrado | Se registrar o resultado é simples o suficiente |
| Tarefas adiadas que foram retomadas depois | Se o sistema favorece a retomada |
| Categorias com tarefa aberta e sem atividade por longo período | Se o Planner está deixando categorias esquecidas |
| Dias em que o sistema foi aberto sem nenhum passo iniciado | Se o sistema consegue oferecer algo possível em dias difíceis |

### Valores de referência

Nenhum valor-alvo é definido antecipadamente.

A primeira semana de uso real servirá como **linha de base**. Os valores de referência serão definidos a partir dela e registrados neste documento.

---

## 6. Método de validação

### Decidido

* **Período de validação:** 2 semanas de uso real pelo autor.
* **Observações qualitativas:** registradas em uma lista e também persistidas no banco de dados.

```text
Semana 1 → uso real → linha de base dos indicadores
        ↓
Revisão 1 (dia 7) → ajuste de regras do Planner / UX
        ↓
Semana 2 → uso com os ajustes
        ↓
Revisão 2 (dia 14) → comparação com a linha de base → decisão
```

### Frequência de revisão

| Momento | O que fazer | Duração |
| --- | --- | --- |
| Fim de cada dia | Anotar uma observação curta (o que funcionou, o que travou) | ~2 min |
| Dia 7 | Fechar a linha de base e decidir ajustes | ~30 min |
| Dia 14 | Comparar com a linha de base e decidir próximos passos do produto | ~30 min |

A anotação diária existe porque, em apenas duas semanas, detalhes qualitativos se perdem até a revisão semanal. Ela deve ser opcional: um dia sem anotação não invalida a validação.

---

## 7. Sinais de alerta

Os seguintes sinais indicam que o produto pode estar se afastando de sua proposta:

* o usuário precisa ir a outra tela para descobrir o que fazer;
* sugestões da mesma categoria são rejeitadas repetidamente;
* tarefas adiadas deixam de aparecer como opção;
* o registro de resultado é pulado com frequência;
* o usuário evita abrir o sistema em dias ruins — possível sinal de que o produto está transmitindo cobrança.

---

## 8. Critérios para evolução para LangGraph

A evolução para a Fase 1 deve ser justificada por necessidades observadas, e não pela disponibilidade da tecnologia.

### Sinais de que a evolução pode ser necessária

* o fluxo da conversa passa a ter muitos caminhos condicionais difíceis de manter em serviços simples;
* conversas de vários turnos exigem um estado compartilhado entre etapas;
* torna-se necessário pausar e retomar fluxos de conversa (checkpoint);
* novas etapas de decisão passam a depender umas das outras.

### Como saberemos que a nova arquitetura melhorou o produto

* os mesmos cenários de `scenarios.md` continuam sendo atendidos;
* os critérios de sucesso deste documento não pioram;
* o fluxo se torna mais simples de entender, modificar e testar;
* cada Node possui uma responsabilidade que pode ser explicada.

Se nenhuma dessas condições for observada, a evolução não é necessária naquele momento.

---

## 9. O que NÃO é critério de sucesso

O MVP **não** será avaliado por:

* o usuário cumprir todas as tarefas planejadas;
* aumento de horas produtivas;
* todas as categorias aparecerem todos os dias;
* consistência perfeita ao longo da semana;
* ausência de adiamentos.

Adiamentos, execuções parciais e dias sem atividade fazem parte do funcionamento normal do produto.

---

## 10. Resumo

O MVP será considerado bem-sucedido quando:

> **o usuário abre o sistema, sabe qual pode ser o próximo passo, decide livremente, executa, registra o que aconteceu e consegue retomar depois — sem que o sistema transforme esse processo em cobrança.**

---

## 11. Relação com outros documentos

* `problem.md` — origem da hipótese;
* `principles.md` — base dos critérios de linguagem e autonomia;
* `requirements.md` — requisitos que sustentam cada critério;
* `domain/events.md` — eventos necessários para calcular os indicadores;
* `testing/acceptance-criteria.md` — verificação comportamento a comportamento;
* `testing/scenarios.md` — situações usadas na validação e na comparação com LangGraph.