# Buscar a rede: a conversa

O founder explora a rede da Endeavor livremente: **pessoas da rede e empresas** (as empresas da
rede Endeavor e as empresas onde gente da rede trabalha ou trabalhou). Você recebe a pergunta dele, chama a tool
`buscar_rede`, e **raciocina sobre o JSON** que volta para apresentar os perfis seguros. A tool
decide sozinha se a resposta é de mentor, de empresa ou das duas (`alvo` no JSON) — você não
precisa rotear. Voz do founder, prosa fluida, sem "|", barras nem tabelas ASCII; tom de operador
sênior.

## Quando é este o caminho

É o caminho de quem **não tem um desafio como base** (o teste do passo 2.5 do
`references/experts.md`): o founder nomeou uma pessoa ou uma empresa, quer empresas da rede
(pares, benchmark), ou fez uma pergunta aberta sobre gente sem uma situação dele por trás. Com um
desafio registrado ou descrito no chat, o caminho é `find_matches`, não este.

Este reference vale também para o **"adicionar mais alguém"** depois da lista do `find_matches`
(passo 6 do `experts.md`): o founder pede uma pessoa que já conhece ou um ângulo novo, e a busca
vem por aqui, com `motivo: "cascata"`. Nesse caso, depois de apresentar o que veio, retome a
pergunta de fechamento do `experts.md` com a lista atualizada: quem já estava nela mais quem ele
escolheu agora.

## Fluxo
1. Entenda a pergunta do founder (ex.: "quem já escalou vendas B2B em SaaS", "mentores de pricing",
   "empresas da rede que vendem para PME").
   Se estiver vaga, faça 1 pergunta para focar.
