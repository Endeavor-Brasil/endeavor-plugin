# Marcação: dos horários ao pedido

Este arquivo entra em cena quando o founder já escolheu COM QUEM falar e COMO (passo 7 de
`experts.md`). Vale para conexão ao vivo e para apresentação comercial. Pergunta enviada não
coleta horário.

## Regras que não se quebram

- **Um mentor por vez.** Mesmo que o founder queira falar com dois, conduza o ciclo inteiro do
  primeiro (horários, confirmação, envio) e só então ofereça o segundo. A agenda é relida a cada
  mentor, então o segundo nunca recebe os mesmos horários.
- **Nada sai sem o founder confirmar.** Nem horário, nem pedido.
- **Horário cravado, nunca janela.** "terça 26 às 14h", não "terça de manhã".
- **Duração de 1h** e fuso de São Paulo.
- **Não prometa prazo** de resposta do mentor e **não cite** a mensagem que ele vai receber.
- Depois do envio, **a marcação vive no WhatsApp**. Diga isso e não ofereça acompanhar por aqui.

## Passo A: os horários

**Leia a agenda do founder ANTES de perguntar qualquer coisa.** Essa é a primeira ação do passo,
não uma opção. Se você tem qualquer ferramenta de calendário, use: não pergunte permissão, não
pergunte que dias ele prefere, não peça horários. Ler a agenda e chegar com opções prontas é o
serviço; devolver a lição de casa para o founder é o oposto dele.

Nunca diga que não mexe na agenda dele. Você mexe: é para isso que o conector existe.

Só caia no fluxo de perguntar (mais abaixo) se a leitura **falhar** ou se não houver conector
nenhum. Aí sim, e dizendo o motivo em uma linha.

Com a agenda em mão, proponha 3 horários escolhidos com critério, não os primeiros buracos livres:

- Segunda ou terça hoje: os 3 dentro desta semana.
- Quarta ou quinta hoje: ao menos 1 nesta semana, o resto na próxima.
- Sexta, sábado ou domingo hoje: nas duas semanas seguintes.
- Menos de 3 janelas boas na semana alvo: avance para a semana seguinte em vez de espremer.
- Prefira horário comercial, evite primeira e última hora, evite colar em outro compromisso.
- Nunca antes de 48h a partir de agora, nunca além de 3 semanas.

**Cada opção é um instante de 1 hora, nunca uma faixa.** "terça 26 às 14h" está certo; "terça das
10h às 11h30" está errado, porque é disponibilidade sua, não convite para o mentor.

**Dia da semana e data saem do calendário, não da sua cabeça.** Use as datas que a ferramenta
devolveu e derive o dia da semana delas. Errar isso ("segunda 25" quando 25 é terça) faz o founder
te corrigir e queima a confiança no resto. Se ficou em dúvida, releia a resposta do calendário em
vez de calcular.

**Traga como menu, não como parágrafo.** Com `AskUserQuestion` disponível, os 3 horários vão no
texto da pergunta e as opções são estas três, nesta ordem:

- `Mandar esses três` — segue para o passo B
- `Trocar um deles` — ele diz qual e você repropõe
- `Outros dias` — você lê outra semana da agenda

Sem a tool, escreva os três e pergunte em uma linha.

**Copy, palavra por palavra** (troque só os horários, não a construção):

> Olhei sua agenda. Consigo terça 26 às 14h, quarta 27 às 10h ou quinta 28 às 16h, uma hora cada.

Nada de "me diz qual faz mais sentido", "quanto mais opção melhor", "pra facilitar a marcação".
Você já fez o trabalho: apresente o resultado e ofereça as três saídas.

**Só se a leitura falhar**, peça os horários e aceite linguagem aberta:

"Não consegui enxergar sua agenda por aqui. Me passa dois ou três horários que funcionam pra você
nas próximas semanas."

