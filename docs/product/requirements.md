# Meu Próximo Passo — Requisitos do Produto

## 1. Objetivo

Este documento define os requisitos do **Meu Próximo Passo** para orientar a construção do produto.

Os requisitos descrevem **o que o sistema deve ser capaz de fazer**, sem definir ainda sua implementação técnica.

As regras detalhadas de decisão, modelo de dados, interface e arquitetura serão especificadas em documentos próprios.

---

# 2. Requisitos funcionais

## RF-01 — Cadastro de categorias

O sistema deve permitir o cadastro de categorias.

Cada categoria deverá possuir informações que permitam ao sistema determinar:

* sua identificação;
* sua frequência de participação na rotina;
* sua programação;
* suas tarefas em aberto;
* seu estado de atividade.

Os campos definitivos ainda serão especificados no modelo de domínio.

---

## RF-02 — Categorias iniciais

O sistema deve permitir trabalhar inicialmente com as seguintes categorias:

* Programação;
* Inglês;
* Calistenia;
* LinkedIn.

Essas categorias não devem ser tratadas como categorias permanentes ou exclusivas do sistema.

---

## RF-03 — Cadastro de novas categorias

O sistema deve permitir que novas categorias sejam cadastradas no MVP.

A forma detalhada de cadastro e os campos necessários serão definidos posteriormente.

---

## RF-04 — Frequência da categoria

O sistema deve permitir configurar a frequência de uma categoria.

A frequência poderá variar entre categorias.

Exemplos:

* uma categoria pode ocorrer diariamente;
* outra pode ocorrer três vezes por semana;
* outra pode depender da existência de tarefas abertas.

O sistema não deve assumir uma frequência universal para todas as categorias.

---

## RF-05 — Programação da categoria

O sistema deve permitir associar uma programação à categoria quando necessário.

A programação poderá determinar em quais dias ou condições a categoria deverá participar da rotina.

A estrutura exata dessa programação ainda será definida.

---

## RF-06 — Tarefas em aberto

O sistema deve permitir que uma categoria possua tarefas em aberto.

Essas tarefas deverão servir como fonte para a definição de próximos passos.

O sistema não deverá depender exclusivamente de tarefas criadas pelo próprio Planner.

---

## RF-07 — Projetos

O sistema deve permitir que tarefas relacionadas à Programação sejam organizadas por projetos.

A estrutura deverá suportar o cenário atual em que existem múltiplos projetos dentro da categoria Programação.

---

## RF-08 — Issues/Tarefas de projetos

Um projeto deve poder possuir issues ou tarefas a serem realizadas.

Essas issues poderão servir como origem para os próximos passos de execução.

A quantidade de issues por projeto não deverá ser limitada pela estrutura do produto.

---

## RF-09 — Categoria ativa ou finalizada

O sistema deve permitir identificar se uma categoria está ativa ou finalizada.

Uma categoria finalizada não deve ser apagada automaticamente.

Ela deverá permanecer registrada para preservar seu histórico e permitir eventual reativação.

---

## RF-10 — Seleção das categorias do dia

O sistema deve determinar quais categorias podem participar da rotina do dia considerando suas configurações.

Para que uma categoria seja apresentada na rotina, deverá existir uma condição válida para sua participação e uma tarefa aberta disponível.

---

## RF-11 — Ocultação de categorias sem tarefa

Uma categoria prevista para determinado dia, mas sem tarefas em aberto, não deverá ser apresentada como uma atividade disponível naquele dia.

---

## RF-12 — Conversa como entrada

O sistema deve permitir que o usuário forneça informações por meio da conversa.

O usuário poderá informar, por exemplo:

* categoria desejada;
* projeto;
* tarefa;
* intenção de realizar uma atividade;
* contexto atual;
* intenção de criar uma nova tarefa.

---

## RF-13 — Interpretação sem IA

No MVP, a interpretação das mensagens deverá funcionar sem depender de inteligência artificial generativa.

O sistema deverá utilizar mecanismos determinísticos, como:

* palavras-chave;
* regras;
* correspondências com categorias;
* correspondências com projetos;
* correspondências com tarefas;
* identificação de intenções previamente definidas.

---

## RF-14 — Identificação de contexto

O sistema deve ser capaz de utilizar informações fornecidas pelo usuário durante a conversa para auxiliar na escolha do próximo passo.

O contexto deverá atuar como informação para decisão, não como mecanismo de controle do usuário.

---

## RF-15 — Check-in

O sistema deve possuir um check-in simples para identificar o contexto atual do usuário.

O check-in inicial não deverá exigir escalas complexas ou avaliações numéricas de estado.

A evolução do check-in será definida posteriormente.

---

## RF-16 — Identificação do próximo passo

O sistema deve ser capaz de selecionar um próximo passo a partir das informações disponíveis.