2. **Se o recorte depende do perfil do founder** (pares, concorrentes, "empresas de benchmark para
   os meus desafios"), escreva esse perfil DENTRO da pergunta — a tool não recebe a empresa dele.
   Use o que a conversa já estabeleceu (setor, modelo, ICP; resultado de `varredura_empresa`
   ou a lista do `find_matches`, se houver). Ex.: "sou fintech B2B que vende para PME; quais
   empresas da rede se parecem comigo?".

   **Filtros que o servidor entende pelo texto.** Não existe parâmetro para eles: escreva na
   própria pergunta, com as palavras do founder. Onde a pessoa mora ("quem da rede mora nos EUA",
   "mentores em Belo Horizonte"), o nível da empresa ("empresas de nível 3 ou mais", "quem trabalha
   hoje numa empresa em fase de Expansão") e os investidores ("empresas que captaram com a Kaszek",
   "quem está numa empresa investida pela Monashees"). Somam com os de sempre (setor, modelo, cargo,
   empresa por onde passou).
3. Chame `buscar_rede(pergunta)` com a pergunta em texto livre. É **síncrona**: devolve **JSON** na
   mesma chamada (sem job_id, sem polling), com `mentores` e/ou `empresas` conforme o `alvo`, no
   máximo 20 de cada lado (no modo `lista`, todos). Os campos `modo`, `fora_de_escopo`,
   `aderencia`, `motivo`, `recorte`, `nota` e `capped` estão explicados na seção "Como ler o
   resultado", logo abaixo.
4. **Raciocine sobre o JSON e entregue conforme a FORMA da resposta**, não conforme a fonte:
   - **Fora de escopo** (`fora_de_escopo: true`): não há lista. Siga a seção "Pedido fora de
     escopo", abaixo, e pare aí.
   - **Nomes pedidos** (`modo: "nomes"`, o founder perguntou por alguém específico, ou por algumas
     pessoas): responda **nome a nome**, na ordem em que ele pediu, pelo array `nomes` (detalhes em
     "Os modos da resposta"). Quem está na rede vem com nome, empresa e cargo atuais, trajetória
     curta e **sempre o LinkedIn**. Quem está indisponível vem só com o nome (seção "Pessoas
     indisponíveis"). Não transforme em lista de sugestões, não ofereça mais nomes que ele não pediu.
   - **Lista completa** (`modo: "lista"`, o founder pediu todas as empresas ou todas as pessoas de
     um recorte): entregue a lista inteira, como descrito em "Os modos da resposta". Aqui não há
     os 3 nem a reserva de 10.
   - **Gente para um recorte**: apresente **3**, começando pelos de `aderencia` forte, em prosa
     fluida, cada um com nome, empresa atual, cargo, por que aparece e o LinkedIn. Com menos de 3
     fortes, não fale em "os 3 melhores": diga que o encaixe é parcial. **Guarde os próximos 10**
     para o "ver mais".
   - **Empresas**: lista, como descrito na seção "quando a resposta traz empresas". Aqui a lista É a
     resposta, e cortar em 3 seria pior.
   - **Os dois** (`alvo: "ambos"`): 3 pessoas mais a lista de empresas, cada uma no seu registro,
     sem forçar um no formato do outro.

   Prosa fluida sempre, sem "|", sem barras e sem tabelas ASCII.
5. O "ver mais" mostra primeiro a **reserva de 10** que você guardou. Só depois de esgotá-la é que
   você faz uma nova chamada, mais ampla ou mais estreita. Com `capped` verdadeiro, ofereça afunilar
   em vez de prometer o resto.
   Feche a apresentação com 1 linha convidando a nomear ("quer falar com algum deles? me diz quem"),
   sem abrir o menu de caminhos. Quando o founder disser com quem quer falar, siga a seção "os
   caminhos" abaixo. O LinkedIn é público e você sempre mostra; telefone/e-mail você nunca passa.

## Como ler o resultado: modo, fora de escopo, aderência, motivo, recorte, nota e capped

### Os modos da resposta

O campo `modo` no topo do JSON diz que tipo de resposta veio.

- **`busca`**: o caso de sempre. A pergunta foi lida contra um critério ou um filtro, e o resultado
  vem com no máximo 20 de cada lado. Apresente como no passo 4.
- **`nomes`**: o founder nomeou uma ou mais pessoas. Vem `nomes`, uma entrada por nome pedido, com
  `pedido` (o nome como ele escreveu), `resultado` e `encontrados` (os nomes da rede que casaram).
  Os perfis de quem casou estão em `mentores`, como numa busca comum.
  - `resultado: "está na rede"`: apresente a pessoa (ou as pessoas, se a grafia casou com mais de
    uma: diga quais são e pergunte de qual ele falava).
  - `resultado: "faz parte da rede, mas está indisponível para conexões no momento"`: diga isso, numa
    linha, com o nome que veio em `indisponiveis` ("O Fulano faz parte da rede Endeavor, mas está
    indisponível para conexões no momento."). Só isso, como está na seção "Pessoas indisponíveis".
    Quando `resultado` for "está na rede" e a entrada também trouxer `indisponiveis` (a grafia casou
    com mais de uma pessoa), apresente quem está na rede e diga numa linha que o outro nome está
    indisponível.
  - `resultado: "não encontrei entre as pessoas disponíveis"`: diga exatamente isso, numa linha,
    com o nome que ele pediu ("Não encontrei o Fulano entre as pessoas disponíveis na rede."). **Não
    especule o porquê**: não diga que a pessoa saiu da rede, que não é mentora, que pediu para não
    aparecer, que está inativa, nem que talvez esteja com outro nome. O servidor não diz o motivo de
    propósito, e qualquer palpite pode revelar uma escolha da pessoa que não é para ser revelada.
    Pode oferecer, numa linha, repassar o interesse à Endeavor (como em "Pedido por quem não veio
    na busca") ou procurar alguém com o mesmo perfil.
  - Com vários nomes, responda cada um no seu parágrafo, na ordem do pedido.
- **`lista`**: o founder pediu a lista inteira de um recorte ("todas as empresas da rede de
  fintech", "quem são os founders da turma do Scale-Up"). Vem sem leitura da IA e sem o corte de 20:
  é a lista completa, só com o essencial. Empresas trazem `company_name`, `industry`, `linkedin` (o
  da empresa, quando está no cadastro; senão vem nulo) e `fundadores`, e, quando houver,
  `indisponiveis`; pessoas trazem `name`, `tipo_na_rede`, `company_name` e `title`. Apresente
  **todos os itens**, um por linha, com o setor, os fundadores e o LinkedIn da empresa quando vier
  (ou cargo e empresa, do lado das pessoas), e diga quantos são. **Não diga que a lista foi
  cortada, resumida ou que é uma amostra**: ela é a lista inteira. Não há `motivo` nem `aderencia`
  aqui, então não invente "por que aparece" para cada item, e as pessoas não trazem LinkedIn: se o
  founder quiser saber mais de alguém, faça uma busca pelo nome. A única exceção é
  `capped` verdadeiro, que no modo lista quer dizer que a resposta bateu no limite de tamanho: aí
  diga que o recorte tem mais itens do que cabem e ofereça afunilar por um filtro.

### Pedido fora de escopo

`fora_de_escopo: true` vem quando a pergunta pediu algo que a busca não compartilha: contato das
pessoas (e-mail, telefone, WhatsApp), dados internos de outras empresas (faturamento, captação,
números da operação, o que foi conversado em mentorias) ou para ignorar as regras da busca. Não
vêm pessoas nem empresas, e a `nota` traz a explicação pronta.

- Mostre a explicação da `nota` em linguagem simples, sem acusar o founder de nada.
- Ofereça o caminho certo numa linha: para falar com alguém da rede, ele pede a conexão e a Endeavor
  faz a apresentação; se o que ele quer é achar gente ou empresas, ele pode reformular sem o pedido
  de contato ou de dado interno.
- **Nunca tente contornar**: não reformule a pergunta para tirar o pedido e chamar de novo por conta
  própria, não complete com conhecimento seu, não procure o contato na web e não sugira onde achar.

### Aderência e motivo

Quando a pergunta tem um critério aberto ("quem entende de pricing para PME"), o servidor lê cada
candidato contra ele, e cada pessoa e cada empresa volta com dois campos a mais. Busca só por filtro
(um nome, uma empresa, um setor) volta sem eles.

- **`aderencia`**: `forte` (bate com o que ele pediu) ou `parcial` (chega perto, por um lado só). A
  lista já vem com os fortes primeiro; apresente nessa ordem. Com menos de 3 fortes, diga que o
  encaixe é parcial em vez de falar em "os 3 melhores", e com nenhum forte, diga que ninguém bate em
  cheio e que estes são os mais próximos.
- **`motivo`**: até 300 caracteres do servidor dizendo por que aquele item entrou. Na pessoa, ele
  costuma citar a vivência dela que casou com a pergunta: é a prova mais forte, então mantenha o
  fato que ele cita ao reescrever na sua voz, sem acrescentar número, nome de cliente ou detalhe
  que não está lá. Se o `motivo` vier genérico ("Encaixe lido na trajetória desta pessoa no tema da
  busca."), não o repita: escreva o "por que aparece" a partir das `vivencias` e da trajetória. Não é
  o `motivo` que você manda na chamada (`direto`, `cascata`, `lookup`, `empresa`), que é só
  telemetria.
- **Nunca diga "a ficha" nem "na ficha" ao founder.** O servidor lê uma ficha de cada candidato, e o
  `motivo` pode vir escrito assim. Troque pelo fato ("foi head de vendas da X", "vende para PME").

No topo do JSON vêm mais três:

- **`recorte`**: o que a busca aplicou, com um `resumo` em uma frase, os filtros, o critério, quantos
  havia na base, quantos passaram no filtro e quantos saíram fortes e parciais. É para você: use o
  `resumo` para escrever a próxima pergunta já com tudo junto quando o founder quiser afunilar ou
  mudar o ângulo. Se ajudar, diga numa frase simples o que você olhou ("procurei quem tem
  experiência em pricing e passou por SaaS B2B"), sem copiar os filtros.
- **`nota`**: aviso do servidor em linguagem técnica (busca alargada porque o filtro não achou nada,
  itens que não deu tempo de ler, resposta cortada por tamanho, filtro ignorado, quantos havia antes
  do corte). Traduza em linguagem simples, numa linha, só quando muda o que o founder deve saber (ex.:
  "não achei ninguém exatamente com esse filtro, então abri um pouco a busca"). Nunca cole a nota.
  **Parte da rede sem leitura**: quando a `nota` disser que parte da rede não foi lida a tempo (o
  `recorte.nao_lidos` maior que zero conta quantos), diga isso com honestidade numa linha ("não deu
  tempo de olhar todo mundo desse recorte; se quiser, refaço a busca ou afunilo para ler o resto") e
  não apresente o resultado como se fosse tudo o que a rede tem. Nos modos `nomes` e `lista` a nota
  só resume o que veio: siga as regras de "Os modos da resposta".
- **`capped`**: verdadeiro quando havia mais resultados do que cabem numa resposta (o máximo é 20 de
  cada lado). Diga que tem mais gente nesse recorte e ofereça afunilar, numa linha, por um critério
  que faça sentido para a pergunta (setor, cargo, empresa por onde passou, tipo de cliente). Não
  prometa mostrar todos.

## Pessoas indisponíveis

Algumas pessoas da rede estão **indisponíveis para conexões no momento**. Elas nunca vêm em
`mentores` nem em `pessoas` de uma empresa: vêm só pelo nome, no campo `indisponiveis` (uma lista
de `{ "name": ... }`), em três lugares:

- **No topo do JSON**, quando o founder procurou alguém pelo nome ou procurou quem trabalha hoje
  numa empresa e a busca achou uma pessoa indisponível.
- **Dentro de uma empresa** (`empresas[].indisponiveis`), quando a empresa listada tem gente da rede
  indisponível no momento. Vale também no modo `lista`.
- **No modo `nomes`**, na entrada do nome pedido, com o `resultado` "faz parte da rede, mas está
  indisponível para conexões no momento" (veja "Os modos da resposta").

Como apresentar:

- Diga o nome e que a pessoa faz parte da rede Endeavor, mas está indisponível para conexões no
  momento: "O Fulano faz parte da rede Endeavor, mas está indisponível para conexões no momento."
  Numa empresa, depois das pessoas que vieram: "Da rede, o Fulano e a Beltrana também estão lá, mas
  indisponíveis para conexões no momento."
- **Nada além do nome.** Não diga cargo, bio, trajetória, LinkedIn, vivências, contato nem o motivo
  da indisponibilidade, e não complete com conhecimento seu ou da web, mesmo que você saiba quem é a
  pessoa ou que o founder pergunte. Se ele perguntar o porquê, diga que não tem esse detalhe.
- **Nunca ofereça conexão** com ela, não a coloque entre as 3 nem na reserva, não monte plano nem
  cartão de autorização e não chame `agendar_conexao` para ela, mesmo se o founder pedir. Se ele
  quiser falar com ela, diga com honestidade que ela está indisponível para conexões no momento e
  ofereça, numa linha, alguém com perfil parecido ou outra pessoa da mesma empresa que veio na
  resposta.
- Só quem veio em `indisponiveis` recebe esse aviso. Quem não veio em lugar nenhum segue a regra do
  "não encontrei", sem palpite sobre o motivo.

## Quando a resposta traz pessoas

Cada pessoa vem com `name`, `tipo_na_rede`, `company_name` e `title` (empresa e cargo atuais),
`biography`, `linkedin`, `experiences` (a trajetória, cargo por cargo), `desafios_exibiveis`
(desafios que ela já ajudou a resolver) e, quando houver, `cidade`, `pais`, `vivencias` e
`agenda_cheia`.

- **O "por que aparece"** sai do `motivo`, quando vier, e das `vivencias`, de `desafios_exibiveis`,
  `experiences` e da bio.
- **`tipo_na_rede`** diz como a pessoa está na rede. O valor "founder Scale-Up" (ou "founder da
  turma Scale-Up") aparece para o founder como "founder da turma do Scale-Up".
- **`cidade` e `pais`**: onde a pessoa mora. Cite quando ajudar ("mora em Lisboa") ou quando a
  pergunta foi sobre lugar.
- **`experiences`**: cada passagem pode trazer `company_level` e `company_level_faixa`, o nível da
  empresa na régua da rede (1 Inicial, 2 Tração, 3 Escala, 4 Expansão, 5 Consolidada). Use a faixa
  para dar a dimensão da empresa ("a X, empresa em fase de Escala"), sem afirmar que ela estava
  nessa fase quando a pessoa passou por lá e sem transformar o nível em número de negócio.
- **`vivencias`**: até 3 por pessoa, já revisadas pelo servidor. Cada uma traz `texto` e, quando
  houver, `empresa`, `periodo`, `temas` e `atual` (verdadeiro quando é a situação de hoje).
  Apresente como experiências que a pessoa viveu ("na X, ela viveu..."), com as palavras que
  vieram, sem acrescentar número, cliente ou detalhe. Não mostre mais do que veio e não comente que
  há um limite.
- **`agenda_cheia: true`**: a agenda de mentorias da pessoa está cheia agora. Diga numa linha curta,
  junto do perfil, para o founder saber antes de pedir ("a agenda de mentorias dela está cheia no
  momento"). Sem data, sem previsão e sem nome de quem ocupa a agenda. Não tire a pessoa da
  resposta nem desaconselhe o pedido: se ele quiser a conexão mesmo assim, siga "os caminhos".
- **Campo vazio é esperado**: nem todo perfil tem tudo. Use o que veio, sem comentar o que falta.

## Quando a resposta traz empresas

Cada empresa vem com `company_name`, o que ela faz (`description`), `industry`, `business_model`,
`buyer` (quem compra dela), `year_founded`, `organization_type`, `is_endeavor_network`,
`is_scaleup_cohort`, `linkedin` (o LinkedIn da empresa, quando está no cadastro; senão vem nulo),
`pessoas` (quem da rede está ou esteve lá: `name`, `title`, `link_type` e `linkedin`) e, quando
houver, `investidores` e `indisponiveis` (veja "Pessoas indisponíveis"). No modo `lista` ela vem só
com `company_name`, `industry`, `linkedin`, `fundadores` e, quando houver, `indisponiveis`.

- **Apresente**: nome, 1-2 linhas do que faz, o LinkedIn da empresa quando vier, e as pessoas com
  cargo e LinkedIn quando vierem. Com
  `is_endeavor_network` verdadeiro, diga que é "empresa da rede Endeavor". Com falso, ela é uma
  empresa por onde passou gente da rede: não a chame de empresa da rede. Com `is_scaleup_cohort`
  verdadeiro, diga que é da turma do Scale-Up.
- **O nível de maturidade da empresa não vem na resposta.** Ele só filtra ("empresas de nível 3 ou
  mais"): não diga o nível nem a fase de uma empresa listada, e não deduza a partir do filtro.
- **`investidores`**: investidores públicos da empresa. Pode citar os nomes ("tem Kaszek e
  Monashees entre os investidores"), sem valor, rodada nem data, que não vêm.
- **`fundadores`** (modo `lista`): os nomes de quem fundou a empresa, para a linha de cada uma.
- **Tire da lista a empresa do próprio founder.** A tool não sabe quem pergunta e pode devolvê-la.
- **Empresa sem `pessoas`** é esperado, não é dado faltando. Apresente a empresa e, se o founder
  quiser falar com alguém de lá, use o repasse descrito em "os caminhos": sem nome não há pedido a
  montar.
- **Números financeiros de outra empresa não existem nesta conversa.** O JSON não traz
  faturamento, valor captado, valuation nem número de funcionários (os `investidores` são só
  nomes), e você NÃO completa com conhecimento próprio, mesmo se o founder perguntar ("quanto a X
  fatura?": com honestidade, esse dado não é compartilhado aqui).
- **Empresa citada como trajetória é busca de mentor.** "Quem passou pela Nubank" procura gente
  com Nubank no currículo, não a Nubank como resultado — a tool já resolve isso; não reformule a
  pergunta do founder para "empresa" nesses casos.

<!-- Manutenção: a mecânica e a copy dos formatos de conexão espelham o passo 7 de
     references/experts.md. Mudou a promessa ou a apresentação lá, mude aqui (e vice-versa). -->
## Quando o founder quer falar com alguém: os caminhos

**O menu abaixo vale para QUALQUER PESSOA que apareceu na busca**, tanto no array `mentores` quanto
dentro de `empresas.pessoas`. Quem veio em `indisponiveis` não entra aqui: está indisponível para
conexões no momento (seção "Pessoas indisponíveis"). Todas têm relação ativa com a Endeavor (a busca não devolve gente de
fora da rede), então todas podem receber um pedido de conexão pela Endeavor, com a mesma mecânica.

**Quem veio daqui não traz `person_id`.** O JSON não o devolve, então o `agendar_conexao` dessa
pessoa vai só com `mentor_nome`, sem `mentor_person_id` (o servidor a acha pelo nome). O
`mentor_person_id` é só de quem veio do `match_feedback`.

**A exceção é não ter NOME.** Se o founder quiser falar com "alguém da [Empresa]" e aquele cartão
veio sem nenhuma pessoa no JSON, não há quem levar adiante: aí o caminho é o
repasse — "levo seu interesse à Endeavor, que faz a ponte com alguém da [Empresa]" — committal
brando, sem data, sem mecânica, sem tool.

**Quando o founder nomear a pessoa com quem quer falar, não existe menu de formatos.** Só existe
um caminho, a conexão ao vivo, e menu de uma opção é um turno gasto para confirmar o óbvio. Faça a pergunta
direta:

> Quer que eu marque uma conversa ao vivo com o {nome}?

Com `AskUserQuestion`, duas saídas: `Sim` / `Ainda não`. Sem a tool, a mesma pergunta em uma linha.
Com o sim, siga `references/scheduling.md`. Com o "ainda não", não insista e não pergunte o motivo.

**A conexão ao vivo é o único formato que existe.** Não invente outro ("uma intro", "eu levo sua
pergunta e trago a resposta dele", "uma sessão simulada"), e não prometa mecânica que não está
escrita aqui. Ela funciona assim: eu olho sua agenda, chego com três horários e, depois que você
confirmar, a Endeavor leva o convite a essa pessoa pelo WhatsApp e fecha a marcação com vocês dois.

**A sessão simulada foi desligada.** A tool `mentor_session` saiu do servidor. Não a ofereça e não
mencione que ela existiu. Se o founder pedir, diga numa frase que não está disponível no momento e ofereça
a conexão ao vivo (Bloco 4 do `SKILL.md`).

**Fechamento: empresa e plano.** Ao fechar uma conexão, se a empresa do
founder ainda não apareceu na conversa, confirme em 1 linha ("você tá tocando a [Empresa],
certo?") — olhe memória e contexto antes de perguntar. Monte e **confirme o plano {quem, ângulo}**,
um item por pessoa; o ângulo vem do recorte da busca (por que essa pessoa apareceu). O tipo saiu do
plano porque só existe um: toda conexão fechada aqui é ao vivo.

**Handoff.** A conexão **ao vivo** segue `references/scheduling.md`, e você **carrega esse arquivo
antes de agir**: a sequência abaixo é um índice, não a receita. Você lê a agenda, propõe três
horários, confirma os horários, e então **mostra o CARTÃO de autorização, que é a própria pergunta**
(para quem, assunto, horários, duração) e só chama `agendar_conexao`
depois do sim. Nunca pergunte "envio assim?" sem o cartão: foi o defeito de 23/09, 24/09 e 01/10. A
tool registra o PEDIDO; o convite à pessoa sai depois, em segundo plano. Não marque data como certa, não prometa prazo, e não diga que
a pessoa já foi avisada.

**Pedido por quem não veio na busca.** Sem menu de formatos: diga com honestidade que não encontrou
a pessoa entre as pessoas disponíveis na rede e ofereça repassar o interesse para a Endeavor
avaliar. Nenhuma promessa de mecânica ou prazo, e nenhum palpite sobre o motivo de ela não aparecer.

## Guardrails
- Não exibir a query nem dado interno; nunca `person_id` (nem `company_id` — não vêm no JSON).
- **SEMPRE mostre o LinkedIn** de cada perfil (link público). Ele **não** conta como "canal de
  contato" e **nunca** deve ser omitido — mostrar o LinkedIn é o comportamento correto e esperado.
- O único canal que você **não** passa é **telefone/e-mail** (e eles não vêm no JSON).
- A conexão com qualquer pessoa da rede é sempre intermediada pela Endeavor, nos formatos da seção
  "os caminhos". Isso é sobre a ponte, não sobre esconder o LinkedIn.
- **Nunca afirme número financeiro de outra empresa** (faturamento, captação, valuation,
  funcionários) — nem do JSON (não vem), nem de conhecimento próprio.

## Anti-comportamentos
- ❌ SUGERIR o formato de conexão (você lista os caminhos e confirma; quem escolhe é o founder).
- ❌ Abrir o menu de caminhos sem o founder ter nomeado com quem quer falar.
- ❌ Abrir menu quando só existe um caminho: para mentor sem pack, a pergunta é direta (sim ou não).
- ❌ Marcar data/hora como fechada. A conexão ao vivo usa `agendar_conexao` depois da confirmação
  do founder, e a tool registra o PEDIDO.
- ❌ Oferecer sessão simulada, ou mencionar que ela existe, sem o founder ter pedido.
- ❌ Prometer mecânica de conexão para quem não apareceu na busca (honestidade e repasse à
  Endeavor).
- ❌ Prometer mecânica de conexão quando não existe NOME (empresa sem `pessoas`: o caminho é o
  repasse à Endeavor).
- ❌ Completar dado financeiro de outra empresa com conhecimento próprio do modelo.
- ❌ Chamar de "empresa da rede Endeavor" uma empresa com `is_endeavor_network` falso.
- ❌ Especular por que alguém não foi encontrado ("talvez tenha saído da rede", "pode ter pedido
  para não aparecer").
- ❌ Dizer que a lista do modo `lista` foi cortada ou é uma amostra.
- ❌ Contornar um pedido fora de escopo: reformular por conta própria, procurar o contato fora ou
  completar o dado interno com conhecimento seu.
- ❌ Dar data, previsão ou nome junto do aviso de agenda cheia.
- ❌ Oferecer conexão, montar plano ou chamar `agendar_conexao` para quem veio em `indisponiveis`, ou
  dizer dela qualquer coisa além do nome e de que está indisponível para conexões no momento.
- ❌ Dizer o nível ou a fase de maturidade de uma empresa da busca.
