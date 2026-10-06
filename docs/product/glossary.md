# Meu Próximo Passo — Glossário

## 1. Objetivo deste documento

Este documento fixa o significado dos termos usados no produto.

Todos os outros documentos — domínio, dados, API, UX — devem usar os termos com o significado definido aqui. Quando um termo mudar, ele muda aqui primeiro.

Termos marcados como **(proposta)** ainda precisam de confirmação do autor.

---

## 2. Estrutura

```text
Categoria
   ↓
Fonte de tarefas (Plano ou Backlog)
   ↓
[Projeto]  ← apenas em Programação
   ↓
Tarefa (Issue, quando pertence a um projeto)
   ↓
Próximo passo
   ↓
Sugestão  →  usuário decide
   ↓
Execução
   ↓
Resultado
   ↓
Evento  →  Histórico
```

---

## 3. Organização

### Categoria

Área de desenvolvimento que participa da rotina do usuário. Categorias do MVP: 💻 Programação, 🇺🇸 Inglês, 💼 LinkedIn, 💪 Treino (Calistenia).

Uma categoria possui nome, ícone, lema, frequência, fonte de tarefas, duração de referência e status.

**Regra:** toda categoria ativa possui um próximo passo disponível até ser finalizada.

### Lema

Frase que expressa o sentido da categoria para o usuário. Ex.: Inglês — "Aumentar minhas possibilidades".

### Status da categoria

* **Ativa** — participa da rotina conforme sua frequência.
* **Finalizada** — encerrada por conclusão; não participa da rotina, mas mantém seu histórico e pode ser **reativada**.

Uma categoria nunca é apagada.

### Frequência

Regularidade com que a categoria participa da rotina. Ex.: todos os dias (Inglês), cerca de três vezes por semana (LinkedIn).

### Plano **(proposta)**

Agenda que define o que a categoria propõe em cada dia. Ex.: o plano de Inglês define "Segunda — Aula KNN", "Terça — Listening".

> Substitui o uso de "programação" no sentido de agenda, para não confundir com a categoria 💻 Programação (ver INC-05).

### Fonte de tarefas

De onde vêm as tarefas de uma categoria. Existem dois tipos:

* **Plano** (recorrente) — a tarefa nasce do plano conforme o dia. Ex.: Inglês, LinkedIn, Treino.
* **Backlog** (acumulado) — as tarefas são cadastradas e ficam em aberto até serem concluídas. Ex.: Programação.

Ver `domain/categories.md`.

### Backlog

Conjunto de tarefas cadastradas que existem até serem concluídas, independentemente do dia. Uma tarefa de backlog não "vence": se não for feita hoje, continua lá amanhã.

### Projeto

Agrupador de issues dentro de 💻 Programação. Ex.: Soberana.

Um projeto pode ser concluído sem que a categoria seja finalizada.

### Tarefa

Unidade de trabalho disponível em uma categoria. É o termo genérico.

### Issue

Tarefa que pertence a um projeto. As issues de um projeto possuem **ordem**: uma issue pode depender da anterior.

### Tarefa do plano

Tarefa que nasce do plano de uma categoria em determinado dia (também chamada **etapa**). É oferecida **apenas no seu dia**, exceto se for obrigatória.

### Etapa obrigatória

Etapa de plano que, se não for concluída no seu dia, continua sendo oferecida até ser concluída. Ex.: Post — projeto, do LinkedIn. Descreve uma regra de persistência, não uma cobrança.

> Não existem tarefas avulsas: toda tarefa pertence ao backlog ou ao plano da sua categoria.

### Tarefa em aberto

Tarefa que ainda não foi concluída e pode originar um próximo passo.

### Objetivo **(em aberto)**

Termo presente na Documentação Inicial (`Goal`). Ainda não está decidido se existe como entidade própria ou se o papel é cumprido pela Categoria e seu Lema (ver INC-07).

---

## 4. Decisão

### Rotina do dia

Conjunto de categorias que podem participar do dia: categorias **ativas**, **previstas para hoje** pela frequência/plano e com **tarefa em aberto**.

### Contexto

Informação fornecida pelo usuário que influencia a escolha do próximo passo: o que quer fazer, em qual projeto, quanto tempo tem, como está. Pode vir da conversa ou do check-in.

