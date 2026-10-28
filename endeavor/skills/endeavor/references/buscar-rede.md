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
3. Chame `buscar_rede(pergunta)` com a pergunta em texto livre. É **síncrona**: devolve **JSON** na
   mesma chamada (sem job_id, sem polling), com `mentores` e/ou `empresas` conforme o `alvo`, no
   máximo 20 de cada lado. Os campos `aderencia`, `motivo`, `recorte`, `nota` e `capped` estão
   explicados na seção "Como ler o resultado", logo abaixo.
4. **Raciocine sobre o JSON e entregue conforme a FORMA da resposta**, não conforme a fonte:
   - **Um nome pedido** (o founder perguntou por alguém específico): responda direto, uma pessoa,
     com nome, empresa e cargo atuais, trajetória curta e **sempre o LinkedIn**. Não transforme em
     lista, não ofereça mais nomes que ele não pediu.
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

## Como ler o resultado: aderência, motivo, recorte, nota e capped

Quando a pergunta tem um critério aberto ("quem entende de pricing para PME"), o servidor lê cada
candidato contra ele, e cada pessoa e cada empresa volta com dois campos a mais. Busca só por filtro
(um nome, uma empresa, um setor) volta sem eles.

- **`aderencia`**: `forte` (bate com o que ele pediu) ou `parcial` (chega perto, por um lado só). A
  lista já vem com os fortes primeiro; apresente nessa ordem. Com menos de 3 fortes, diga que o
  encaixe é parcial em vez de falar em "os 3 melhores", e com nenhum forte, diga que ninguém bate em
  cheio e que estes são os mais próximos.
- **`motivo`**: uma frase curta do servidor dizendo por que aquele item entrou. É o ponto de partida
  do "por que aparece": reescreva na sua voz, como fato sobre a pessoa ou a empresa. Não é o
  `motivo` que você manda na chamada (`direto`, `cascata`, `lookup`, `empresa`), que é só telemetria.
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
- **`capped`**: verdadeiro quando havia mais resultados do que cabem numa resposta (o máximo é 20 de
  cada lado). Diga que tem mais gente nesse recorte e ofereça afunilar, numa linha, por um critério
  que faça sentido para a pergunta (setor, cargo, empresa por onde passou, tipo de cliente). Não
  prometa mostrar todos.

## Quando a resposta traz pessoas

Cada pessoa vem com `name`, `tipo_na_rede`, `company_name` e `title` (empresa e cargo atuais),
`biography`, `linkedin`, `skills`, `experiences` (a trajetória, cargo por cargo),
`desafios_exibiveis` (desafios que ela já ajudou a resolver) e `frases_liberadas` (frases dela
liberadas para uso).

- **O "por que aparece"** sai do `motivo`, quando vier, e de `desafios_exibiveis`, `skills`,
  `experiences` e da bio.
  `frases_liberadas` você pode citar como frase da pessoa.
- **Campo vazio é esperado**: nem todo perfil tem tudo. Use o que veio, sem comentar o que falta.

## Quando a resposta traz empresas

Cada empresa vem com `company_name`, o que ela faz (`description`), `industry`, `business_model`,
`buyer` (quem compra dela), `year_founded`, `organization_type`, `is_endeavor_network` e `pessoas`
(quem da rede está ou esteve lá: `name`, `title`, `link_type` e `linkedin`).

- **Apresente**: nome, 1-2 linhas do que faz, e as pessoas com cargo e LinkedIn quando vierem. Com
  `is_endeavor_network` verdadeiro, diga que é "empresa da rede Endeavor". Com falso, ela é uma
  empresa por onde passou gente da rede: não a chame de empresa da rede.
- **Tire da lista a empresa do próprio founder.** A tool não sabe quem pergunta e pode devolvê-la.
- **Empresa sem `pessoas`** é esperado, não é dado faltando. Apresente a empresa e, se o founder
  quiser falar com alguém de lá, use o repasse descrito em "os caminhos": sem nome não há pedido a
  montar.
- **Números financeiros de outra empresa não existem nesta conversa.** O JSON não traz
  faturamento, captação, valuation nem número de funcionários — e você NÃO completa com
  conhecimento próprio, mesmo se o founder perguntar ("quanto a X fatura?" → honestidade: esse
  dado não é compartilhado aqui).
- **Empresa citada como trajetória é busca de mentor.** "Quem passou pela Nubank" procura gente
  com Nubank no currículo, não a Nubank como resultado — a tool já resolve isso; não reformule a
  pergunta do founder para "empresa" nesses casos.

<!-- Manutenção: a mecânica e a copy dos formatos de conexão espelham o passo 7 de
     references/experts.md. Mudou a promessa ou a apresentação lá, mude aqui (e vice-versa). -->
## Quando o founder quer falar com alguém: os caminhos

**O menu abaixo vale para QUALQUER PESSOA que apareceu na busca**, tanto no array `mentores` quanto
dentro de `empresas.pessoas`. Todas têm relação ativa com a Endeavor (a busca não devolve gente de
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

**Pedido por quem não veio na busca.** Sem menu de formatos: diga com honestidade que não encontra
a pessoa na rede ativa que você enxerga e ofereça repassar o interesse para a Endeavor avaliar.
Nenhuma promessa de mecânica ou prazo.

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
