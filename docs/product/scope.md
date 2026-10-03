# Meu Próximo Passo — Escopo do Produto

## 1. Objetivo deste documento

Este documento define o escopo do produto **Meu Próximo Passo**, estabelecendo:

* o que faz parte do produto;
* o que faz parte do MVP;
* o que não faz parte do MVP;
* o que pertence a evoluções futuras;
* os limites de atuação do sistema.

O objetivo é evitar que novas ideias sejam incorporadas ao produto sem uma decisão consciente sobre sua prioridade e seu momento de implementação.

---

# 2. Escopo geral do produto

O **Meu Próximo Passo** é um Sistema de Apoio à Decisão (DSS) pessoal que ajuda o usuário a transformar objetivos e tarefas em **próximos passos concretos e executáveis**.

O sistema considera, progressivamente:

* objetivos do usuário;
* tarefas disponíveis;
* contexto atual;
* histórico de execução;
* tempo disponível;
* resultados das ações anteriores.

A decisão final permanece com o usuário.

O produto não tem como objetivo controlar a rotina do usuário, estabelecer uma produtividade ideal ou determinar como ele deve conduzir sua vida.

---

# 3. Escopo do MVP

O MVP deve validar a hipótese central do produto:

> O sistema consegue ajudar o usuário a identificar e executar um próximo passo possível?

Para isso, o MVP deve contemplar:

### 3.1 Conversação

A conversa será uma das principais formas de interação do sistema.

O usuário poderá informar seu contexto e conversar sobre o que pretende fazer.

A interação deve permitir que o sistema compreenda o necessário para propor um próximo passo.

---

### 3.2 Check-in simples

O MVP terá um check-in simples para compreender o contexto atual do usuário.

O check-in não terá como objetivo realizar avaliação psicológica ou diagnóstico.

Informações mais complexas sobre estado, energia, humor ou outros parâmetros poderão ser estudadas posteriormente.

---

### 3.3 Objetivos e tarefas

O usuário poderá trabalhar com objetivos e tarefas relacionados às suas áreas de interesse.

As categorias iniciais definidas para o produto são:

* 💻 Programação — construir meu futuro
* 🇺🇸 Inglês — aumentar minhas possibilidades
* 💪 Calistenia — fortalecer meu corpo
* 💼 LinkedIn — mostrar meu trabalho

A definição completa do modelo de categorias e sua expansão será detalhada posteriormente na documentação de domínio.

---

### 3.4 Próximo passo

O sistema deverá transformar uma tarefa ou objetivo em uma ação concreta.

O usuário deverá receber:

* um próximo passo principal;
* alternativas possíveis.

As alternativas poderão pertencer:

* à mesma categoria;
* a outra categoria.

O usuário poderá aceitar, rejeitar ou escolher outra alternativa.

O sistema trabalhará inicialmente com **um próximo passo principal por vez**, evitando apresentar uma lista excessiva de ações.

---

### 3.5 Execução

O usuário deverá conseguir iniciar uma ação e registrar seu resultado.

O MVP deverá considerar estados básicos de execução, incluindo:

* iniciada;
* concluída;
* parcialmente concluída;
* adiada/postergada.

A definição formal dos estados e das transições será detalhada posteriormente no domínio.

---

### 3.6 Histórico

O sistema deverá registrar acontecimentos relevantes da execução.

O histórico deverá permitir, progressivamente, compreender:

* o que foi realizado;
* o que foi parcialmente realizado;
* o que foi postergado;
* quando uma atividade foi retomada;
* quais categorias foram utilizadas.

O histórico representa acontecimentos registrados, e não uma avaliação do usuário.

---

### 3.7 Visualização da semana

O produto deverá possuir uma visão que permita ao usuário observar sua atividade ao longo da semana.

Essa visualização deverá utilizar dados reais registrados pelo sistema.

O objetivo é permitir percepção do próprio comportamento, e não gerar uma nota de produtividade.

---

# 4. O que NÃO faz parte do MVP

Os seguintes elementos não fazem parte da primeira versão e não devem ser implementados prematuramente.

## 4.1 Inteligência artificial avançada

O MVP não depende de IA generativa para funcionar.

A arquitetura inicial deve permitir que as regras do produto sejam executadas de maneira determinística.

IA poderá ser incorporada posteriormente onde houver valor real para interpretação, linguagem ou adaptação contextual.

---

## 4.2 LangGraph

LangGraph não é requisito do MVP.

A arquitetura deve ser construída de forma que uma evolução para LangGraph seja possível quando houver necessidade real de:

* estado compartilhado;
* múltiplas etapas de decisão;
* fluxos condicionais;
* memória;
* checkpoints;
* maior complexidade de orquestração.

---

## 4.3 Sistema de pontuação

O produto não terá um **score de produtividade**.

Não haverá uma nota para determinar se o usuário foi:

* produtivo;
* pouco produtivo;
* bom;
* ruim.

O sistema deverá apresentar fatos e padrões registrados.

---

## 4.4 Diagnóstico do usuário

O sistema não terá como objetivo diagnosticar:

* saúde mental;
* condições psicológicas;
* transtornos;
* níveis clínicos de ansiedade;
* outros estados clínicos.

Informações relacionadas ao contexto pessoal deverão ser utilizadas apenas dentro dos limites necessários para apoiar a decisão sobre o próximo passo.