### Check-in

Momento simples em que o sistema pergunta como o usuário está. Sem escalas numéricas no MVP e sem objetivo diagnóstico.

### Planner

Componente que escolhe o próximo passo a partir da rotina do dia, do contexto, do histórico e de regras explícitas. No MVP é determinístico.

### Próximo passo

Ação concreta, derivada de uma tarefa, que responde: **o quê**, **onde** e **por quanto tempo**. Não precisa ser a tarefa inteira.

Ex.: tarefa "Issue #4 — tela de login" (categoria Soberana) → próximo passo "Abrir o Soberana e criar o formulário de login — 30 min".

### Sugestão

Proposta do sistema de um próximo passo. Pode ser **principal** ou **alternativa**.

### Tag de origem

Marcação exibida no próximo passo que informa seu histórico recente. Ex.: "adiado em 05/10", "sugerido antes". Torna visível por que aquele passo está aparecendo e fica registrada no evento da sugestão.

### Sugestão principal

A única sugestão em destaque em um dado momento.

### Alternativa

Outra sugestão oferecida junto ou após a principal. Pode ser da mesma categoria ou de outra.

### Rejeição

Recusa de uma **sugestão** pelo usuário.

> **Rejeitar uma sugestão não altera a tarefa.** A tarefa continua em aberto. Rejeição não é adiamento nem falha.

### Sugestão proativa **(futuro — FUT-01)**

Sugestão que o sistema apresenta sem ter sido solicitada, quando o usuário abriu o sistema e não iniciou a conversa após um tempo (~15 min), com base na hora do dia e no histórico.

### Lembrete

Aviso enviado ao usuário após um período sem entrar no sistema. Fora do MVP (ver FUT-02).

---

## 5. Execução

### Execução (sessão)

Período em que o usuário trabalha em um próximo passo, do início até o registro do resultado.

### Resultado

O que aconteceu na execução:

* **Concluída** — o próximo passo foi realizado.
* **Parcialmente concluída** — parte foi realizada; a tarefa continua em aberto.
* **Adiada** — não foi realizada agora; a tarefa continua em aberto para outro momento.

> Padronizado como **adiada**; "postergada" não deve ser usado (ver INC-06). Estados e transições definitivos ficam em `task-states.md`.

### Interrupção

Execução iniciada que parou antes de um resultado de conclusão.

### Retomada

Início de uma nova execução sobre uma tarefa que havia sido adiada, interrompida ou parcialmente concluída.

### Duração de referência

Tempo que a categoria propõe por execução. Pode ser fixa (Inglês, 20 min), um intervalo (Treino, 20 a 30 min) ou **até concluir** (Programação, posts do LinkedIn). Em planos, pode variar por etapa. Ajuste com base no histórico fica para evolução futura (ver FUT-03).

### Duração real

Tempo efetivamente gasto, registrado na execução.

### Dificuldade percebida

Avaliação do usuário, após a execução, sobre o quão difícil foi.

---

## 6. Registro

### Evento

Fato registrado com data e hora. Ex.: sugestão apresentada, sugestão rejeitada, execução iniciada, resultado registrado. Eventos não são editados para "corrigir" o passado.

### Histórico

Conjunto de eventos organizado para consulta.

### Fato × Interpretação

* **Fato** — algo registrado (um evento).
* **Interpretação** — conclusão derivada dos fatos (ex.: "LinkedIn sem atividade há 6 dias").

O sistema sempre distingue os dois (RNF-05).

### Linha de base

Valores dos indicadores medidos na primeira semana de validação, usados como referência de comparação.

---

## 7. Conversa

### Intenção

O que o usuário quer fazer com uma mensagem. Ex.: iniciar uma categoria, rejeitar uma sugestão, informar contexto.

### Entidade

Elemento reconhecido em uma mensagem: categoria, projeto, issue, duração, dia, disposição.

### Palavra-chave

Termo cadastrado que permite reconhecer uma entidade ou intenção. Ex.: "soberana" → projeto Soberana.

### Pergunta de esclarecimento

Pergunta feita pelo sistema quando a mensagem é ambígua ou incompleta, sempre com opções para o usuário escolher.

Ver `domain/conversation-rules.md`.