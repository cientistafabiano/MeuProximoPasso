# Meu Próximo Passo — Regras de Conversação

## 1. Objetivo deste documento

Este documento define como o sistema interpreta as mensagens do usuário **sem inteligência artificial** no MVP (RF-13, RNF-01).

Ele cobre: o que o sistema reconhece, como decide o que a mensagem quer dizer, o que fazer quando não entende e como se comporta quando o usuário não conversa.

O fluxo visual da conversa (telas, botões, ordem das mensagens) fica em `ux/chat-flow.md`.

Itens marcados como **(proposta)** precisam de confirmação do autor.

---

## 2. Princípio

> **A conversa contextualiza; o Planner decide depois.**

O usuário indica o que quer e como está. Só então o Planner escolhe o próximo passo, respeitando o que foi dito.

```text
Mensagem do usuário
        ↓
Normalização
        ↓
Reconhecimento de entidades
        ↓
Reconhecimento de intenção
        ↓
   Entendeu?
   ↓        ↓
  Sim      Não / ambíguo
   ↓        ↓
Contexto   Pergunta de esclarecimento
   ↓
Planner
   ↓
Sugestão
```

---

## 3. Botões antes de texto livre **(proposta)**

Ações com resposta fechada usam **botões**, não interpretação de texto:

* aceitar / rejeitar sugestão;
* escolher uma alternativa;
* registrar resultado (concluída / parcial / adiada);
* responder perguntas de esclarecimento.

O texto livre fica para o que é aberto: intenção, contexto, criação de tarefa.

Motivo: cada ação resolvida por botão é uma ambiguidade a menos para as regras tratarem. O texto livre continua aceito para essas ações (ex.: "bora"), mas o botão é o caminho principal.

---

## 4. Normalização

Antes de qualquer reconhecimento, a mensagem é normalizada:

* letras minúsculas;
* remoção de acentos ("inglês" → "ingles");
* remoção de pontuação;
* espaços múltiplos reduzidos.

As palavras-chave cadastradas passam pela mesma normalização. Assim, "Inglês", "ingles" e "INGLÊS!" são equivalentes.

---

## 5. Entidades reconhecidas

| Entidade | Como é reconhecida | Exemplos |
| --- | --- | --- |
| Categoria | Nome + palavras-chave cadastradas na categoria | "programação", "codar", "inglês", "treino", "calistenia" |
| Projeto | Nome + palavras-chave cadastradas no projeto | "soberana" |
| Issue | Número ou trecho do título | "issue 4", "tela de login" |
| Duração | Padrões de tempo | "20 min", "meia hora", "1h", "pouco tempo" |
| Disposição | Lista de termos de estado | "cansado", "sem energia", "animado", "bem" |
| Dia | Termos de tempo | "hoje", "amanhã", "depois" |

As listas de categoria, projeto e issue **vêm do cadastro do usuário** — não são fixas no código. Disposição, duração e dia são listas do sistema.

---

## 6. Intenções do MVP **(proposta)**

| Intenção | Exemplos | Resultado |
| --- | --- | --- |
| `PEDIR_SUGESTAO` | "o que eu faço agora?", "me dá um passo" | Planner sugere sem restrição |
| `ESCOLHER_CATEGORIA` | "hoje quero fazer programação", "algo de inglês" | Planner sugere dentro da categoria |
| `ESCOLHER_PROJETO` | "quero trabalhar no Soberana" | Planner sugere a próxima issue do projeto |
| `INFORMAR_CONTEXTO` | "estou cansado", "tô bem hoje" | Contexto registrado; Planner reavalia |
| `INFORMAR_TEMPO` | "tenho 30 min", "pouco tempo" | Tempo disponível registrado; Planner reavalia |
| `ACEITAR` | "bora", "sim", "vamos" | Execução iniciada |
| `REJEITAR` | "outra", "não", "agora não" | Nova sugestão (rejeição não altera a tarefa) |
| `REGISTRAR_RESULTADO` | "terminei", "fiz metade", "vou deixar pra amanhã" | Resultado registrado |
| `CRIAR_TAREFA` | "nova issue no Soberana: tela de cadastro" | Fluxo de criação (§10) |

Uma mensagem pode ter **mais de um elemento**. Ex.: "estou cansado mas quero fazer programação" → `INFORMAR_CONTEXTO` (cansado) + `ESCOLHER_CATEGORIA` (Programação).

---

## 7. Regras de interpretação

### 7.1 O mais específico vence

```text
Issue  >  Projeto  >  Categoria
```

