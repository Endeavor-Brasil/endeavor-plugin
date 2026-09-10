# Briefing de conexão: os dois documentos

Entra em cena no passo 4 do `scheduling.md`, junto do convite, depois de o founder autorizar o
envio. Você compõe **dois documentos** que a Endeavor entrega antes da conversa: um para o mentor e
um para o founder. Eles vão nos campos `briefing_mentor` e `briefing_founder` da mesma chamada de
`agendar_conexao`.

**Você não escreve HTML.** Você preenche campos, e o servidor monta o documento com a identidade
visual da Endeavor. Se você mandar markup, ele vai aparecer escapado no meio do texto.

## Regras que não se quebram

- **Os dois juntos ou nenhum.** Não existe pedido com um só. Se você não conseguir compor um dos
  dois, chame a tool sem nenhum dos campos: o pedido de conexão entra do mesmo jeito.
- **Briefing nunca atrasa a conexão.** Se algo der errado na composição, o pedido vai sem os
  documentos. Não avise o founder que faltou briefing, não pergunte se ele quer, não tente de novo.
- **Nada de meta-conversa dentro do documento.** Nenhuma etiqueta de origem, nenhuma nota de rodapé
  explicando de onde veio um dado, nenhuma frase que fale com o leitor sobre como o documento foi
  montado. O leitor não sabe que existe uma IA no meio, e não é papel do documento contar.
- **Nenhum número sobre a trajetória do mentor**, nos dois documentos. Nem valor, nem múltiplo, nem
  proporção, nem contagem de conta ganha. Vale papel, empresa, período, setor, mercado e a natureza
  do movimento. Detalhe em "o que nunca entra".
- **O documento do founder não afirma nada sobre a cabeça, o estilo ou o preparo do mentor.** Você
  não sabe como ele pensa, o que ele vai perguntar, nem se ele vai estudar a empresa antes.
- **Só o que o founder falou NESTA conversa.** Nada que ele tenha dito em mentoria com outro mentor
  entra no documento do mentor, mesmo estando no dossiê.
- **Sem travessão.** Vírgula, ponto, parênteses ou dois pontos.

## O que o servidor faz, e você não faz

- O HTML, o CSS, a paleta e a tipografia.
- A marca d'água com o nome do mentor.
- O logo e o rodapé.
- O cabeçalho com título, data e a nota de confidencialidade.
- A **abertura adaptativa**: você só manda `mentor_recorrente: true` ou `false`, e o servidor decide
  se entra o parágrafo institucional da Endeavor.
- O bloco **"Como funciona uma mentoria na Endeavor"**, que aparece sozinho quando
  `mentor_recorrente` é `false`.

**A formatação que os campos aceitam é só esta, e é o que o documento aprovado usa:**

- `**assim**` vira negrito. Serve para o termo que o documento inteiro gira em torno (uma vez por
  campo, no máximo) e para a frase de abertura de cada ponto do `preparar`.
- Linha em branco no `contexto` separa parágrafo. Use uma: o primeiro parágrafo apresenta, o
  segundo diz o que está em jogo.
- Qualquer outra tag ou marcação sai como texto na cara do leitor. Não tente.

## Documento 1: o que o mentor recebe

Cinco blocos. A estrutura é a do briefing que a Endeavor já usa há tempo com mentores, e não é para
ser reinventada por conexão.

### `contexto`

Prosa, dois a quatro períodos. O que a empresa faz em uma frase, o momento dela em seguida, e o
paralelo com a trajetória do mentor fechando. Não abra com saudação: o servidor cuida disso.

O paralelo é o bloco que decide se o mentor lê o resto. Tem que ser específico daquele mentor. "Pela
sua experiência montando o time de vendas enterprise" serve. "Pela sua vasta experiência em gestão"
não serve para ninguém.

### `empresa_resumo`

De cinco a oito linhas, cada uma com `rotulo` e `valor`. As cinco primeiras são fixas, nesta ordem:

| `rotulo` | `valor` |
|---|---|
| Fundação | Ano e cidade |
| Modelo | O que vende e como cobra, em uma linha |
| Escala | Porte de operação: clientes, funcionários, perfil de cliente |
| Captação | Estágio, rodada e investidores, **só de fonte pública** |
| Produtos | Os produtos centrais e a sequência entre eles |