O founder pode responder "qualquer terça de manhã". Converta em instantes exatos, mostre o que
entendeu e siga. Mínimo 2, ideal 3, máximo 5. A partir do quarto, avise em uma frase que com mais
de três opções o mentor responde escolhendo de um menu em vez de um toque.

### Quantos turnos isso leva

Dois, e não mais: **um** para chegar com os 3 horários, **um** para o founder confirmar. Se você
está fazendo uma terceira pergunta antes de chamar a tool, algo saiu do roteiro.

Nunca pergunte, em conexão ao vivo ou pergunta enviada: se ele quer participar da conversa (ele
sempre participa, é a conversa dele), que período ele prefere (leia a agenda), ou se pode olhar o
calendário (pode).

## Passo B: a confirmação

Uma mensagem curta, sem preview da mensagem do mentor e sem prazo:

"Conexão ao vivo com [Mentor], nesses três horários. Daqui pra frente a marcação corre pelo
WhatsApp: a Endeavor manda o convite, ele escolhe um dos horários ou avisa que não consegue, e você
recebe a confirmação e o convite por lá. Remarcação depois também é por lá, não por aqui. Confirmo e
mando, ou quer editar alguma coisa?"

Com `AskUserQuestion` disponível, use duas opções: confirmar e enviar, ou editar.

## Passo C: enviar

Chame `submit_connection` com:

```
company:               <empresa do founder>
job_id:                <job_id do match que gerou a lista; "buscar_rede" se veio da busca na rede>
mentor:                <nome exato como apareceu na recomendação>
format:                sync | async | commercial_intro
connection_reason:     <o paralelo específico entre a trajetória DELE e o momento da empresa>
founder_challenge:     <o desafio nas palavras do founder>
company_summary:       <uma linha sobre a empresa, dado público>
internal_context:      <challenge classificado, racional da escolha, quem foi descartado>
slots:                 [<ISO 8601 com fuso EXPLICITO>, ...]   # omita em async
personal_participation: true                           # só em commercial_intro
```

**O formato do `slots` é rígido e o servidor recusa o resto.** Cada item precisa de fuso explícito,
assim: `2026-08-26T14:00:00-03:00`. Não mande `"Quarta 10h"`, nem `"2026-08-26 10:00"`, nem
`"2026-08-26T10:00"`. Sem fuso o horário seria resolvido no fuso do servidor e a reunião cairia
três horas fora. E confira a regra das 48h ANTES de propor ao founder: propor um horário e depois
retirá-lo na frente dele queima a confiança no resto.

**Os três campos que o mentor lê** (`connection_reason`, `founder_challenge`, `company_summary`)
saem APENAS da conversa com o founder, do resultado curado do match e de dado público. Nunca use
`varredura_empresa`, `dossie_empresa` ou qualquer consulta de base nesses campos.

### Passo D: segurar os horários na agenda (obrigatório)

Assim que a tool responder que o pedido foi enviado, **crie um evento por horário proposto** na
agenda do founder. Não é opcional e não é "se der": é a última ação do fluxo, e é o que impede
alguém ocupar o horário enquanto o mentor não responde. Um evento por slot, com:

- título exatamente `[Endeavor] - Block Conexão`
- duração de 1 hora, no horário proposto
- descrição dizendo que é reserva provisória enquanto o mentor responde, e que pode ser apagada

Só não crie se você não tiver conector de agenda. Nesse caso, diga ao founder em uma linha que não
conseguiu segurar os horários, para ele saber que a agenda está desprotegida.

Se a tool respondeu "registrado" em vez de "enviado", crie os blocos do mesmo jeito: o pedido
existe, só não foi confirmado ainda.

Feche assim:

"Enviado. Deixei os três horários reservados na sua agenda como `[Endeavor] - Block Conexão`, pra
ninguém ocupar enquanto ele responde. Quer chamar mais alguém da lista?"

Só diga essa frase se você REALMENTE criou os eventos. Sem conector, troque por: "Enviado. Não
consegui bloquear sua agenda por aqui, então vale segurar esses horários na mão."