"Quero mexer na tela de login do Soberana" → reconhece a issue; projeto e categoria são deduzidos dela.

### 7.2 A intenção explícita do usuário vence o contexto

"Estou cansado, mas quero programar" → a categoria escolhida é respeitada. O contexto pode **reduzir o tamanho** do próximo passo, mas não troca a categoria.

> Esta regra aplica o princípio Autonomia > controle: o contexto modifica a recomendação, não a decisão.

### 7.3 A escolha do usuário vence a frequência

Se o usuário pede uma categoria que não está prevista para hoje, ela é atendida, desde que tenha tarefa em aberto.

---

## 8. Quando o sistema não entende

| Situação | Comportamento |
| --- | --- |
| Nenhuma entidade ou intenção reconhecida | Pergunta com opções: as categorias do dia + "me sugira algo" |
| Mais de uma correspondência (ex.: dois projetos com nomes parecidos) | Lista os candidatos como botões |
| Categoria reconhecida sem tarefa em aberto | Informa e pergunta: adicionar tarefa ou escolher outra categoria |
| Categoria finalizada | Informa e pergunta se deseja reativar |

### Regras da pergunta de esclarecimento

* uma pergunta por vez;
* sempre com opções clicáveis;
* sempre com uma saída ("me sugira algo").

---

## 9. Quando o usuário não conversa

No MVP, sem mensagem do usuário, o sistema apresenta a sugestão principal ao abrir (CS-01) e aguarda.

Os comportamentos abaixo estão registrados como **evolução futura** (`roadmap/future-ideas.md`) e não fazem parte do MVP.

### 9.1 Sugestão proativa (FUT-01)

Se o sistema foi aberto e a conversa não foi iniciada, após **~15 minutos** o sistema apresenta uma sugestão com base na **hora do dia** e no **histórico**.

```text
Sistema aberto
      ↓
15 min sem mensagem
      ↓
Planner sugere usando hora do dia + histórico
      ↓
Mensagem curta, sem cobrança
```

**(proposta)** Nos primeiros dias, ainda sem histórico suficiente, a sugestão usa apenas a rotina do dia e a ordem do plano/backlog.

**(proposta)** A sugestão proativa acontece no máximo uma vez por abertura, para não virar insistência.

### 9.2 Lembrete por ausência (FUT-02)

O sistema pode avisar o usuário após um período sem entrar.

Pendente para quando entrar: intervalo e canal (notificação do navegador, e-mail, outro).

---

## 10. Criação de tarefa pela conversa

```text
"nova issue no Soberana: tela de cadastro"
        ↓
Projeto reconhecido: Soberana
Título reconhecido: tela de cadastro
        ↓
Faltou algo obrigatório?
   ↓              ↓
  Não            Sim → pergunta (ex.: "Em qual posição da ordem?")
   ↓
Confirmação com botões
   ↓
Tarefa criada e disponível para o Planner
```

**(proposta)** Toda criação passa por confirmação antes de gravar, porque uma interpretação errada criaria uma tarefa errada no backlog.

---

## 11. Linguagem das respostas

As respostas do sistema seguem `principles.md`.

| Evitar | Preferir |
| --- | --- |
| "Você não fez inglês ontem." | "Inglês está disponível hoje." |
| "Você está atrasado no LinkedIn." | "LinkedIn não aparece há alguns dias. Quer incluir hoje?" |
| "Tarefa falhou." | "Ficou para depois. Ela continua disponível." |
| "Você só fez 10 min." | "10 min de Programação registrados." |
| "Adiado 4 vezes." | Tag: "adiado em 05/10" |

No MVP as respostas são **modelos fixos com campos variáveis** (ex.: "{categoria} — {próximo passo} por {duração}").

Quando o próximo passo já foi adiado ou rejeitado antes, ele é exibido com a **tag de origem** (ver glossário e CS-15).

---

## 12. Evolução

O interpretador do MVP deve ter uma saída fixa:

```text
mensagem  →  { intenções, entidades, contexto, entendeu? }
```

Na evolução, uma LLM pode substituir ou complementar o interpretador **mantendo essa mesma saída**. O Planner e o restante do sistema não precisam mudar.

Esse ponto de troca também é um candidato natural a Node na Fase 1 (LangGraph).

---

## 13. Pendências

* lista inicial de termos de disposição e como cada um afeta a sugestão;
* palavras-chave iniciais de cada categoria;
* por quanto tempo um contexto informado vale (até o fim da sessão? do dia?);
* campos obrigatórios na criação de tarefa por conversa;
* textos das tags de origem.