A decisão deverá considerar, progressivamente:

* categorias disponíveis;
* frequência;
* tarefas em aberto;
* histórico;
* contexto informado;
* tempo disponível;
* demais regras definidas para o Planner.

As regras de prioridade serão especificadas separadamente.

---

## RF-17 — Um próximo passo principal

O sistema deve apresentar um **próximo passo principal por vez**.

O objetivo é reduzir excesso de opções e facilitar o início da execução.

---

## RF-18 — Alternativas

O sistema deve poder oferecer alternativas ao próximo passo principal.

Uma alternativa poderá:

* pertencer à mesma categoria;
* pertencer a outra categoria.

---

## RF-19 — Rejeição da sugestão

O usuário deve poder rejeitar o próximo passo sugerido.

Ao rejeitar, o sistema deverá poder apresentar outra alternativa disponível.

A rejeição não deverá ser registrada como falha do usuário.

---

## RF-20 — Autonomia na escolha

O sistema deve permitir que o usuário escolha entre as opções apresentadas.

Uma recomendação do sistema não deve impedir que o usuário escolha outro próximo passo disponível.

---

## RF-21 — Execução da tarefa

O sistema deve permitir que o usuário inicie a execução do próximo passo escolhido.

A interface e os estados detalhados da execução serão especificados posteriormente.

---

## RF-22 — Registro do resultado

O sistema deve permitir registrar o resultado da execução.

O resultado deverá suportar, no mínimo, os conceitos:

* concluído;
* parcialmente concluído;
* postergado.

Os estados definitivos e suas transições serão definidos em `task-states.md`.

---

## RF-23 — Retomada

O sistema deve permitir registrar que uma atividade foi retomada após uma interrupção ou adiamento.

A retomada deverá fazer parte do histórico de execução.

---

## RF-24 — Histórico

O sistema deve manter um histórico das ações relevantes realizadas pelo usuário.

O histórico deverá permitir identificar, progressivamente:

* atividades realizadas;
* atividades parcialmente realizadas;
* atividades postergadas;
* atividades retomadas;
* categorias utilizadas;
* tempo de execução, quando registrado.

---

## RF-25 — Registro de duração

O sistema deverá permitir registrar a duração real de uma atividade.

A forma e o momento desse registro ainda serão definidos.

---

## RF-26 — Registro de dificuldade

O sistema deverá poder registrar a dificuldade percebida pelo usuário após uma atividade.

Esse dado será utilizado futuramente para análise do histórico e possível adaptação das recomendações.

---

## RF-27 — Dados históricos para análise

O sistema deverá armazenar informações suficientes para permitir análises futuras sobre:

* frequência de atividades por categoria;
* tempo dedicado;
* atividades concluídas;
* atividades parcialmente concluídas;
* atividades postergadas;
* horários de execução;
* retomadas.

---

## RF-28 — Visualização da atividade semanal

O sistema deverá oferecer uma visualização que permita observar a atividade do usuário ao longo da semana.

A visualização deverá utilizar dados registrados pelo sistema.

---

## RF-29 — Ausência de pontuação

O sistema não deve utilizar pontuação de produtividade como mecanismo central do produto.

Os dados apresentados deverão representar acontecimentos e padrões registrados, e não uma avaliação da pessoa.

---

## RF-30 — Criação de tarefa durante a conversa

O sistema deverá permitir que o usuário indique durante a conversa que deseja realizar uma nova atividade.

A interação poderá resultar na criação de uma nova tarefa.

A forma detalhada dessa criação será especificada posteriormente no fluxo de tarefas e conversa.

---

# 3. Requisitos relacionados ao tempo

## RF-31 — Duração variável por categoria

O sistema não deve assumir uma duração única para todas as categorias.

Uma atividade de Inglês, LinkedIn ou Calistenia poderá possuir uma duração diferente de uma atividade de Programação.

---

## RF-32 — Programação com duração diferenciada

O sistema deverá suportar atividades de Programação que exijam períodos maiores de execução.

A duração não deverá ser limitada à faixa inicialmente utilizada para atividades curtas.

---

## RF-33 — Tempo disponível

O tempo disponível informado pelo usuário poderá ser considerado na seleção do próximo passo.

A regra exata de como esse dado afetará a recomendação será definida posteriormente.

---

# 4. Requisitos de continuidade e adaptação

## RF-34 — Consideração do histórico

O sistema deverá poder utilizar o histórico para auxiliar na escolha do próximo passo.

Um dos objetivos é evitar que uma categoria seja continuamente ignorada quando existem tarefas disponíveis.

---

## RF-35 — Sugestão de categoria menos utilizada

O sistema poderá apresentar uma categoria menos utilizada como alternativa ou próximo passo.

Essa regra deverá preservar a possibilidade de rejeição pelo usuário.

