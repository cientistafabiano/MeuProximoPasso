# Meu Próximo Passo

## Problema do Produto

### 1. Problema central

Saber o que precisa ser feito não significa necessariamente conseguir começar.

Uma pessoa pode possuir objetivos claros, tarefas definidas e intenção de realizar essas atividades, mas ainda assim encontrar dificuldade para transformar o planejamento em uma ação concreta.

Quando existem vários objetivos simultaneamente, o planejamento pode se transformar em uma lista extensa de cobranças.

Nesse cenário, o problema não é necessariamente falta de objetivos.

O problema pode estar na distância entre:

**“Eu sei o que preciso fazer.”**

e

**“Eu sei exatamente o que posso fazer agora.”**

O Meu Próximo Passo nasce para reduzir essa distância.

---

## 2. O problema da lista infinita

Uma lista tradicional pode apresentar várias tarefas ao mesmo tempo:

```text
Programação
Inglês
Calistenia
LinkedIn
...
```

Embora a lista organize as atividades, ela não necessariamente responde à pergunta mais importante:

> **Qual delas deve ser o próximo passo?**

Quanto maior a quantidade de tarefas, maior pode ser a sensação de que tudo precisa ser resolvido simultaneamente.

O sistema deve trabalhar com a ideia de reduzir esse excesso de decisão.

Em vez de apresentar apenas uma lista, deve ajudar a identificar uma ação concreta para o momento atual.

---

## 3. O problema da tarefa abstrata

Algumas tarefas são grandes ou vagas demais para representar uma ação imediata.

Exemplo:

> “Estudar programação.”

Essa definição não informa necessariamente:

* o que abrir;
* onde começar;
* o que fazer primeiro;
* quanto tempo dedicar;
* quando considerar aquela sessão concluída.

O sistema deve transformar uma intenção ampla em um próximo passo executável.

Exemplo:

> **Abrir o projeto Soberana e trabalhar durante 20 minutos na próxima tarefa definida.**

A diferença fundamental é transformar:

**intenção → ação**

---

## 4. O problema do planejamento rígido

Um planejamento pode parecer adequado no início do dia e deixar de ser adequado algumas horas depois.

O usuário pode:

* ter menos tempo disponível;
* estar cansado;
* precisar interromper uma atividade;
* não conseguir concluir uma tarefa;
* precisar adiar uma atividade;
* mudar a prioridade naquele momento.

O sistema não deve considerar o planejamento original como algo imutável.

Quando uma tarefa não puder ser realizada como planejada, o sistema deverá permitir que o ciclo seja adaptado.

A tarefa pode ser reduzida, parcialmente executada, adiada ou retomada posteriormente.

---

## 5. O problema de interpretar o não cumprimento como fracasso

Não realizar uma tarefa não significa necessariamente que o planejamento perdeu seu valor.

Uma tarefa não concluída também gera informação.

Por isso, o sistema deverá registrar diferentes resultados:

```text
Concluída
Parcialmente concluída
Adiada
Retomada posteriormente
```

O objetivo do registro não é punir o usuário.

É compreender o que aconteceu e utilizar essa informação nos próximos ciclos.

---

## 6. O problema da perda de contexto

Quando o histórico não é registrado, cada novo dia começa praticamente do zero.

O usuário pode não lembrar:

* o que realizou;
* o que adiou;
* o que interrompeu;
* onde parou;
* quando retomou;
* quanto tempo realmente dedicou a determinada atividade.

O sistema deve construir um histórico que permita recuperar esse contexto.

Assim, o passado deixa de ser apenas memória e passa a ser informação disponível para decisões futuras.

---

## 7. O problema da retomada

Um dos aspectos importantes do produto é reconhecer que interrupções fazem parte do processo.

O sistema deve conseguir registrar situações como:

```text
Planejado
   ↓
Iniciado
   ↓
Interrompido
   ↓
Não concluído
   ↓
Retomado
```

A retomada não deve ser tratada apenas como uma consequência secundária.

Ela representa uma informação importante sobre o comportamento de execução.

Por isso, o sistema deverá acompanhar quantas vezes o usuário consegue retornar a uma atividade depois de uma interrupção ou adiamento.

---

## 8. O problema da decisão diária

O usuário pode ter objetivos de médio e longo prazo, mas precisa tomar decisões em períodos muito menores.

Existe uma diferença entre:

> “Quero melhorar minha programação.”

e:

> “O que devo fazer durante os próximos 20 minutos?”

O Meu Próximo Passo deve atuar justamente nesse intervalo.

O sistema utiliza o planejamento maior como contexto, mas busca produzir uma decisão pequena e executável.

---

## 9. O problema que o DSS pretende resolver

O problema pode ser resumido como:

> **Como transformar objetivos e tarefas em um próximo passo concreto, considerando o contexto atual e o histórico de execução do usuário?**

O sistema deverá apoiar essa decisão utilizando informações como:

* objetivos;
* tarefas disponíveis;
* tarefas realizadas;
* tarefas adiadas;
* histórico;
* tempo disponível;
* contexto informado pelo usuário.

A decisão final continua pertencendo ao usuário.

---

## 10. O que não faz parte do problema

O Meu Próximo Passo não pretende resolver:

* todos os aspectos da vida do usuário;
* produtividade de forma absoluta;
* desempenho pessoal por meio de uma pontuação;
* diagnóstico psicológico ou médico;
* tomada automática de decisões pessoais;
* obrigação de cumprir todas as tarefas planejadas.

O sistema deve apoiar a decisão sobre o próximo passo, não assumir o controle da vida do usuário.

---

## 11. Formulação resumida

### Problema

O usuário possui objetivos e tarefas, mas pode ter dificuldade para transformar o planejamento em uma ação pequena, concreta e executável.

### Consequência

O planejamento pode gerar excesso de tarefas, indecisão, adiamentos e dificuldade de retomada.

### Oportunidade

Criar um DSS pessoal capaz de utilizar contexto e histórico para ajudar o usuário a identificar um próximo passo possível.

### Resultado esperado

Reduzir a distância entre:

**“Preciso fazer isso.”**

e

**“Sei exatamente o que vou fazer agora.”**

---

## 12. Hipótese do produto

A hipótese inicial é:

> **Se o sistema conseguir transformar objetivos e tarefas em próximos passos pequenos, concretos e adaptáveis ao contexto atual, o usuário terá uma experiência mais clara para iniciar, executar e retomar suas atividades.**

Essa hipótese deverá ser validada pelo MVP.

O MVP não precisa provar que o sistema melhora a vida do usuário inteira.

Precisa verificar se ele consegue cumprir sua função fundamental:

> **ajudar o usuário a identificar e executar o próximo passo possível.**
