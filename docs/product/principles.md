# Meu Próximo Passo

# Princípios do Produto

## 1. Próximo passo > lista infinita

O sistema deve ajudar o usuário a identificar **uma ação principal para o momento atual**, em vez de aumentar a quantidade de tarefas apresentadas.

O usuário poderá possuir várias tarefas e objetivos, mas o sistema trabalha com **um próximo passo por vez**.

Isso não significa esconder as demais possibilidades.

O sistema pode apresentar alternativas quando necessário, mas deve evitar transformar a experiência em uma nova lista de cobrança.

### Regra

> O sistema recomenda um próximo passo principal, mantendo alternativas disponíveis para o usuário.

---

## 2. Autonomia > controle

O sistema existe para apoiar a decisão do usuário, não para decidir por ele.

Uma recomendação não é uma ordem.

O usuário pode:

* aceitar;
* rejeitar;
* escolher outra tarefa;
* escolher outra tarefa da mesma categoria;
* escolher uma tarefa de outra categoria;
* ajustar o que pretende fazer.

A decisão final permanece com o usuário.

### Regra

> Toda recomendação do sistema deve preservar a possibilidade de escolha do usuário.

---

## 3. Pequeno > perfeito

O sistema deve favorecer ações que possam ser iniciadas e executadas, mesmo quando não representam a execução ideal.

O objetivo não é produzir o planejamento perfeito.

O objetivo é reduzir a distância entre intenção e execução.

Uma atividade pode começar pequena e posteriormente ser ampliada.

### Regra

> Quando houver dúvida entre uma ação ideal difícil de iniciar e uma ação menor que permita começar, o sistema deve considerar a alternativa menor.

Os parâmetros exatos de duração serão definidos posteriormente no domínio do produto.

---

## 4. Adaptar > cobrar

O planejamento inicial não deve ser tratado como uma obrigação imutável.

As condições do usuário podem mudar.

O sistema deve utilizar as informações disponíveis para adaptar a sugestão, quando necessário.

Exemplo conceitual:

```text
Planejamento original
        ↓
Contexto atual
        ↓
Nova avaliação
        ↓
Próximo passo possível
```

Uma mudança de plano não representa necessariamente falha.

Pode representar uma adaptação adequada ao contexto.

### Regra

> Quando o contexto tornar o próximo passo original inadequado, o sistema deve buscar uma alternativa executável em vez de aumentar a cobrança.

---

## 5. Retomar > punir

Não realizar uma tarefa não deve encerrar a relação do usuário com o sistema.

Uma tarefa adiada ou não concluída representa um acontecimento que pode ser registrado e utilizado para decisões futuras.

O sistema deve facilitar a retomada.

A ausência de execução não deve gerar mensagens que culpabilizem ou constranjam o usuário.

### Regra

> O sistema registra o que aconteceu e utiliza essa informação para o próximo ciclo, sem transformar o não cumprimento em punição.

---

## 6. Histórico > memória vaga

O sistema deve registrar acontecimentos relevantes para que o usuário não dependa apenas da memória para entender seu próprio processo.

O histórico deverá permitir, ao longo da evolução do produto, observar padrões como:

* tarefas realizadas;
* tarefas adiadas;
* tarefas parcialmente realizadas;
* retomadas;
* tempo dedicado;
* distribuição das atividades;
* períodos de maior atividade.

Esses dados devem representar o processo real do usuário.

### Regra

> Decisões futuras poderão utilizar fatos registrados no histórico, e não apenas informações do momento atual.

---

## 7. Dados > julgamento

Os dados registrados pelo sistema devem servir para compreender o comportamento do processo, e não para atribuir um valor ao usuário.

O sistema não deve transformar produtividade em uma nota pessoal.

Por isso, indicadores devem responder perguntas como:

> “O que aconteceu?”

e não:

> “Quão bom você foi?”

Os dados devem ajudar o usuário a perceber padrões e tomar decisões.

### Regra

> O sistema apresenta dados sobre comportamento e execução sem transformar esses dados em uma avaliação da pessoa.

---

## 8. Contexto > automatismo

Uma mesma tarefa pode ser adequada em um momento e inadequada em outro.

Por isso, uma recomendação não deve depender exclusivamente da lista de tarefas.

O contexto informado pelo usuário poderá futuramente influenciar a escolha do próximo passo.

O sistema deverá evoluir para compreender melhor situações como:

* disposição para realizar uma tarefa;
* falta de tempo;
* interrupções;
* dificuldade percebida;
* necessidade de reduzir o tamanho da atividade.

Essa evolução deverá ser baseada em regras e evidências adequadas, e não em julgamentos arbitrários.

### Regra

> O contexto pode modificar a recomendação, mas não deve retirar a autonomia do usuário.

---

## 9. Recuperação > perfeição do planejamento

O sistema deve considerar que um planejamento real possui interrupções, mudanças e dias diferentes.

O sucesso do produto não depende de um planejamento ser seguido perfeitamente.

Uma parte importante da experiência será permitir:

```text
Planejar
   ↓
Executar
   ↓
Interromper
   ↓
Registrar
   ↓
Retomar
```

A capacidade de voltar ao processo é parte importante do produto.

### Regra

> Uma interrupção deve poder fazer parte do fluxo normal do sistema, sem representar o fim do planejamento.

---

# 10. Princípio arquitetural

A tecnologia deve servir ao produto.

O sistema não deve utilizar inteligência artificial ou uma arquitetura complexa apenas porque essas tecnologias estão disponíveis.

O MVP deverá validar primeiro:

* problema;
* experiência;
* fluxo;
* regras;
* dados;
* comportamento do usuário.

Somente depois devem ser introduzidas tecnologias adicionais quando houver uma necessidade clara.

Isso inclui a evolução planejada para LangGraph.

### Regra

> Primeiro definimos o problema e o fluxo; depois escolhemos a tecnologia necessária para resolvê-los.

---

# 11. Princípio de evolução

As decisões do MVP não precisam antecipar todo o produto futuro.

O sistema deverá ser construído de maneira que novas capacidades possam ser adicionadas quando houver evidência de que são necessárias.

A evolução poderá incluir:

* novas categorias;
* novas formas de entrada;
* análise de padrões;
* adaptação contextual;
* inteligência baseada em histórico;
* novos indicadores;
* LangGraph;
* recursos de IA.

### Regra

> Não devemos construir hoje aquilo que ainda não precisamos, mas devemos evitar decisões que impeçam a evolução amanhã.

---

# 12. Resumo dos princípios

```text
PRÓXIMO PASSO
       ↓
AUTONOMIA
       ↓
PEQUENO
       ↓
ADAPTAÇÃO
       ↓
RETOMADA
       ↓
HISTÓRICO
       ↓
DADOS SEM JULGAMENTO
       ↓
CONTEXTO
       ↓
EVOLUÇÃO
```

O princípio central que conecta todos os demais é:

> **O sistema deve ajudar a pessoa a recuperar o controle da próxima ação, sem transformar o processo em cobrança.**