---

## RF-36 — Contexto como fator de adaptação

O sistema deverá poder adaptar a recomendação de acordo com o contexto informado pelo usuário.

Exemplo:

> "Estou cansado, mas quero fazer alguma coisa."

A forma de transformar esse contexto em uma recomendação será definida posteriormente.

---

# 5. Requisitos de arquitetura do produto

## RNF-01 — Funcionamento sem IA

O MVP deve funcionar sem depender de um modelo de inteligência artificial generativa.

---

## RNF-02 — Evolução arquitetural

A arquitetura deve permitir evolução futura para mecanismos de maior complexidade, incluindo LangGraph, sem exigir que essa tecnologia seja utilizada no MVP.

---

## RNF-03 — Persistência

As informações necessárias para continuidade e histórico devem ser persistidas.

---

## RNF-04 — Dados reais

As visualizações e análises devem utilizar dados efetivamente registrados pelo sistema.

Não devem depender de dados fictícios para representar o funcionamento normal do produto.

---

## RNF-05 — Separação entre dados e interpretação

O sistema deve ser capaz de distinguir:

* acontecimentos registrados;
* interpretações ou análises futuras realizadas pelo sistema.

Essa separação será importante para a evolução da inteligência contextual.

---

## RNF-06 — Autonomia

O funcionamento do sistema deve preservar a capacidade do usuário de aceitar, rejeitar ou escolher alternativas às recomendações.

---

# 6. Requisitos de UX

## RNF-07 — Conversa como experiência principal

A conversa deve ser uma das principais formas de interação do usuário com o sistema.

---

## RNF-08 — Clareza do próximo passo

O próximo passo apresentado deve ser compreensível e suficientemente concreto para que o usuário saiba o que fazer.

---

## RNF-09 — Baixa carga de decisão

O sistema deve evitar apresentar uma quantidade excessiva de ações simultaneamente.

O foco deve permanecer em um próximo passo principal.

---

## RNF-10 — Continuidade

O usuário deve conseguir retornar ao fluxo após interrupções, adiamentos ou atividades parcialmente concluídas.

---

# 7. Requisitos que NÃO devem ser implementados como premissa do MVP

Não fazem parte dos requisitos obrigatórios iniciais:

* IA generativa;
* LangGraph;
* sistema de pontuação;
* diagnóstico psicológico;
* escalas complexas de energia, humor ou ansiedade;
* análise científica automatizada do estado do usuário;
* recomendação totalmente autônoma;
* classificação do usuário por produtividade.

Esses elementos podem ser estudados posteriormente quando houver justificativa.

---

# 8. Requisitos ainda dependentes de decisões futuras

Os seguintes pontos foram identificados, mas ainda não possuem especificação definitiva:

### Categorias

* campos completos do cadastro;
* formato da frequência;
* programação por dia;
* detalhes da reativação;
* lista futura de categorias.

### Projetos e tarefas

* campos de Projeto;
* campos de Issue/Tarefa;
* relação exata entre Issue e próximo passo;
* criação de tarefas via conversa.

### Conversa

* conjunto de palavras-chave;
* intenções reconhecidas;
* tratamento de ambiguidades;
* perguntas de esclarecimento;
* regras para criação de tarefas.

### Planner

* prioridade entre categorias;
* peso da frequência;
* peso do histórico;
* escolha entre tarefas;
* escolha entre categorias;
* regras para rejeição;
* uso do tempo disponível.

### Execução

* estados definitivos;
* transições;
* registro de duração;
* registro de dificuldade;
* registro de conclusão parcial;
* registro de adiamento;
* registro de retomada.

Esses pontos não devem ser considerados indefinidos por erro de documentação. Eles estão deliberadamente reservados para os documentos específicos.

---

# 9. Fluxo funcional mínimo

O comportamento mínimo esperado do produto pode ser representado como:

```text
Categorias / tarefas disponíveis para hoje
                    ↓
             Início da conversa
                    ↓
          Identificação do contexto
                    ↓
          Análise das opções disponíveis
                    ↓
          Sugestão do próximo passo
                    ↓
        Usuário aceita ou rejeita
              ↓             ↓
           Aceita        Rejeita
              ↓             ↓
          Executa       Nova opção
              ↓
       Registra resultado
              ↓
        Atualiza histórico
              ↓
         Próximo passo
```

---

# 10. Critério geral dos requisitos

O MVP estará alinhado aos requisitos quando conseguir realizar o ciclo fundamental:

> **identificar o que está disponível → compreender o contexto necessário → sugerir um próximo passo concreto → permitir a decisão do usuário → registrar o resultado → preservar o histórico.**

Os detalhes necessários para tornar esse ciclo determinístico serão definidos nos documentos de domínio, UX, dados e arquitetura.