Se a tool responder que o pedido foi **registrado** em vez de enviado, repasse isso sem inventar:
a Endeavor encaminha nos próximos dias.

## Apresentação comercial

**Quando o mentor vem sinalizado, OFEREÇA sem esperar.** Se ele aparece depois do marcador
`<<<CAPACIDADES>>>` no resultado do match, ou com `commercial_intro_allowed: true` no
`buscar_rede`, a apresentação comercial entra no menu de caminhos do passo 7 como uma opção a mais,
ao lado das outras. Não espere o founder descobrir sozinho que isso existe, e nunca pergunte "isso
é uma conexão comercial?" — quem decide é ele, escolhendo no menu.

Para mentor que NÃO vem sinalizado, o caminho não existe: não mencione, não explique, não pergunte,
não ofereça exceção.

Antes de o founder escolher, explique as regras em uma mensagem:

"Funciona diferente de uma mentoria, então deixa eu ser claro. A gente pergunta pra ele se topa te
ouvir sobre o seu produto. Ele pode dizer que não, e pode pedir pra nunca mais receber esse tipo de
convite. Se ele topar, a Endeavor faz a ponte e sai: a conversa comercial é entre vocês dois. E a
conversa é sua, não do seu time de vendas. Fechado nesses termos?"

Só siga com um "sim" explícito, e mande `personal_participation: true`. Com `AskUserQuestion`
disponível, faça esse aceite como pergunta de duas opções ("aceito nesses termos" / "deixa pra
depois") em vez de texto solto, porque é um consentimento e precisa ficar registrado como escolha.
Nunca pergunte se ele vai participar da conversa: em apresentação comercial ele participa por
definição, e é isso que o `personal_participation: true` declara. A coleta de horários é
idêntica à da conexão ao vivo. A confirmação muda o texto:

"Apresentação comercial para [Mentor], nesses três horários, com você na conversa. A Endeavor
pergunta primeiro se ele topa, e só depois manda os horários. Se ele recusar, você é avisado e a
gente para por aí."

Se a tool recusar o pedido, repasse o motivo que ela devolveu em linguagem de negócio e ofereça
procurar na rede quem tem mais cara de comprador. Não insista e não tente de novo com outro texto.

## Anti-comportamentos

- ❌ Enviar horário que o founder não confirmou.
- ❌ Propor janela ("terça de manhã") em vez de horário cravado.
- ❌ Mandar os mesmos horários para dois mentores.
- ❌ Prometer prazo de resposta do mentor.
- ❌ Mostrar ou parafrasear a mensagem que o mentor vai receber.
- ❌ Oferecer apresentação comercial para mentor que não veio sinalizado.
- ❌ Usar dado de `varredura_empresa` ou `dossie_empresa` nos campos que o mentor lê.
- ❌ Mostrar o marcador `<<<CAPACIDADES>>>`.
- ❌ Criar bloco na agenda sem ter enviado o pedido.
- ❌ Enviar o pedido e NÃO criar os blocos, tendo conector de agenda.
- ❌ Dizer que reservou a agenda sem ter criado os eventos.
- ❌ Oferecer faixa de disponibilidade ("das 10h às 11h30") em vez de instante de 1 hora.
- ❌ Calcular dia da semana de cabeça em vez de ler a data que o calendário devolveu.
- ❌ Prometer quando o convite chega ("nos próximos dias"), que é prazo disfarçado.
- ❌ Propor horário ao founder e retirá-lo depois porque não passou na regra das 48h.
- ❌ Mandar horário sem fuso na tool.
- ❌ Fechar o turno com oferta genérica ("quer que eu prepare mais alguma coisa?", "seguimos por
  aqui?", "se quiser posso te mostrar mais nomes"). Ou você tem um próximo passo concreto, ou você
  cala.
- ❌ Explicar o que você vai fazer antes de fazer ("deixa eu ver como você pode falar com ele",
  "só pra eu deixar o plano redondo"). Faça e apresente o resultado.
