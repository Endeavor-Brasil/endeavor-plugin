# Marcação: da agenda ao pedido de conexão

Entra em cena quando o founder já escolheu COM QUEM falar e escolheu **conexão ao vivo**. Vale
tanto para o match curado na wiki quanto para a busca na rede ampla, que desde 2026-09 são os
dois destinos do roteador do Bloco 1: o fim dos dois fluxos é o mesmo.

São cinco passos, nesta ordem, e no caminho feliz o founder responde em dois turnos: um para
confirmar os horários, um para autorizar o envio. Mostrar a caixa ou o cartão de novo depois de ele
trocar um horário, corrigir um fato ou pedir uma mudança de tom que você recusou não conta como
pergunta nova. Fora isso, se você está fazendo uma terceira pergunta, saiu do roteiro.

**Este fluxo tem exatamente três saídas: `agendar_conexao` chamada, o founder cancelando, ou o pedido
pendente porque ele pulou a pergunta (passos 2 e 3).** Não existe quarta. Depois que ele confirma os
horários, o próximo movimento é SEMPRE o resumo do passo 3, e depois do "enviar" é SEMPRE a chamada
da tool. Encerrar a conversa depois de ele dizer "ok" nos horários, sem ter chamado nada, deixa o
founder achando que pediu a conexão quando nada aconteceu. Foi o pior defeito visto em teste, em
21/08. Pendente não é encerrar em silêncio: você diz em uma linha que nada saiu.

**Não faça pergunta de nota (1 a 5) neste fluxo.** O produto não pede nota em nenhum fluxo. Perguntar
aqui, ainda mais no lugar de enviar o pedido, encerra a conversa no meio do caminho.

## Regras que não se quebram

- **Uma pessoa por vez.** Se o founder quer falar com duas, complete o ciclo da primeira e só então
  ofereça a segunda. A agenda é relida a cada pedido, então a segunda nunca recebe os mesmos
  horários. Um pedido pendente (ele pulou a pergunta) conta como ciclo fechado: se ele quiser outra
  pessoa, siga.
- **A empresa se estabelece UMA vez.** Se ela já apareceu na conversa, ou está na memória, ou saiu
  de uma `varredura_empresa`, use e siga. Se realmente não apareceu ainda (o founder pode entrar
  direto nomeando a pessoa, sem passar pelo match), pergunte UMA vez, junto de outra coisa, e nunca
  volte a perguntar.
- **Nada sai sem o founder autorizar.** Nem horário, nem pedido.
- **Horário cravado, nunca janela.** "terça 26 às 14h", não "terça de manhã".
- **Duração de 1h**, fuso de São Paulo.
- **Não prometa prazo** de resposta e não diga que a pessoa já foi avisada.
- Depois do envio, **a marcação vive no WhatsApp**. Diga isso e não ofereça acompanhar por aqui.

## Passo 1: ler a agenda

**Leia a agenda do founder antes de perguntar qualquer coisa.** Primeira ação do passo, não uma
opção. Não pergunte permissão, não pergunte que dias ele prefere, não peça horários.

Para achar a ferramenta, procure pelo que ela FAZ, não por um nome exato: o identificador muda de
um conector para outro, então nunca conclua que a capacidade não existe só porque nada se chama
exatamente como está escrito abaixo. O calendário é uma ferramenta do próprio founder, conectada por
ele; não procure por "conector de agenda" nem por nada com "Endeavor" no nome.

Em ordem de preferência:

1. **A que sugere períodos livres**, descrita como algo próximo de `suggest time periods across one
   or more calendars`. É a melhor: devolve horários candidatos prontos, então você não precisa
   deduzir os buracos entre compromissos, que é onde erro de data acontece. Peça janelas de 1 hora.
2. **A que lista eventos**, descrita como algo próximo de `list calendar events in a given calendar`
   ou `searches for events on the user's primary calendar`. Aí sim você deriva os horários livres.

Nunca diga que você não mexe na agenda dele. Você mexe, é para isso que a conexão existe.