Da sexta em diante você nomeia, com a regra de "extras" mais abaixo. Numa fintech pode valer uma
linha de regulatório; numa empresa de infraestrutura, o motion de vendas. Não complete a tabela só
para ela ficar com seis linhas.

### `diferenciais`

De três a cinco itens, cada um com `titulo` e até dois `pontos`. O título é a afirmação, e os pontos
são a evidência. Isto não é lista de qualidades: é o que explica por que a empresa abriu espaço num
mercado que já tinha dono. Se um item serviria para qualquer concorrente dela, ele não é
diferencial.

### `temas`

Um ou dois. Cada um com `titulo` (o tema em duas ou três linhas, que aparece destacado) e
`valorizaria` (três a cinco pontos do que o founder valorizaria ouvir daquele mentor
especificamente).

Um tema é melhor que dois quando a conversa tem foco. Dois quando o desafio tem duas frentes e o
mentor cobre as duas. Nunca três: uma hora não dá.

Os pontos de `valorizaria` são as perguntas do founder traduzidas para a experiência do mentor.
Cada um tem que ser respondível por aquela pessoa, e por poucas outras.

### `pares`

De três a seis, cada um com `nome` e `porque` em uma linha. Empresas de referência no mercado da
empresa do founder, não necessariamente concorrentes. Serve para o mentor calibrar o tabuleiro em
dez segundos. Só de pesquisa pública.

## Documento 2: o que o founder recebe

Seis blocos. É o **espelho inverso** do documento do mentor: onde lá se descreve a empresa, aqui se
descreve o mentor, e os dois últimos blocos preparam o founder para a hora.

### `contexto`

Prosa, dois a três períodos. Abre nomeando o mentor, o que ele faz hoje e o vínculo com a Endeavor.
Depois, o paralelo, do lado de cá: o que o founder precisa agora e onde a trajetória do mentor
encosta nisso. É o mesmo cruzamento do outro documento, escrito para o outro leitor.

### `mentor_resumo`

Sete linhas fixas, na ordem, mais até uma nomeada por você:

| `rotulo` | `valor` |
|---|---|
| Hoje | Papel e empresa atual, com o ano de início |
| Trajetória | Os papéis anteriores relevantes, com empresa e período |
| Expertise | As áreas em que ele tem repertório, não adjetivos |
| Setores onde operou | Os setores das empresas em que ele trabalhou |
| Perfil de cliente | Porte, decisor e tipo de ciclo que ele operou |
| Geografia | Onde a trajetória dele aconteceu |
| Perfil | Operador, founder, investidor, conselheiro. O que ele é, não como ele é |

Nada aqui descreve comportamento. "Provoca muito", "chega preparado", "gosta de números" não entram.

### `operou`

De dois a quatro itens, cada um com `titulo` (papel, empresa e período) e até três `pontos`. Os
pontos dizem **o que a empresa era e o que mudou na gestão dele**, sem quantificar. "Montou a
máquina de vendas saindo da venda liderada pelos sócios" entra. "Multiplicou a receita por dez" não.

Este bloco é o que faz o founder confiar no encaixe, então prefira o movimento específico ao cargo
genérico. "CRO de SaaS B2B" diz menos que "entrou quando a venda era toda dos sócios e saiu com time
comercial rodando".

### `temas`

Um ou dois, cada um com `titulo` e de dois a quatro pontos em `explorar`. Mesmos temas do outro
documento, virados para a perspectiva do founder: o que **ele** deve levantar, não o que o mentor
sabe. "Como ele estruturou a passagem da venda dos sócios para o time" é do founder. "Ele pode
explicar sobre estruturação de time" é descrição.

### `levar`

Oito linhas fixas, mais até duas nomeadas por você. Cada uma com `pergunta` (o que pode ser
perguntado na conversa) e `levar` (o que o founder deve ter na cabeça).

**Nenhum número da base entra aqui.** A coluna `levar` é orientação em texto, e a razão é simples: o
founder pensa melhor nos números dele do que relendo os nossos, que podem estar velhos ou
divergentes. "Quanto os maiores clientes representam do total" está certo. "Seus três maiores
clientes são 40% da receita" está errado, mesmo que a base diga isso.

As oito, nesta ordem: onde vocês estão e para onde vão; ICP; quem vendeu até aqui; concentração da
receita; ticket por tipo de cliente; decisor e processo de compra; canais e custo; retenção e
expansão.