---

## 4.5 Automação total das decisões

O sistema não deverá decidir pelo usuário qual caminho de vida seguir.

A recomendação poderá ser apresentada pelo sistema, mas o usuário mantém a decisão final.

---

# 5. Evoluções futuras

Algumas capacidades fazem parte da visão do produto, mas serão desenvolvidas posteriormente.

## 5.1 Adaptação contextual

O sistema poderá utilizar informações como:

* disposição relatada;
* tempo disponível;
* histórico recente;
* dificuldade percebida;
* horário;
* padrão de execução.

Essas informações poderão ajudar a selecionar uma ação mais adequada ao contexto.

---

## 5.2 Parâmetros baseados em evidências

Futuramente poderá ser estudada a utilização de evidências científicas para definir parâmetros de adaptação das recomendações.

Por exemplo, investigar como diferentes condições de disposição, duração da atividade ou características da tarefa podem influenciar a escolha de um próximo passo.

Essa evolução deverá ser baseada em pesquisa específica e documentada antes de ser incorporada às regras do sistema.

---

## 5.3 Análise histórica

O sistema poderá analisar padrões como:

* categorias nas quais o usuário mais atua;
* tempo dedicado a cada categoria;
* horários de maior atividade;
* tarefas concluídas;
* tarefas parcialmente concluídas;
* tarefas postergadas;
* frequência de retomadas.

Essas informações deverão servir para compreensão e apoio à decisão, e não para criar uma pontuação pessoal.

---

## 5.4 Registro detalhado das tarefas

Futuramente, uma tarefa poderá conter informações como:

* descrição;
* categoria;
* duração planejada;
* duração real;
* dificuldade percebida;
* resultado da execução.

O usuário também poderá criar uma tarefa durante a própria conversa.

Por exemplo:

> "Vou fazer programação."

O sistema poderá conduzir a conversa até transformar essa intenção em uma tarefa concreta.

---

## 5.5 Cards de tarefas

As tarefas poderão ser representadas visualmente como cards.

O card poderá permitir:

* visualizar a tarefa;
* iniciar;
* concluir;
* registrar resultado;
* informar duração;
* informar dificuldade;
* registrar conclusão parcial ou adiamento.

A estrutura detalhada dos cards será definida na documentação de UX.

---

## 5.6 Memória e contexto

O sistema poderá evoluir para manter maior contexto sobre:

* objetivos;
* histórico;
* preferências;
* padrões de execução;
* decisões anteriores.

Essa memória deverá servir à continuidade da experiência e à qualidade das recomendações, sem retirar a autonomia do usuário.

---

## 5.7 Inteligência contextual

Em uma evolução posterior, o sistema poderá interpretar melhor situações como:

> "Estou cansado, mas quero fazer alguma coisa."

A partir de informações disponíveis, poderá selecionar alternativas mais compatíveis com o contexto.

Esse comportamento deverá ser definido por regras claras e, quando apropriado, apoiado por pesquisas e evidências.

---

# 6. Limites do produto

O **Meu Próximo Passo** não pretende:

* organizar toda a vida do usuário;
* substituir sua capacidade de decisão;
* criar uma rotina perfeita;
* cobrar produtividade;
* punir interrupções;
* diagnosticar condições pessoais;
* determinar quais objetivos o usuário deve possuir;
* transformar execução em uma competição;
* criar uma nota para medir o valor do usuário.

Seu papel é mais específico:

> **ajudar o usuário a recuperar clareza sobre qual pode ser o próximo passo possível.**

---

# 7. Critério para inclusão de novas funcionalidades

Uma nova funcionalidade deverá ser avaliada considerando principalmente:

1. Ela ajuda o usuário a identificar ou executar o próximo passo?
2. Ela preserva a autonomia do usuário?
3. Ela transforma dados em apoio à decisão, em vez de julgamento?
4. Ela contribui para a continuidade e retomada?
5. Ela é necessária neste momento ou pertence a uma evolução futura?

Se uma funcionalidade não for necessária para validar a proposta central, ela poderá ser registrada como evolução futura em vez de incorporada ao MVP.

---

# 8. Relação com os próximos documentos

Este documento define **o limite do produto**, mas não detalha sua implementação.

As próximas decisões deverão ser aprofundadas em documentos específicos:

* **requirements.md** — requisitos funcionais e não funcionais;
* **user-flow.md** — jornada principal do usuário;
* **chat-flow.md** — funcionamento da conversa;
* **task-flow.md** — criação, execução e encerramento das tarefas;
* **categories.md** — categorias iniciais e futuras;
* **task-states.md** — estados e transições das tarefas;
* **planner-rules.md** — regras para escolha do próximo passo;
* **data-model.md** — dados necessários para sustentar o produto;
* **acceptance-criteria.md** — critérios para considerar cada comportamento implementado.

---

# 9. Definição atual do MVP

O MVP do **Meu Próximo Passo** pode ser resumido como:

> **Conversar → compreender o contexto → identificar uma tarefa → propor um próximo passo → oferecer alternativas → permitir que o usuário escolha → executar → registrar o resultado → construir histórico.**

O produto começa simples.

Sua evolução deverá acontecer a partir das necessidades observadas no uso real, e não da complexidade tecnológica disponível.