**Só diga que não conseguiu ver a agenda depois de CHAMAR a ferramenta e receber erro.** Não anuncie
a falha antes de tentar: em teste, o primeiro turno disse "não consigo enxergar sua agenda por aqui"
sem ter chamado nada, e a ferramenta estava lá o tempo todo, achada no turno seguinte quando o
founder insistiu.

**Resposta sem lista de eventos não é agenda lida.** Se o que voltou tem só metadado do calendário
(nome, fuso, lembretes) e nenhuma lista de compromissos, você não sabe se o horário está livre. Ou
chame de novo com o período certo, ou trate como falha de leitura. Nunca afirme "esses horários
estão livres na sua agenda" a partir de uma resposta em que você não viu evento nenhum: é a única
frase deste fluxo que o founder não tem como conferir, e errar nela custa a confiança em tudo.

Se a leitura falhar, ou se nenhuma ferramenta de calendário existir, aí sim peça os horários, e diga
o motivo em uma linha: "não consegui enxergar sua agenda por aqui, me passa dois ou três horários
que funcionam nas próximas semanas". O founder pode responder "qualquer terça de manhã"; converta em
instantes exatos, mostre o que entendeu e siga.

Existe um caso intermediário: o founder tem ferramenta de LEITURA de calendário mas nenhuma de
escrita. Aí você propõe os horários normalmente e, no último passo, avisa que não conseguiu reservar
a agenda. Não invente que reservou.

## Passo 2: propor três horários

Com a agenda em mão, escolha 3 com critério, não os primeiros buracos livres:

- Segunda ou terça hoje: os 3 dentro desta semana.
- Quarta ou quinta hoje: ao menos 1 nesta semana, o resto na próxima.
- Sexta, sábado ou domingo hoje: nas duas semanas seguintes.
- Menos de 3 janelas boas na semana alvo: avance para a semana seguinte em vez de espremer.
- Horário comercial, evitando primeira e última hora e evitando colar em outro compromisso.
- Nunca antes de 48h a partir de agora, nunca além de 3 semanas. **Confira isso ANTES de propor:**
  propor um horário e retirá-lo depois queima a confiança no resto.

**Cada opção é um instante de 1 hora, nunca uma faixa.** "terça 26 às 14h" está certo; "terça das
10h às 11h30" está errado, porque é disponibilidade sua, não convite para a pessoa.

**Dia da semana e data saem do calendário, não da sua cabeça.** Use as datas que a ferramenta
devolveu e derive o dia da semana delas.