### `preparar`

Três ou quatro pontos. Orientação de como usar a hora, não sobre o mentor. Uma hora dá para uma
decisão, não para três. Feche com uma linha sobre onde o repertório do mentor é mais fundo, que é a
única parte deste bloco que muda por conexão.

Cada ponto abre com a instrução em negrito e o resto explica: `**Chegue com a pergunta de
verdade.** "Como eu escalo o time comercial sem comprimir a margem" rende muito mais que "como eu
vendo mais".`

## De onde vem o conteúdo

| Bloco | Fonte |
|---|---|
| Paralelo, nos dois documentos | O resultado curado do match, mais o que o founder falou nesta conversa |
| Empresa: fundação, modelo, escala, produtos | `varredura_empresa` e `dossie_empresa` |
| Empresa: captação | **Só pesquisa pública.** Nunca o valor de captação que a base traz |
| Diferenciais competitivos e pares | Pesquisa na web no turno, ancorada no que a varredura e o dossiê dizem do modelo |
| Mentor: tudo | `buscar_rede` com o nome do mentor, mais o resultado curado do match |

Sobre a captação: a base tem esse campo e ele erra com frequência, porque é cadastro e não é
atualizado a cada rodada. Fonte pública é mais correta e é dizível a um terceiro. Se a pesquisa não
achar nada confiável, deixe a linha com o estágio só ("Series A") ou omita.

Sobre a pesquisa: ela é a parte mais lenta da composição. Faça uma busca por bloco, não uma por
linha, e não vá atrás de número que você não vai usar.

## O que nunca entra no documento do mentor

Esta lista **não tem rede de segurança do lado do servidor**. Se passar aqui, chega ao mentor.

- ❌ **Nome de cliente do founder.** O dossiê cita clientes nomeados em casos de valor entregue.
  Contar isso a um terceiro entrega quem compra dele.
- ❌ **Penetração da carteira da Endeavor.** Coisas como "trinta das trinta e nove empresas do
  programa já são clientes" são leitura interna, e algumas empresas nem podem usar isso comercialmente.
- ❌ **Nome de outro mentor.** O dossiê cita quem já mentorou e atribui fatos por autor. Um mentor
  saber quem mais conversou com aquela empresa entrega o envolvimento de gente que não autorizou.
- ❌ **Nome de pessoa da rede citada em prioridade.** Founders, executivos e mentores aparecem
  nominalmente nos registros de desafio. Nenhum deles vai para o documento.
- ❌ **Leitura interna da Endeavor.** Status na rede, classificação de faixa, nota de mentoria,
  quantidade de mentorias, notas de relacionamento, nome do gerente da conta, e qualquer avaliação.
- ❌ **Número marcado com ⚠ no dossiê.** O dossiê sinaliza dado divergente, desatualizado ou com
  erro de transcrição de propósito. Quando há dois números para a mesma coisa, não escolha: prefira o
  que o founder falou nesta conversa, ou não cite número nenhum.
- ❌ **Qualquer coisa que o founder tenha dito em mentoria com outro mentor.** Está no dossiê porque
  é memória da Endeavor, não porque é dizível a terceiros.
- ❌ **Tabela, JSON ou trecho colado de saída de tool.** Você reescreve em prosa. A saída da
  `varredura_empresa` e do `dossie_empresa` é memória de trabalho sua.

## O que nunca entra no documento do founder

- ❌ **Quantificação da trajetória do mentor.** Nem "de dez para cem milhões", nem "multiplicou por
  dez", nem "cortou o ciclo pela metade", nem "nove das dez maiores do setor", nem percentual, nem
  valor de aquisição ou de saída.
- ❌ **Caracterização de pessoa ou de conduta.** Estilo, viés, temperamento, conflito de interesse,
  o que ele costuma fazer em mentoria. Nada disso.
- ❌ **Previsão de comportamento.** "Ele vai perguntar", "ele vai reenquadrar", "ele chega tendo
  estudado a empresa". Você não controla o que o mentor faz, e prometer isso ao founder cria
  expectativa que a Endeavor não sustenta.
- ❌ **Nota, avaliação ou quantidade de mentorias do mentor.**
- ❌ **Nome de outra empresa que ele mentorou.**

## Extras: quando vale trazer coisa nova