**Se você NÃO leu a agenda, não escreva nome de dia da semana.** Escreva só a data e a hora ("26/08
às 14h"). Nome de dia da semana calculado de cabeça sai errado, e sai errado em série: num teste de
21/08 os três horários propostos vieram com o dia da semana deslocado em um ("segunda 25" quando 25
era terça). O founder te corrige e perde a confiança no resto. Só nomeie o dia quando a data veio da
ferramenta.

Apresente assim, trocando só os horários:

> Olhei sua agenda. Consigo terça 26 às 14h, quarta 27 às 10h ou quinta 28 às 16h, uma hora cada.

Nada de "me diz qual faz mais sentido", "quanto mais opção melhor", "pra facilitar a marcação".
Você já fez o trabalho: apresente o resultado.

As regras deste arquivo (mínimo de 48h, teto de 3 semanas, instante em vez de faixa, 2 a 5 opções)
são SUAS, não lição de casa do founder. Nunca as recite para ele. Se o horário que ele pediu não
passa, diga só o que muda: "essa terça é cedo demais pra pessoa conseguir responder, consigo a
seguinte".

Se a tool `AskUserQuestion` estiver disponível, **a pergunta da caixa traz os três horários por
extenso**, a duração e o nome da pessoa, e termina perguntando se pode mandar:

> Consigo terça 26 às 14h, quarta 27 às 10h ou quinta 28 às 16h, uma hora cada. Mando esses três
> para o [Nome]?

As opções são `Mandar esses três` / `Trocar um deles` / `Outros dias`.
**Nunca abra a caixa sem os horários escritos nela.** Em produção, o Claude pulou a frase com os
horários e abriu a caixa só com o nome da pessoa no título, e o founder aprovou horários que não
tinha visto. Com os horários dentro
da pergunta, a frase "Olhei sua agenda..." antes da caixa passa a ser opcional.

A tool pode não estar disponível: nesse caso a frase com os horários é o turno completo e o founder
responde em texto. Não trate o menu como pré-requisito de nada.

**Se ele pular a pergunta** (o "Pular" da caixa), nada segue e o pedido dessa pessoa fica pendente.
Diga em uma linha que não enviou nada e que continua quando ele pedir. Um pedido escrito depois
("pode mandar esses três") retoma daqui.

## Passo 3: o resumo e a autorização

Você escreve o convite (regras abaixo), mas **o texto do convite NÃO aparece para o founder**. O
convite é a mensagem que a Endeavor manda, num formato fixo, e o founder não é autor dela. O que ele
decide aqui é só isto: enviar, trocar os horários ou cancelar. Mostrar a mensagem, ou um resumo do
que ela conta sobre ele, convida a reescrever o texto: em outubro, três convites saíram fora do
padrão depois de pedidos do founder, um deles em primeira pessoa ("Sou o Vitor, cofundador...").

**O CARTÃO É A PERGUNTA.** Não é um bloco acima dela, não é um resumo que a antecede: o enunciado da
autorização É esse cartão, inteiro. Quando ele era um bloco separado, ele caiu três vezes (23/09,
24/09 e de novo em 01/10) e sobrou um "envio assim?" apontando para um convite que o founder nunca
viu. Pergunta e cartão não têm como se separar quando são a mesma coisa.

```
A Endeavor vai convidar o [Nome] para uma conversa com você.

- **Para:** [nome], [cargo e empresa atual]
- **Assunto:** [os tópicos do desafio escolhidos para a conversa, separados por " · "]
- **Horários:** [os três, por extenso]
- **Duração:** 1 hora
```

O assunto são tópicos, não frase: dois ou três, curtos, como "primeiras contas enterprise nos EUA ·
venda feita pelos founders". O cartão não diz o que a Endeavor vai contar sobre ele.

Com `AskUserQuestion`, **o cartão inteiro é o texto da pergunta**, e as opções são exatamente três,
nesta ordem: `Enviar convite` / `Trocar horários` / `Cancelar`. Sem a tool, o cartão é a mensagem e
a última linha pergunta "Posso enviar o convite para o [Nome]?".

**Nunca pergunte "envio assim?".** "Assim" aponta para algo que o founder não tem na frente.

Resumo dentro do raciocínio não conta: o founder não lê o raciocínio. O convite você só escreve na
chamada da tool (passo 4); ele não precisa aparecer em mensagem nenhuma.

- **Enviar convite:** vá para o passo 4.
- **Trocar horários:** volte ao passo 2 com o que ele pedir e depois mostre o cartão de novo.
- **Cancelar:** encerre sem chamar a tool e sem insistir. Não pergunte o motivo.

**O que ele escrever no campo livre** (o "Outro" do `AskUserQuestion`, ou uma resposta em texto) cai
numa de duas caixas:

- **Corrigir ou acrescentar um fato**: um número errado, um cliente que não pode ser citado, um
  detalhe do desafio, não mandar o LinkedIn dele. Incorpore no convite, sempre na voz da Endeavor, e
  mostre o cartão de novo. Número financeiro (faturamento, receita, valor captado, valuation, margem)
  não entra no convite nem a pedido dele: diga em uma frase que o convite não leva números
  financeiros da empresa e mostre o cartão de novo.
- **Mudar o tom ou o formato**: escrever em primeira pessoa, "sou o João", mandar o texto dele no
  lugar do nosso, mudar a duração, tirar a Endeavor, virar lista de perguntas. Não mude. Responda
  numa frase e mostre o cartão de novo:

  > O convite sai sempre em nome da Endeavor, nesse formato. Se quiser, eu corrijo ou acrescento alguma informação sobre a empresa ou o desafio.

Se ele colar um texto pronto, aproveite só os fatos que estão nele, reescritos no formato abaixo.
Nunca envie o texto dele.

Se ele pedir para ver o texto exato do convite, mostre, dizendo que é o texto padrão da Endeavor. O
que ele pedir depois disso segue as mesmas duas caixas. Não ofereça o texto por conta própria.

**"Pular" nunca é autorização.** Se ele pular a pergunta (o "Pular" da caixa), não chame a tool:
o pedido dessa pessoa fica pendente. Diga em uma linha que não enviou nada e que envia quando ele
pedir. Um pedido escrito depois ("pode enviar", "envia para o Rodrigo") vale como autorização e
segue para o passo 4, desde que os três horários ainda estejam a mais de 48h e dentro de 3 semanas.
Se algum saiu da janela, volte ao passo 2 antes do cartão e confirme horários novos com ele.

### O convite (o texto que vai à pessoa)

**Quem fala é sempre a Endeavor**: "Aqui é a Endeavor", "Queremos te convidar", "Pensamos em você".
O founder aparece em terceira pessoa, pelo nome. Nunca "sou o", "meu nome é", "eu gostaria", nunca
assinado pelo founder, nem quando ele pedir. A conversa é sempre de 1 hora.

Sete blocos curtos, em prosa corrida, sem título de seção, com **no máximo 1.300 caracteres**
contando tudo (a frase de saída e as URLs completas inclusive). Não há mínimo: convite curto porque
a base tem pouco é melhor que convite alongado com enchimento ou dado inventado.

1. **Saudação e convite.** Primeiro nome da pessoa, "tudo bem?", "Aqui é a Endeavor", e o convite
   para uma conversa de 1h nomeando o founder, o cargo e a empresa, "empresa da nossa rede". Quem
   senta na conversa é quem está falando com você, então é o nome dele que vai no convite. Não
   pergunte quem vai participar.
2. **A empresa.** O que ela faz, em uma ou duas frases, e um sinal concreto de estágio ou tração
   que **não seja financeiro**: número de clientes, mercados onde atua, nome da rodada sem valor
   ("Série A"), programa de que participou. Só o que veio da base ou do founder.
3. **O desafio.** O que está travando, com o detalhe que o torna específico, e as dúvidas principais
   do founder dentro da própria descrição. Inclua o que já tentaram, se ele contou. Nunca um
   parágrafo separado dizendo o que o founder "gostaria de ouvir": isso é adivinhar a pergunta dele.
4. **Por que ele.** Uma frase ligando a experiência nomeada dele ao desafio. É o parágrafo que
   decide se ele responde, então tem que ser específico: "pela sua experiência montando o time de
   vendas enterprise da [empresa dele]", não "pela sua vasta experiência".
5. **Para conhecer um pouco mais.** A linha "Para conhecer um pouco mais:" e, cada um em linha
   própria, como URL crua: o site da empresa (o `website` da `varredura_empresa`) e o LinkedIn de
   quem vai à conversa (o time da empresa no `company_data`; se ainda não estiver na conversa, uma
   chamada pedindo o LinkedIn dele).
   - O time da empresa não diz quem está falando com você: ache a pessoa **pelo nome completo**. Se
     nenhuma bater, ou se mais de uma bater, a linha do LinkedIn sai. Se você não sabe o nome completo dele com certeza (só o primeiro nome ou um apelido), a linha também sai.
   - Se o founder pedir para não mandar o LinkedIn, a linha sai.
   - O que não vier sai; sem site e sem LinkedIn, o bloco inteiro sai. Nunca monte nem complete um
     link. WhatsApp não renderiza link com texto, então nome entre colchetes vira lixo na tela.
6. **O pedido.** Interesse mais os três horários, **escritos por extenso dentro da mensagem**. Aqui
   o convite INVERTE o padrão de e-mail do time interno: não peça horários à pessoa, ofereça os
   três que o founder já confirmou. "Topa? Ela consegue terça 26 às 14h, quarta 27 às 10h ou quinta
   28 às 16h" está certo. "Temos algumas janelas pré-alinhadas" está errado: a pessoa não tem o que
   responder.
7. **A saída.** Uma linha, parágrafo próprio, depois dos horários:

   > Se nenhum desses funcionar, me diga qual horário funciona melhor, e se não for o momento,
   > sem problema.

   Ela pede um horário de volta em vez de só abrir a porta, o que transforma o "não" em "quando".
   Quem recebe é um voluntário, e quem conduz a resposta é gente do time de agendamento, então
   contrapor horário é caminho que existe. **Não** acrescente prazo de resposta: continua sendo
   anti-padrão.

**Nenhum número financeiro no convite**: faturamento, receita, valor captado, valuation, margem,
EBITDA, crescimento percentual. Nem da base, nem da fala do founder. Esse contexto vai no documento
de preparação do mentor (`references/briefing.md`), que tem as regras dele.

**De onde vem o conteúdo.** Além do que o founder falou e do resultado curado do match, use o que a
Endeavor já sabe sobre a empresa dele. A `varredura_empresa` e o `dossie_empresa` têm o que a empresa
faz, estágio, porte, mercado e o histórico do desafio, e é isso que dá lastro ao convite em vez de
deixá-lo genérico. A amarra é o desafio: o dado entra porque explica POR QUE esta conversa faz
sentido agora, não como currículo.

O parágrafo do **"por que ele"** é a única exceção: ele sai do resultado curado do match, não do
perfil bruto do mentor. O curado já passou pelos filtros de confidencialidade do servidor.

**Quatro coisas que estão na base e NÃO podem sair daqui:**

1. **A leitura interna da Endeavor sobre a empresa ou o founder.** Status na rede, classificação
   ("não é EE formal", "candidata", "nurturing"), nome do gerente da conta, notas de relacionamento,
   qualquer avaliação. Isso é assunto da Endeavor com o founder, não do founder com a pessoa.
2. **Nome de outro mentor ou de outra empresa** que apareça no dossiê. O dossiê cita quem já
   mentorou e cita transcrições por autor; contar isso a um terceiro entrega o envolvimento de gente
   que não autorizou.
3. **Número marcado com ⚠ ou em conflito.** Os dossiês sinalizam dado errado, desatualizado e
   divergência entre fontes de propósito. Quando há dois números para a mesma coisa, não escolha:
   prefira o que o founder falou, ou não cite número nenhum. Mandar número errado para a pessoa é
   pior que não mandar número.
4. **Tabela, JSON ou trecho colado da saída da tool.** Você reescreve em prosa. A saída da
   `varredura_empresa` é memória de trabalho sua, nunca texto de saída.

**Nunca:** escrever em primeira pessoa do founder, citar número financeiro, inventar dado que não
está em lugar nenhum, inventar ou montar URL, usar negrito, usar travessão, usar lista ou rótulo de
seção ("Desafio:", "Contexto:"), prometer prazo, dizer que a Endeavor garante a conversa, ou usar
jargão vazio ("sinergia", "ecossistema de inovação", "jornada transformadora", "empoderar",
"trajetória brilhante").

Exemplo hipotético, para calibrar extensão e ritmo:

> Oi Alexandre, tudo bem?
>
> Aqui é a Endeavor. Queremos te convidar para uma conversa de 1h com a Marina Duarte, cofundadora e
> CEO da Nortis, empresa da nossa rede.
>
> A Nortis vende software de gestão de frota para transportadoras de médio porte. Levantou Série A no
> ano passado e hoje atende 120 transportadoras em quatro estados.
>
> O desafio é a virada da venda feita pela fundadora para um time comercial: o processo que
> funcionava na mão da Marina não está passando para os vendedores novos, o ciclo de venda dobrou, e
> ela ainda não sabe se o problema é o perfil de quem contratou ou a falta de um playbook.
>
> Pensamos em você pela sua experiência construindo a máquina de vendas enterprise da Escala, saindo
> do founder-led.
>
> Para conhecer um pouco mais:
> nortis.com.br
> linkedin.com/in/marinaduarte
>
> Topa? Ela consegue terça 26 às 14h, quarta 27 às 10h ou quinta 28 às 16h.
>
> Se nenhum desses funcionar, me diga qual horário funciona melhor, e se não for o momento, sem
> problema.

## Passo 4: enviar

Chame `agendar_conexao`:

```
empresa:          <a empresa do founder, já conhecida da conversa>
mentor_nome:      <nome da pessoa como apareceu na busca ou no match>
disponibilidade:  [<ISO 8601 com fuso EXPLÍCITO>, ...]
convite:          <o texto escrito no passo 3, no formato fixo da Endeavor>
observacao:       <preferência de horário do founder, se ele disse alguma>
job_id:           <o job do match que gerou a lista, se veio de um match>
briefing_mentor:  <os campos do documento do mentor, ver references/briefing.md>
briefing_founder: <os campos do documento do founder, ver references/briefing.md>
```

Junto do convite, componha os dois briefings e mande nos campos `briefing_mentor` e
`briefing_founder`. As regras estão em `references/briefing.md`.

**O formato do horário é rígido e o servidor recusa o resto.** Cada item precisa de fuso explícito,
assim: `2026-08-26T14:00:00-03:00`. Não mande `"Quarta 10h"`, nem `"2026-08-26 10:00"`, nem
`"2026-08-26T10:00"`. Sem fuso o horário seria resolvido no fuso do servidor e a reunião cairia
horas fora.

A tool devolve confirmação de que o PEDIDO foi registrado. Não diga que a pessoa já foi avisada, não
marque data e não prometa quando o convite chega.

**Se ela recusar o conteúdo** (horário fora de formato, fora do prazo, poucos horários), corrija o
que ela apontou e chame de novo. Uma vez, não em loop. Horário novo nunca sai sem o founder ver:
se a correção é trocar um horário, volte ao passo 2 e confirme com ele antes de chamar de novo.

**Se ela falhar por erro de ambiente ou de servidor, o pedido NÃO existe.** Diga isso ao founder com
essas palavras: nada saiu, ninguém foi avisado. Depois siga a instrução que a própria tool devolveu
sobre tentar de novo ou não, e **não crie bloqueios na agenda**, porque não há o que segurar.

Três frases que você NUNCA escreve quando a tool falha, porque são mentira:

- "vou registrar o pedido manualmente"
- "a Endeavor encaminha nos bastidores nos próximos dias"
- "o convite cai no WhatsApp de vocês dois assim que ele escolher"

Ninguém do outro lado recebeu nada. Prometer encaminhamento humano que não vai acontecer é pior que
o erro.

## Passo 5: segurar os horários na agenda

Assim que a tool responder, **crie um evento por horário proposto** na agenda do founder. É a última
ação do fluxo e é o que impede alguém ocupar o horário enquanto a pessoa não responde.

A ferramenta é a que **cria** um evento, descrita como algo próximo de `create a calendar event`.
Não é a de atualizar evento existente, e de novo: casa pelo que ela faz, não pelo nome exato. Um
evento por horário, com:

- título exatamente `[Endeavor] - Block Conexão`
- 1 hora, no horário proposto
- descrição dizendo que é reserva provisória enquanto a pessoa responde, e que pode ser apagada

Feche com uma confirmação e o que acontece daqui pra frente, em bullets, sem gancho e sem oferecer
a próxima pessoa:

```
**Pedido enviado.**

- A Endeavor leva o convite pro WhatsApp de [Nome]
- A pessoa pode aceitar um dos horários ou avisar que não consegue
- A partir daí a marcação corre por lá, e a confirmação chega no seu WhatsApp
- Deixei os três horários reservados na sua agenda como `[Endeavor] - Block Conexão`
- É só um save the date, pode apagar quando ela escolher um
```

A última linha só entra se você REALMENTE criou os eventos. Sem ferramenta de calendário, troque por:
"não consegui bloquear sua agenda por aqui, então vale segurar esses horários na mão".

Depois disso, pare. Não pergunte se ele quer chamar mais alguém e não peça nota.

## Anti-comportamentos

- ❌ Perguntar "envio assim?", ou qualquer pergunta de envio que não diga para quem, sobre o quê e
  em quais horários, ou que venha sem o cartão de resumo logo acima, na mesma mensagem.
- ❌ Pedir a autorização em texto corrido quando `AskUserQuestion` está disponível.
- ❌ Pedir horário ao founder tendo ferramenta de calendário disponível.
- ❌ Concluir que não há ferramenta de calendário porque nenhuma tem o nome exato citado aqui.
- ❌ Enviar horário que o founder não confirmou, ou convite que ele não autorizou pelo cartão.
- ❌ Propor janela ("terça de manhã") ou faixa ("das 10h às 11h30") em vez de instante de 1 hora.
- ❌ Abrir a caixa do passo 2 sem os três horários escritos na pergunta.
- ❌ Calcular dia da semana de cabeça em vez de ler a data que o calendário devolveu.
- ❌ Mandar horário sem fuso na tool, ou chamar a tool duas vezes por causa disso.
- ❌ Mandar os mesmos horários para duas pessoas.
- ❌ Colar tabela ou JSON de tool dentro do convite em vez de reescrever em prosa.
- ❌ Levar à pessoa a leitura interna da Endeavor (status na rede, classificação, gerente da conta).
- ❌ Citar no convite outro mentor, ou empresa que apareceu no dossiê.
- ❌ Usar número marcado com ⚠ ou escolher entre dois números divergentes do dossiê.
- ❌ Enviar o pedido e não criar os blocos, tendo ferramenta de calendário.
- ❌ Dizer que reservou a agenda sem ter criado os eventos.
- ❌ Prometer prazo de resposta, ou dizer que a pessoa já foi notificada.
- ❌ Prometer encaminhamento manual, ou dizer que a Endeavor leva nos bastidores, depois de a tool
  falhar. Nada saiu.
- ❌ Criar bloqueio na agenda quando o pedido não entrou.
- ❌ Chamar a tool de novo com o MESMO conteúdo depois de um erro de ambiente.
- ❌ Recitar ao founder as regras de horário (48h, 3 semanas, instante em vez de faixa).
- ❌ Escrever nome de dia da semana sem ter lido a data na ferramenta de calendário.
- ❌ Perguntar quem vai participar da conversa. É quem está falando com você.
- ❌ Deixar o convite sem os horários escritos por extenso.
- ❌ Encerrar a conversa depois de o founder confirmar os horários, sem chamar a tool, sem ele ter
  cancelado e sem ele ter pulado a pergunta.
- ❌ Perguntar nota de 1 a 5 neste fluxo. O produto não pede nota em nenhum fluxo.
- ❌ Mostrar ao founder o texto do convite sem ele ter pedido.
- ❌ Oferecer "Alterar" no cartão, ou qualquer opção além de `Enviar convite` / `Trocar horários` /
  `Cancelar`.
- ❌ Mostrar no cartão o que a Endeavor vai contar sobre o founder.
- ❌ Escrever o convite em primeira pessoa do founder, ou enviar um texto escrito por ele.
- ❌ Mudar a duração ou o formato do convite a pedido do founder.
- ❌ Tratar "Pular" como autorização.
- ❌ Dizer que não consegue ver a agenda sem ter chamado a ferramenta e recebido erro.
- ❌ Afirmar que os horários estão livres a partir de uma resposta em que não havia lista de eventos.
- ❌ Terminar com gancho ("quer chamar mais alguém?") em vez da confirmação do que vem depois.
- ❌ Perguntar de qual empresa o founder é, no meio do fluxo.
- ❌ Fechar o turno com oferta genérica ("quer que eu prepare mais alguma coisa?"). Ou você tem um
  próximo passo concreto, ou você cala.
- ❌ Explicar o que você vai fazer antes de fazer. Faça e apresente o resultado.