A parte fixa dos blocos existe para o documento ser reconhecível. Os extras existem porque cada
conexão é diferente.

**A regra de entrada é uma só:** um extra entra se mudar o que o leitor precisa preparar para **esta**
conversa. Se ele serviria em qualquer briefing daquela empresa, ou em qualquer briefing daquele
mentor, é currículo e fica fora.

**Teto de três extras por bloco.** O documento tem três páginas e parte do motivo de ele ser lido é
isso. O servidor descarta o excedente sem avisar.

## Exemplo hipotético, para calibrar extensão e ritmo

Empresa e mentor inventados, com o mesmo grau de detalhe que se espera de um caso real.

**Documento do mentor, `contexto`:**

> A Nortis vende software de gestão de frota para transportadoras de médio porte, em assinatura por
> veículo monitorado. Cresceram com a venda na mão da fundadora e chegaram a algumas dezenas de
> contas, e agora estão montando o primeiro time comercial: o processo que funcionava com ela não
> está passando para os vendedores novos, e o ciclo de venda alongou. É a virada que você operou na
> Vext, e é sobre isso que ela quer te ouvir.

**Documento do mentor, `temas[0]`:**

> `titulo`: Passar a venda da fundadora para um time, sem perder a taxa de fechamento que ela tinha
> na mão. O produto é técnico e o comprador é operacional, então o vendedor novo precisa de
> repertório que hoje só existe na cabeça dela.
>
> `valorizaria`:
> - Como você separou o que era processo do que era a pessoa, quando montou o time comercial da Vext
> - Que primeiro papel você contrataria aqui, vendedor ou pré-vendas, e por quê
> - Como você mediria os primeiros noventa dias de alguém nessa posição

**Documento do founder, `contexto`:**

> Esta é uma nota de contexto antes da sua conversa com Helena Braga, hoje sócia da Vext e mentora da
> rede Endeavor. O que vocês precisam agora é tirar a venda da sua mão sem perder a taxa de
> fechamento no caminho. A Helena entrou na Vext quando a venda era toda dos sócios e saiu de lá com
> time comercial rodando, num produto técnico vendido para comprador operacional, que é o seu caso.

**Documento do founder, `operou[0]`:**

> `titulo`: Vext, diretora comercial, 2018 a 2023
>
> `pontos`:
> - SaaS de gestão de operação industrial, vendido para indústria de médio porte
> - Entrou quando a venda era toda dos sócios e saiu com time comercial próprio rodando
> - Estruturou pré-vendas e passou o repertório técnico dos fundadores para material de venda

**Documento do founder, `levar[3]`:**

> `pergunta`: Concentração da receita
>
> `levar`: Quanto os seus maiores clientes representam do total. Se não estiver à mão, é o primeiro
> número a levantar antes da conversa.

## Anti-comportamentos

- ❌ Escrever HTML, markdown ou qualquer marcação dentro dos campos.
- ❌ Mandar um dos dois documentos sem o outro.
- ❌ Segurar o pedido de conexão porque a composição do briefing não fechou.
- ❌ Avisar o founder que o briefing não saiu, ou perguntar se ele quer um.
- ❌ Mostrar ao founder o conteúdo do documento do mentor antes de enviar. O cartão de resumo do
  passo 3 já é a autorização, e ele não vira preview.
- ❌ Colocar número da base no `levar`.
- ❌ Quantificar a trajetória do mentor em qualquer campo dos dois documentos.
- ❌ Afirmar estilo, viés, humor ou preparo do mentor.
- ❌ Prever o que o mentor vai perguntar ou fazer na conversa.
- ❌ Dizer no documento de onde veio um dado, ou explicar como o documento foi montado.
- ❌ Levar ao mentor nome de cliente do founder, de outro mentor, ou de pessoa da rede.
- ❌ Usar valor de captação que veio da base em vez de fonte pública.
- ❌ Usar número que o dossiê marca com ⚠, ou escolher entre dois números divergentes.
- ❌ Usar no documento do mentor algo que o founder disse em mentoria com outro mentor.
- ❌ Completar a tabela de resumo com linha que não muda nada, só para dar seis ou oito.
- ❌ Propor três temas.
- ❌ Usar jargão vazio: sinergia, ecossistema de inovação, jornada transformadora, empoderar,
  trajetória brilhante, referência no mercado.
