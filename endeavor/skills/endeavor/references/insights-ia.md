# Insights das mentorias coletivas de IA

Base de conhecimento destilada de 10 encontros da trilha de IA das mentorias coletivas da
Endeavor, com founders, CHROs, CTOs e pesquisadores. Organizada em 12 temas, em formato de
pergunta e resposta.

**Material anonimizado**: sem nomes de pessoas, empresas, produtos proprietários ou números
identificáveis. Os números que restaram são ordens de grandeza. Quando duas pessoas
discordaram, as duas visões estão registradas.

## 01. Por onde começar

### Onde eu coloco o primeiro projeto de IA?

**No core. Onde dói e onde é crítico.**

O padrão de fracasso mais comum em empresas grandes é começar pelo periférico, exatamente porque dá medo: "vamos usar IA para deixar o processo administrativo mais eficiente". Ninguém olha, ninguém se importa, e o projeto morre por irrelevância.

Uma empresa que atravessou isso colocou agentes falando diretamente com o cliente na primeira interação de atendimento — "ou funciona ou morre". Justamente por ser crítico, a organização inteira teve que olhar. Quando funcionou, a IA permeou naturalmente para o resto.

> Se funcionou na coisa mais importante, sabemos que é válido.

O contraexemplo é igualmente instrutivo: uma empresa grande contratou um fornecedor de IA e entregou a ele a lista de leads mortos "que ninguém consegue vender". Se é para ser motor de receita, precisa receber lead core e ter um C-level como dono.

### Devo transformar a operação existente ou criar algo apartado do zero?

Essa é literalmente a mesma discussão do começo do e-commerce e dos bancos digitais: o varejista tinha que se transformar ou criar uma marca nova? **Nunca houve estudo conclusivo, e há casos de sucesso dos dois lados.**

O que é fato: qualquer iniciativa que começa do zero nasce com uma lógica muito mais centrada em IA. A grande maioria das empresas hoje está apenas automatizando processos existentes — o equivalente a usar o chat como um buscador melhorado. Você está acessando IA, mas não é fluente em IA.

Empresas que redesenham os processos com IA no centro capturam muito mais valor. A pergunta prática é se você consegue fazer isso por dentro.

### Qual é o erro de sequenciamento mais caro?

**Começar pela eficiência em vez de terminar nela.**

É fácil demais a conversa virar custo. Você entrega ganho de eficiência em um ano, comemora, e um ano depois descobre que a sua área continua não operando com IA no centro — você só fez o velho mais rápido.

**[A sequência correta]** Entenda o processo → repense o processo com IA no centro → **a eficiência é o output**, não o ponto de partida.

Um estudo com dezenas de implementações bem-sucedidas encontrou o mesmo padrão: cerca de um terço dos projetos automatiza o que já era feito (incremental), um terço faz transformações mais profundas, e muito poucos fazem a pergunta certa — *"se eu não tivesse nenhuma bagagem nem restrição, como eu redesenharia esse processo do zero?"*. É aí que está a transformação, e quase ninguém chegou lá. Cerca de 90% dos projetos mapeados focavam redução de custo.

Por que quase todo mundo escolhe custo? Porque exige esforço cognitivo muito menor fazer mais rápido o que você já faz do que se reinventar.

### Automatizar um processo ruim resolve?

Não. Piora.

O caso mais didático veio de uma operação logística de grande porte: dezenas de milhares de notas fiscais de manutenção por ano, um problema aparentemente óbvio de leitura automatizada. Falhou feio. Em anos de operação, a taxonomia de classificação tinha virado um Frankenstein — a mesma coisa chamada de três jeitos, contas contábeis duplicadas, e sempre um humano no fim harmonizando tudo. A IA não tem essa visão e classifica com o que está disponível.

**O que era ruim ficou pior: tiveram que dobrar o time para corrigir os erros da IA.**

A solução não foi tecnológica. Simplificaram a taxonomia e reduziram os modelos de nota quase pela metade. Só isso fez o projeto funcionar.

A lição de orçamento: todo projeto estima desenvolvimento, token e infraestrutura. Quase nenhum estima que **o seu processo não está pronto para receber a tecnologia**.

### Vale tentar fazer o data lake único da empresa inteira antes de começar?

Na teoria é o ideal. Na prática trava.

Você fica sem dono; e mesmo com dono, há requisitos conflitantes por área — quem pode ver dado de pessoas versus jurídico versus financeiro, qual é a governança, como tudo se conversa. Vira um problema de engenharia muito mais complexo do que parecia.

O que se vê funcionando: o CEO chama os seis liderados diretos e cada um cria o seu. Cada área com sua própria camada, sua própria biblioteca, seus próprios dados. É menos elegante e infinitamente mais rápido.

### Existe diferença entre implantar IA numa empresa de 100 pessoas e numa de milhares?

Sim, e o time pequeno leva vantagem — mas não pelo motivo óbvio.

Num time pequeno não existe processo nem "eu sou do comercial, eu sou do negócio". Sair do quadrado mental é mais fácil. Em escala, a mesma mudança de mentalidade vira manifesto, comunicação interna, bootcamp para centenas e depois para milhares.

Mas o alerta importante é outro: **o playbook não é transferível sem adaptação.** Uma empresa comparou a própria jornada com a de uma empresa irmã de porte médio. Lá, a infraestrutura de dados não estava curada nem integrada — e isso mudou completamente o que era possível fazer. A qualidade da infra determina quanto do playbook você consegue rodar.

### Como destravar uma empresa que está no nível zero, com sócios sem nenhum interesse no tema?

Sem meias palavras: **se a liderança não está comprada, nenhum fornecedor e nenhuma apresentação convencem.** Já tem gente demais no mercado falando; falar mais não muda ninguém.

O que funciona é conectar a um objetivo de negócio que já existe. Muitas empresas já têm uma meta de receita por colaborador. A IA entra como uma alavanca para chegar lá. Sem uma meta explícita — "estou em X, quero chegar em Y" — não sai do lugar.

E o que realmente destrava não é gradual: é um estalo. Costuma acontecer numa reunião de liderança do tipo "é isso ou é isso; quem está a fim vem". A partir daí a conversa da organização muda de *"será que eu me adapto?"* para *"como eu me adapto?"*.

## 02. O papel de quem lidera

### Posso delegar a transformação de IA para um squad abaixo do CTO?

Não. E essa foi provavelmente a resposta mais repetida em todos os encontros.

> Não dá para delegar uma mudança tecnológica dessa ordem. Tem que aprender, tem que se atualizar e tem que dominar cada aspecto.

Quem falou isso apresentou o projeto ao board, colocou no próprio orçamento e assumiu como owner.

Um estudo de dezenas de implementações separou patrocínio **ativo** de **passivo** e encontrou aí a variável que mais separa sucesso de fracasso:

- **Passivo:** "eu apoio o projeto" e delega para TI.
- **Ativo:** o projeto é liderado no nível do CEO, com prioridades de negócio explícitas.

O contraste concreto: um grande banco global onde o CEO diz publicamente que IA é existencial e lidera os projetos pessoalmente — versus uma grande empresa tradicional com muitos projetos de IA, todos tocados pelo departamento de TI, com desalinhamento visível entre CEO, CFO, vendas e TI sentados na mesma sala.

### O que significa "mão na massa" para um C-level, na prática?

Não significa virar engenheiro de dados nem treinar modelos. Significa **usar a ferramenta para mudar o próprio dia a dia**.

- Um líder trocou 30-40 minutos diários olhando dashboards por um orquestrador de sete ou oito agentes que sinaliza só os desvios que importam.
- Um founder passou duas horas por noite durante cinco dias e chegou na reunião com o roadmap trimestral inteiro de um time de dez pessoas já entregue. *"Depois disso ele desafia tudo."*
- Um sócio que não programava havia duas décadas construiu sozinho um módulo inteiro de integração.

### Quanto tempo um líder precisa dedicar a se atualizar?

O número mais citado por quem está na fronteira: **no mínimo uma hora por dia, todos os dias.** E estudar de verdade.

> Quanto mais você estuda e aprende sobre o assunto, mais você tem a sensação de que não sabe nada.

A prática que sustenta o ritmo do time junto: levar para a reunião semanal um exemplo novo aprendido na semana — **relevante para eles, não para você**. Isso obriga o líder a estudar mais e transforma a atualização num hábito coletivo.

### Como a liderança sustenta a transformação sem paralisar o time?

Como toda grande transformação carrega risco, é essencial que a liderança demonstre que está **no mesmo barco, correndo o mesmo risco e encarando junto**. Senão ninguém se mexe.

E há um cuidado específico: parte das conversas — o medo individual, a dúvida sobre o próprio futuro — só pode ser resolvida no nível individual, nunca em escala de empresa. Por isso tudo depende da camada de liderança direta. Os comportamentos esperados de um líder numa dessas empresas incluem *"construa um time melhor que você"* e *"seja paranoico: seu time precisará ainda mais de você"*.

### Qual é a pergunta que os founders não estão se fazendo?

> Em que eu quero e preciso gastar meu tempo, que só eu posso fazer?

Com essa resposta você sabe o que delegar. E só a partir do que precisa ser delegado é que você sabe o que contratar. Sem ela, você contrata para preencher caixas de organograma.

### Devo montar a organização a partir das caixas ou a partir das pessoas?

A resposta convencional é: monte as caixas, depois encaixe as pessoas.

Uma founder com dez anos de escala declarou o contrário:

> Eu não acredito mais nisso. A organização são as pessoas.

Descubra no que cada um é bom, no que você é bom, e desenhe a organização dos próximos 18 meses a partir disso combinado com quem você consegue trazer. As caixas nunca são ideais. Às vezes você nem precisa delas — você tem um cargo só porque "é o que se espera ter".

## 03. Cultura, medo e comunicação

### Por que a IA gera mais resistência do que outras inovações?

Um profissional com décadas de carreira em inovação foi categórico: *"nunca vi um tema com carga tão negativa para as pessoas."*

São duas coisas somadas:

1. **Medo de ser substituído** — real e legítimo.
2. **Síndrome de complexidade percebida** — você acha que é complicado demais, e é. E quanto mais estuda, mais complicado fica.

O efeito combinado é congelamento. Fora dos early adopters de sempre, quem não tem ímpeto natural simplesmente trava. É exatamente por isso que o papel da liderança pesa mais aqui do que em qualquer ciclo anterior.

### Como comunicar a mudança sem perder o time?

O padrão que funcionou numa empresa que reduziu drasticamente o quadro **sem perder ninguém no processo** foi comunicação radicalmente transparente e antecipada:

> Tudo vai mudar. Mas eu vou te ajudar a chegar do outro lado, e você vai ser líder das próximas empresas.

E o que deu credibilidade à mensagem não foi o discurso: foi investir pesado em formação **em vez de** cortar. Comprar o melhor curso disponível para todo mundo, gastar dinheiro de verdade. *"Se as pessoas estão preocupadas que você vai cortar todo mundo, invista nelas."*

### A transparência total pode virar um problema?

Sim — e este foi um dos aprendizados mais honestos do conjunto.

Uma empresa comunicou a transformação com tanta clareza e urgência que gerou **medo acima do desejável**. A liderança percebeu tarde. A correção não foi suavizar a verdade: foi **contar o outro lado com a mesma clareza**.

O que estava faltando: casos reais de reskilling, histórias concretas de mobilidade interna de pessoas que vieram de áreas desmobilizadas, o quanto a empresa acredita na capacidade de as pessoas se reposicionarem.

> Não é que deixa de ter a queda. Mas amortece.

O diagnóstico externo, de outro founder na mesma conversa, foi que não existe alternativa melhor à transparência — o desconforto é resultado da mudança, não da comunicação. O ajuste é de nuance, não de fundamento.

### Cultura de permissão ao erro é bônus ou pré-requisito?

Pré-requisito. Culturas que penalizam o erro geram comportamento avesso a risco, e isso é incompatível com projetos de IA.

Praticamente todos os casos bem-sucedidos estudados **falharam pelo menos uma vez antes de funcionar**.

Exemplo: uma solução global de recrutamento em dezenas de idiomas (divulgação, triagem, primeira entrevista em vídeo). A primeira versão falhou porque herdou os vieses dos recrutadores locais. Descobrir quais parâmetros excluir leva tempo. Como falhar não era problema, a segunda versão funcionou.

**[O corolário técnico]** **Quase sempre a métrica piora antes de melhorar** quando um modelo novo entra em produção. *"Se você faz melhoria de 0,1% nunca vai encontrar o caminho novo."* Uma equipe brinca que o número mágico é a **versão 11** — vários casos de uso só deram certo na décima primeira tentativa. E a maturidade que acompanha isso é saber matar o projeto na versão 2, 3 ou 6 quando o sinal não aparece. Mostrar só o que deu certo enviesa a própria liderança.

### Qual é a expectativa realista de prazo?

Não é mais o projeto de TI de 18 meses. Mesmo que a jornada inteira seja longa, **a mensurabilidade tem que ser em dias e semanas**: voltamos, vemos o que fizemos, o que aprendemos, como ajustamos.

Esse desalinhamento de expectativa entre quem provê a tecnologia e quem compra foi apontado como um dos maiores pontos de fricção do mercado.

### Como enquadrar emocionalmente a jornada para o time e para si mesmo?

O melhor enquadramento oferecido: **trate a transformação interna como uma sequência de product launches.**

O founder já sabe operar assim. Fundou a empresa com um MVP quebrado, saindo torto, e sempre teve na cabeça que aquilo era o V0 — depois viria o V1, o V2, o V3. É a mesma coisa aqui: *"estou lançando o V0 do nosso jeito de operar, e já estou animado com o próximo lançamento."*

A empresa é que não tem esse repertório. Ela quer garantir que a coisa funcione antes de soltar. O trabalho do founder é propagar a mentalidade de lançar, quebrar e iterar.

### O que responder para quem pergunta "e o que a IA não faz?"

Este é um tema delicado, porque ao levantar essa bandeira parece que você está puxando o freio de mão.

O caminho relatado tem três camadas:

1. **Pela liderança direta** — dar clareza do que a pessoa precisa melhorar, suportar a mudança, suportar o upskilling. É onde a conversa individual acontece.
2. **Por clareza institucional** — a pessoa tem feedback, tem ferramenta, tem verba de desenvolvimento e sabe o que a empresa espera. Isso tira todo mundo do limbo do "é, não é".
3. **Por presença na ponta** — time de pessoas em contato próximo com os times, gerando simetria de informação.

## 04. Adoção e capacitação

### Devo tornar o uso de IA obrigatório?

Duas escolas apareceram, e as duas funcionaram — com custos diferentes.

**[Escola do atrito inteligente]** Uma empresa **não** tornou obrigatório. Criou fricção: quando um engenheiro fecha uma entrega sem ter usado agente, o sistema pergunta no canal interno *"percebemos que você não usou o agente — pode explicar em poucas palavras por que esse código se beneficiou de ser feito à mão?"*. Só o ato de precisar justificar criou o awareness necessário. **A adoção foi de zero a cerca de 85% sem nenhuma obrigatoriedade formal.**

**[Escola do choque]** Outra empresa anunciou numa quarta-feira que todo mundo teria que construir o próprio agente pessoal. Na semana seguinte, reuniões foram praticamente proibidas — não dava nem para marcar no calendário. Prazo: domingo. Na segunda já havia dashboard por pessoa com consumo de token e comparação com os pares. A avaliação de quem viveu: **o incentivo claro funcionou; a velocidade foi excessiva.** Muita gente surtou, houve casos de burnout.

O ponto comum: o incentivo explícito é o que move. A calibragem da velocidade é onde se perde ou se ganha o time.

### Faz sentido colocar uma meta de "X agentes criados"?

Faz — desde que você saiba que a métrica é um proxy e esteja pronto para trocá-la.

Uma empresa colocou a meta de um agente por colaborador. Foi criticada internamente como "meta pela meta". A defesa: a métrica não é o agente, é **adoção, aprendizado e quebra de inércia**. A justificativa do líder técnico foi elegante: *"este não é o momento de métricas perfeitas para fazer análise. É o momento de pegar o feeling se as coisas estão funcionando."*

Resultado: a meta foi superada em várias vezes. E a análise posterior foi honesta:

| Faixa | O que são |
|---|---|
| **~85%** | Lixo. Repetidos, baixa qualidade, utilidade mínima. |
| **~13%** | Bons. Mais de uma pessoa usa; ganho da ordem de 20h/mês. |
| **~1,5%** | Mudam o ponteiro. Altíssimo uso e impacto real. |

> Trinta mil agentes é melhor que zero, mas duzentos é melhor que trinta mil.

A fase seguinte deixou de ser criar e virou curar — encontrar os poucos estruturantes. E depois nem isso: virou *"quais são as skills que mudam a organização"*.

**A correção de rota que importa:** a métrica inicial era "criar agente", e as pessoas começaram a criar agente por criar. Trocaram rapidamente para **agente ativo** — criado e efetivamente em uso.

### Existe um efeito colateral positivo de gerar milhares de agentes ruins?

Sim, e ninguém tinha previsto.

Aqueles milhares de agentes **codificaram processos que nunca estiveram documentados**. Agora existe um sinal riquíssimo de onde está o valor: que ferramenta cada área integrou, para que tipo de tarefa, quantas vezes por dia. E os agentes estruturantes conseguem conversar com esse acervo.

Ou seja: o desperdício aparente virou o mapa de processos que a empresa nunca teve.

### Workshop ou bootcamp?

Workshop é bom e barato: uma live de uma hora e meia, com 45 minutos de conteúdo prático de alguém que domina o tema e sabe explicar, e 45 minutos de perguntas.

**Bootcamp é o que muda o ponteiro:** uma hora de conceito e **seis horas construindo soluções para problemas reais da área**, com o time inteiro.

O ganho principal do bootcamp não é o conteúdo. É **forçar a alocação de tempo**. O feedback mais recorrente em qualquer empresa é *"vocês dão mil coisas, mas eu não tenho tempo"*. Uma empresa saiu de "líderes, organizem-se por área" para calendarizar os bootcamps de forma impositiva justamente por isso.

> No primeiro bootcamp do time técnico, um em cada cinco engenheiros nunca tinha aberto a ferramenta. A visão da liderança estava enviesada pelos bons cases.

### O que faz um treinamento realmente pegar?

**Dever de casa real, apresentado e implementado.**

Uma academia interna de um a dois meses (varia por nível) exige que a pessoa apresente toda semana o que fez, defenda diante de um comitê no fim, e **implemente**. O trabalho tem que ter melhorado o próprio trabalho e a própria produtividade.

Isso resolve, de quebra, a pergunta de "como eu meço quem realmente adotou" — quem não fez, não apresenta.

Outra empresa desenhou o curso interno em três níveis de oito semanas: básico e ferramentas; construção de workflows; construção de agentes. Ao fim do primeiro nível, cada pessoa precisava apresentar uma automação — do próprio trabalho ou de uma dor do cliente.

### Qual é o melhor ritual de entrada para quem nunca tocou no assunto?

Fazer a pessoa **construir um joguinho** com um prompt de três ou quatro linhas. Tipo o jogo da cobrinha dos celulares antigos.

Não é sobre o jogo. É o clique de *"era inimaginável eu fazer isso, e abriu uma porteira que eu não imaginava"*. Uma empresa começa todos os treinamentos assim.

### O time de tecnologia deve construir os agentes para as outras áreas?

**Não vai funcionar. Ninguém vai usar.**

A analogia usada foi o CRM: raríssima é a empresa em que o time comercial alimenta bem o CRM — justamente porque não foi criado por eles. Empresas maiores e mais tradicionais estão colocando o time de tecnologia para criar agentes para todas as outras áreas, e isso não vai pegar.

**Mas o contraponto honesto, do mesmo interlocutor:** não tenha a ilusão de que basta dar incentivo e a área jurídica vai construir sozinha. *"Eu me considero íntimo do tema e levei três dias em tempo integral, com toda a infraestrutura e os cursos da empresa, para montar meu próprio agente."* Não é simples.

O equilíbrio que emergiu: a área constrói, mas com um time técnico circulando para desbloquear, e com ferramental no-code que reduza a barreira de entrada.

### Como escolher quem vai puxar a adoção dentro de cada área?

Não é o mais sênior nem o mais técnico. Procure quem já está **inconformado com o jeito atual de trabalhar** — dentro da área onde a solução vai ser implantada, não em tecnologia.

Um estudo separou isso na linguagem mais simples possível: distinga os *"yes, but"* dos *"why not"*. Ache os "why not". Essa pessoa vira embaixadora dentro da área dela.

O caso concreto mais replicável: numa empresa, uma pessoa **nem sênior nem a melhor tecnicamente**, mas ótima de comunicação e muito acessível, virou evangelista espontânea. Ela transformava as dúvidas que recebia em pílulas de vídeo de três a dez minutos. Isso foi institucionalizado como um modelo de **multiplicadores por área** — e são eles que conduzem os bootcamps hoje.

A lógica por trás: existem microbarreiras no início que geram fricção enorme. Remover a barreira dá um salto absurdo.

### Como dar palco para o comportamento certo?

Numa empresa, o CEO premiava semanalmente os melhores projetos de IA chamando ao palco **os sponsors da área de negócio** — não o time que desenvolveu. O time importa, claro, mas o comportamento que precisa ser recompensado publicamente é o de abraçar a mudança.

Em outra, o mecanismo foi diferente e igualmente potente: um analista de uma área de negócio, sem recurso de tecnologia disponível e sem prioridade na fila, construiu um relatório automatizado para si mesmo. Foi melhorando, o time adotou, e meses depois o CEO olhava aquilo todo dia. Ele foi convidado a contar o caso na reunião mensal da empresa. No mês seguinte, outra pessoa contou o dela.

> A mensagem que se espalhou não foi "use IA". Foi: se você se virar, você resolve o seu problema e o do time inteiro — e isso é seu para sempre.

### Por que os sêniores adotam menos que os juniores?

Porque os juniores fazem o dever de casa e os sêniores dizem que não têm tempo.

O relato foi direto: *"os juniors acabaram de sair da faculdade, vivem com tecnologia, ainda acreditam em fazer o dever de casa — e fizeram. Os sêniores disseram: eu tenho uma operação de 400 pessoas, não tenho tempo para dever de casa."*

O resultado foi que pessoas de 22 a 24 anos passaram a saber mais sobre a operação e a estar mais perto do cliente do que a camada sênior. O CEO passou a pular níveis e conversar direto com elas — porque a explicação do sênior vinha adocicada. Alguns sêniores acabaram saindo.

**Treinar e converter sêniores é muito mais difícil do que juniores**, exige treinamento contínuo e conversas duras. E vale saber disso antes de desenhar o programa.

### Como criar tração no meio da organização (o middle management)?

Mexer em OKR e meta para colocar todo mundo no mesmo barco: o sucesso do projeto impacta **bônus e carreira**. "Se você quer progredir e ter mais oportunidade, este é um dos projetos de que você quer fazer parte."

E lembrar que o conhecimento que faz o projeto funcionar está na cabeça de **quem executa o processo todo dia**. Não está com o CEO, nem com o diretor, nem com tecnologia. Se você não envolve essa pessoa, ou você perde, ou você constrói uma solução que não encaixa.

O contraponto honesto: essa mesma pessoa às vezes não levanta a mão porque teme pelo próprio emprego, e nem sempre existe incentivo para superar esse medo. Programas de "champions" ajudam a dar visibilidade a quem quer mudar, independentemente de hierarquia.

## 05. Estrutura e desenho organizacional

### Existe uma escala de maturidade organizacional em IA?

Sim, e a mais tangível que apareceu tem cinco níveis. O impacto cresce exponencialmente a cada degrau.

| Nível | O que é | O que trava |
|---|---|---|
| **1 — Produtividade individual** | Libera a ferramenta para todos. Quem já era bom fica muito bom. | Abre uma arbitragem enorme entre pessoas. É onde a maioria está. |
| **2 — Produtividade organizacional** | Biblioteca compartilhada de skills e agentes: a melhoria de um propaga para todos. | Sprawl de agentes e soluções desconectadas. |
| **3 — Sistema operacional** | Um harness único com camada de dados por trás. Sai de otimização local para global. | Cai a dependência de gente operacional, mas você ainda não delega a *decisão*. |
| **4 — Motor de recomendação + o "juiz"** | Modelos que recomendam a decisão. Surge o humano que diz "essa está certa, essa está errada". | Padroniza **eficácia**, não só produtividade. Duas pessoas tomam a mesma decisão. |
| **5 — Loop fechado** | A máquina aprende sozinha e supera o melhor humano. | Aspiracional. |

**Diagnóstico de quem atende cerca de duzentas empresas: a maioria está travada no nível 2.**

Um exemplo tangível do nível 4: recrutadores diferentes davam ofertas salariais diferentes para o mesmo perfil. Quem está certo? Não é fácil dizer, mas é objetivo que um está sendo menos eficaz — pagando acima ou abaixo. Um modelo passou a dizer qual é a oferta ideal, e uma pessoa passou a ser o juiz que corrige o modelo.

### Qual é o maior bottleneck para sair do nível 2 para o 3?

**Incentivo perverso.**

Cobrar "número de agentes criados" ou "consumo de tokens" é pouco systems thinking. Se você cobra "faça agentes", a pessoa faz agentes. **Se você cobra "toque um time de dez com uma pessoa", ela descobre sozinha que precisa de dados estruturados e de uma camada de recomendação.**

O sintoma mais claro disso: o cargo mais disputado no mercado hoje é **engenheiro de dados / DevOps** — e é exatamente quem menos é chamado nas conversas sobre "criar agentes".

### Quais mudanças estruturais aparecem nas empresas mais avançadas?

Cinco padrões, sempre juntos:

1. **Menos camadas** — a pirâmide vira diamante. Empresas de cerca de 500 pessoas operando com três camadas.
2. **Span of control maior** — dez ou mais reportes diretos.
3. **Pessoas mais sêniores.**
4. **Menos gestores puros de pessoas.**
5. **Mais autonomia individual.**

Eles são interdependentes: você só sustenta span alto com pessoas muito boas; e você só consegue ter só pessoas muito boas quando precisa de um terço do headcount.

### Por que span of control alto é bom? Não sobrecarrega o líder?

O argumento é contraintuitivo e vale internalizar.

Com quatro reportes, o líder **compensa** o trabalho do colaborador mediano — ele vai lá, ajusta e entrega. Com doze, ele não tem tempo nem energia para isso. **O incentivo dele vira remover quem não performa.**

E há o outro lado: span alto reduz drasticamente o custo de comunicação e favorece justamente as pessoas que não precisam de alto grau de gestão porque são muito boas sozinhas.

> Você só sobrevive como líder com span alto se as pessoas abaixo de você forem muito boas.

### Mas um líder com span de dez consegue priorizar cinco contextos diferentes?

Essa foi a objeção mais forte levantada — e é experiência empírica de vários founders: quando um gestor sai de dois para três contextos, a coisa já complica; ele não consegue carregar contexto suficiente na cabeça, e as interações (síncronas e assíncronas) crescem muito. A pessoa estrangula.

A resposta: se o líder precisa priorizar e definir os três assuntos, **muito provavelmente as pessoas abaixo não têm autonomia ou competência para decidir**. Num cenário em que a pessoa chega e diz "vou fazer isso, isso e aquilo, desse jeito" e está certa em 90% das vezes, o líder não precisa adaptar — ele vira orquestrador, não alguém que entra no detalhe de cada coisa.

Não há bala de prata. É gradual. Onde funcionou, começaram pegando pessoas muito boas e líderes ótimos e migrando reportes para eles primeiro — porque gerir alguém excelente é fácil.

### Squads de duas ou três pessoas funcionam mesmo?

Sim, e apareceram em várias empresas independentemente.

- **Formato relatado:** um squad de duas pessoas substituindo squads de doze a quatorze (produto, design, research, back, front, SRE, analytics). Ambas as pessoas constroem; uma fica mais na frente do cliente.
- **Continuidade em férias?** Resolvido com um pool de generalistas que roda entre os times — e eles ficam muito bons justamente porque circulam.
- **Variação com trio:** processo + IA + negócio numa esteira que entrega ganho incremental a cada quinze dias.
- **Variação com orçamento:** uma empresa reorganizou tudo em cerca de vinte squads que funcionam como startups, com tudo o que precisam e um **teto de orçamento**. Sem poder contratar para escalar, o time é obrigado a usar IA para bater a meta.

### Como conduzir a redução de time sem trauma?

O padrão mais consistente entre quem já está adiantado: **layoff silencioso — simplesmente parar de contratar.**

Só não executar o plano de headcount já muda drasticamente onde você estaria no fim do ano. Se você ia crescer de 400 para 500, ficar em 400 já é uma redução relativa enorme. O turnover natural faz o resto, e você retém os melhores performers.

Observação afiada: as empresas que **anunciam** corte grande "por causa de IA" em geral não estão adiantadas — é uma forma de estressar o time para acelerar. Isso tem seu mérito como choque, mas não confunda com maturidade.

**[A execução que menos machucou]** - Não houve um grande anúncio. Aconteceu em fases.
- Em times de alta rotatividade natural, não houve corte massivo: as pessoas saem de qualquer jeito, e **os melhores passaram a gerenciar os agentes**.
- O enquadramento individual foi: *"este processo agora é mais eficiente. Você quer ajudar a torná-lo melhor? Quer uma oportunidade em outra coisa? Quer usar IA para fazer isso?"* — e a pessoa decide.
- Muita **contratação interna** rodando em paralelo à reorganização.
- Posicionamento cultural: "queremos ser pioneiros nisso e queremos todo mundo no barco" — em vez de "agora você vai perder o emprego".

E o congelamento de contratação como ferramenta recorrente: uma empresa faz isso ciclicamente, a cada dois anos, **justamente porque força a criatividade**. Se não, todo mundo resolve tudo com mais gente, que é a solução fácil.

### Qual é o custo real de resolver problemas contratando gente?

O relato mais visceral do conjunto veio de quem saiu de algumas centenas para mais de dez mil pessoas em cerca de um ano e meio.

O que aconteceu: não havia computador para todo mundo; **literalmente perdiam pessoas** — não se sabia se o novo contratado tinha aparecido no primeiro dia, com quem falaria, quem seria o gestor. Gente com duas semanas de casa tomando decisão de contratação sobre problemas que não entendia.

**[Os cinco sintomas]** 1. **Todo mundo perde contato com o cliente**, inclusive os founders. Cada um cuida da própria caixinha porque não consegue mais olhar o quadro inteiro.
2. **Silos**, e dentro deles cada um construindo em direção diferente da visão.
3. **Meta-jobs** — tarefas que não são importantes, mas que a pessoa começa a fazer para justificar que está trabalhando. E aquele trabalho aleatório passa a exigir mais gente e mais tecnologia para sustentá-lo.
4. **Cost creep** — todo mundo contratando e comprando tecnologia para as próprias coisas.
5. **Ego** — líderes querendo provar que são o chefe da sala em vez de resolver o problema.

E do lado do cliente: *"eu já contei o problema para vocês, e agora dez pessoas diferentes me ligam e eu tenho que contar de novo — e ninguém resolve."*

O efeito estrutural mais perverso: **quando você cascateia uma visão, ela não chega em quem opera**, porque há camadas demais no meio.

Depois de três ou quatro anos de reorganizações sucessivas, a empresa está com cerca de um terço daquele pico — e ainda quer menos. *"Quanto mais gente, mais complexo por dentro, e isso não beneficia o cliente."*

### Quantas pessoas deveria ter o C-level?

Uma empresa já teve quatorze. O período mais produtivo e bem-sucedido foi com **três ou quatro pessoas** no núcleo de decisão — gente que fala o tempo todo, decide rápido e move a organização.

Passou disso: fica mais lento, nem todo mundo recebe a mesma mensagem, e as pessoas passam a brigar por território em vez de entregar.

### A lógica atual de organograma ainda faz sentido?

Provocação que ficou sem resposta e vale carregar: toda a nossa lógica de hierarquia vem do exército romano — o chefe conseguia falar com no máximo oito pessoas, e daí veio o span de oito.

> Faz sentido criar os agentes replicando as áreas que existem hoje? Ou existe uma forma muito mais inteligente de organizar a empresa? Não sabemos. Estamos testando.

### Que experimentos organizacionais estão sendo rodados agora?

Vale roubar a lista, porque são experimentos baratos e reversíveis:

- **Super IC** — pegar uma pessoa sênior, tirar o time dela, dar ferramenta ilimitada e um problema complexo. Resolva sem time.
- **Quebra de squad** — squads de seis viram dois de três, com a meta de dobrar a entrega.
- **Span inflado** — pegar um time com span esperado de sete e colocar quinze, para ver o efeito.
- **Roadmap comprimido** — um time inteiro tentando entregar um roadmap semestral em uma semana.
- **Troca de vaga por token** — substituir a contratação pelo orçamento equivalente de uso.
- **Redução dirigida** — reduzir um time de nove para duas pessoas fazendo o mesmo trabalho.
- **Papéis cruzados** — PMs commitando código.

*"Vai dar certo? Não sei. Mas vamos experimentar."*

## 06. Talento, carreira e avaliação

### Como detectar que um líder está adiando uma decisão difícil sobre o time dele?

Dois testes rápidos, e são brilhantes:

**[Teste 1 — o organograma no tempo]** Peça as versões do organograma dos últimos dois anos e olhe o movimento das caixas. Se responsabilidade sai do executivo 2 e vai para o executivo 1, e seis meses depois sai do executivo 3 e vai também para o 1 — pergunte por quê. É porque não está entregando? Porque você não confia? Às vezes há razão legítima. Mas quase sempre é porque **você não quis ter a conversa**. É mais fácil transferir para quem entrega e chamar de "mudança organizacional" — ninguém nem pergunta. Só que você adia o problema e ainda cria outro: o executivo 1 vai queimar.

**[Teste 2 — a lista de contatos]** Com quem essa pessoa realmente fala? Todos já passamos por isso. Alguém no time não está agregando, e a gente simplesmente **para de falar com essa pessoa** e passa o tempo com quem está construindo. A pessoa fica isolada, faz o que quer, recebe projetos aleatórios sem sentido.

> Se eu não quero passar tempo com essa pessoa, é porque não consigo construir com ela. Esse é o problema de verdade.

### E quando a pessoa entrega bem mas não está alinhada com a cultura?

É a conversa mais adiada de todas — em anos, não em meses.

O caso relatado: performance excelente, mas conflito com a empresa inteira, tratando mal o próprio time. Todo mundo identificou. Ninguém quis decidir porque a pessoa performava e não havia substituto óbvio. Quando finalmente saiu, o custo já era altíssimo: nada se movia porque ninguém queria falar com ela, e a cultura quebrada ainda estava sendo consertada anos depois.

Como detectar cedo: **você percebe rápido, você só não quer confiar no instinto.** Quem está na área de pessoas costuma ver primeiro, justamente porque não é tratado como founder — é tratado como "o RH que resolve papelada". Isso revela traços que ninguém mais vê: o que a pessoa pergunta, como trata o seu time, quão egocêntrica é quando não quer assinar algo.

*"Passei a confiar nesse instinto mais cedo e a levar essas conversas para o resto do C-level."*

### Que perfil sobrevive à transição?

Três leituras convergentes, ditas por pessoas diferentes:

**Capacidade de desaprender.** *"A característica que eu mais olho hoje nas pessoas não é a capacidade de aprender — é a capacidade de desaprender."* Porque coisas inteiras deixaram de ser válidas.

**Curiosidade somada a profundidade.** O analista do futuro não "cospe dashboards"; extrai a análise. Excesso de informação virou problema real — a pessoa manda o dashboard e ninguém sabe o que fazer com ele.

**Agência acima de domínio.** Uma empresa descobriu que era mais fácil ensinar o domínio (RH, finanças) para alguém com alta agência e systems thinking do que ensinar agência para um especialista. Perfil de domínio profundo sem capacidade de construir vai perdendo espaço.

E um sinal de contratação concreto, citado por um founder: **engenheiro que constrói projetos sozinho, por hobby, em casa.**

### O que muda em quem é considerado "gente crítica" na empresa?

Muda rápido, e as ferramentas de RH são lentas demais para acompanhar.

Numa empresa, os finalistas de uma competição interna de agentes foram olhados individualmente no ciclo de mérito e de stock options. O racional: *"um ano atrás essas pessoas passariam despercebidas. Hoje elas estão pivotando a empresa."*

Outro exemplo da mesma casa: o diretor de segurança da informação ficou drasticamente mais crítico em seis meses.

**O problema estrutural:** até o comitê de calibração concluir formalmente que alguém virou crítico, a pessoa já está em outra empresa. A solução foi antecipar-se ao processo formal em vez de esperar por ele.

### Como está funcionando a avaliação de desempenho com IA como critério?

O que funciona é **avisar com um ano de antecedência**.

Uma empresa declarou publicamente, para a organização inteira, que o uso de IA seria critério de contratação e de avaliação — e só avaliou de fato doze meses depois. O valor disso é tornar indiscutível a conversa que vem: *"eu te avisei há doze meses, te dei curso, verba, ferramenta e clareza."* É radicalmente diferente de avaliar retroativamente algo que nunca foi combinado.

O resultado da primeira rodada foi surpreendente: **94% das pessoas se autoavaliaram como "na rota ou acima"** em IA. Na visão dos líderes, 75% — ainda alto demais.

> A curva que vocês estão usando está errada. A régua certa é que estamos atrasados. Se você se avaliou voando alto, repense.

Insumos usados pela liderança para a nota: criação de agentes, uso de ferramenta, participação em workshop, e o julgamento qualitativo de quem foi multiplicador e referência para o time. A nota impacta a remuneração variável de forma indireta.

### Alguém decifrou como avaliar performance nesse contexto?

Não — e o depoimento mais honesto do conjunto foi exatamente esse: *"se alguém decifrar isso, me conta."*

O que foi tentado e falhou:

- **Avaliação de cima para baixo pelo líder.** Todo mundo acha que o próprio time é rockstar. Resultado: uma organização inteira que se considera excelente e não bate os números.
- **Avaliação pelo C-level.** Eles não sabem o que os times estão tentando realizar. Outra bagunça.
- **360 graus.** Virou caça às bruxas. Passou a ser usado como atalho para tirar alguém da organização — "faz um 360 nessa pessoa" porque o líder já queria a justificativa. Virou instrumento de medo.
- **Matriz de competências.** Descrita como puro desperdício de tempo, com o melhor argumento do conjunto: quem constrói coisas normalmente **superdesenvolveu uma ou duas habilidades** e não é grande coisa nas outras — e são essas uma ou duas que compensam todo o resto. A matriz coloca uma lupa exatamente no que a pessoa não faz bem, e a organização passa a olhar essa pessoa de outro jeito. *"Ela continua sendo boa naquilo. Por que eu quero fazer ela virar boa nesta outra coisa? Não importa."*

Onde estão hoje: tentando ancorar em KPIs, mas cascatear KPI até o nível individual é dificílimo. Achado contraintuitivo: **KPIs coletivos às vezes funcionam melhor que os individuais.**

### O que fazer com título e promoção quando os papéis mudam tão rápido?

O diagnóstico: quando se institucionalizou promoção e título, as pessoas passaram a gastar tempo demais discutindo se deveriam ser diretor ou VP em vez de perseguir a missão. E o erro se acumulou: promoveram gente cedo demais, e contrataram gente em faixas altas demais — *"se vem daquele banco, tem que entrar como VP, senão não aceita"* — para descobrir depois que performavam abaixo, sem caminho de volta.

Caso concreto do dano: promoveram alguém excelente para gerente-geral de uma operação. A pessoa não era boa nisso, mas era **excepcional no papel anterior**. Voltar foi emocionalmente durríssimo. Hoje, no papel menor, está brilhando de novo.

**[A proposta mais original do conjunto: o modelo militar]** "Nos próximos seis meses você vai para a operação mais difícil. Como você vai para lá, você é o general daquela missão, com esse título e essa remuneração. Quando a missão terminar, você volta para a base — e lá você não é general nem ganha o mesmo, porque é outro papel."

O que isso resolve: elimina o trauma de dizer a alguém que "não é bom o suficiente" para continuar no nível. Você recebeu sua medalha pelo que fez naquele ciclo. E evita deixar a pessoa presa como VP para sempre, o que termina em *"você está fora porque não tenho mais um papel que pague isso"*.

Ressalva honesta de quem propôs: título mexe com a cabeça de todo mundo, inclusive dela. *"Às vezes eu estou construindo algo menor e sinto como um retrocesso de carreira. Mas não é — são ciclos diferentes."*

### A carreira em Y ainda faz sentido?

O consenso foi que a versão tradicional está quebrada — mas por razões diferentes em cada empresa.

**O argumento:** promover o melhor IC a gestor destrói valor, porque o impacto de um IC excelente é cada vez mais desproporcional. Uma empresa está contratando ex-partners de consultoria estratégica como colaboradores individuais, sem gerir ninguém, entre os mais bem pagos da casa.

**Mas remuneração não basta.** Se os ICs mais importantes não estão nos fóruns de decisão estratégica, o modelo não se sustenta. Tem que mudar o viés cultural de que "progressão é virar VP" — e isso é mudança cultural de verdade, difícil, porque a gente passa a vida inteira ouvindo isso.

**O problema não resolvido:** não existe progressão natural de IC sênior para VP. Os perfis são diferentes. Em algum momento você contrata de fora para a camada de orquestração — e não há caminho interno.

E uma barreira cultural declarada em outra empresa: *"crescer aqui significa liderar. Não temos uma carreira Y bem definida, e por isso o experimento de Super IC ainda não decolou."*

### Quando construir a capacidade internamente e quando contratar do mercado?

Três critérios, ditos de forma simples:

1. **Capacidade que você tem e sabe ensinar** → faça internamente.
2. **Capacidade que ninguém no time tem** → traga de fora, obrigatoriamente. Não adianta alguém acordar e decidir virar especialista sozinho; precisa de quem já sabe fazer.
3. **Capacidade que você tem mas não tem tempo de exercer bem** → traga de fora. O exemplo: um founder que seria um excelente CMO, mas precisava ser CEO. Se o time interno é júnior e levaria cinco anos para chegar lá, o tempo é o critério decisivo.

E a variável que ninguém controla: **depende de quem você encontra no momento**. Se aparece a pessoa certa de marketing, você delega marketing e foca em outra coisa. Nunca é o mundo ideal.

### Como trazer uma capacidade que a empresa inteira não tem?

O caminho que funcionou foi adquirir um time que já sabia fazer — mas o que fez a integração dar certo não foi técnico.

> Eles não chegaram no salto alto dizendo que estava tudo um desastre. Começaram pequeno, perguntando "posso te ajudar com isso?".

Foram atravessando a organização a convite, time a time, e as pessoas foram vendo o poder daquilo. Não foi invasão. Foi assim que a capacidade entrou no core da empresa. E é o oposto do padrão de squad central que chega impondo.

### Como contratar C-level de fora sem quebrar a cara?

**Taxa de acerto declarada, sem maquiagem: cerca de 20% quando se contrata direto do mercado.** O resto ficou, mas nunca funcionando como deveria — quase sempre por falta de onboarding adequado.

O que funcionou:

- **Contrate a pessoa "quase lá", não a que já chegou.** Numa consultoria, contrate o associate partner prestes a virar partner, não o partner. O primeiro ainda tem fome e memória de mão na massa, e já tem presença. O partner está acostumado a ter recurso, tempo e time — e costuma ser mais lento.
- **As melhores contratações levaram três a quatro meses de conversa.** Começa vendendo a missão. Depois convida para conhecer a operação. Quando a pessoa é boa, ela vai falar com outras pessoas por conta própria — e é aí que se convence. Só então começa o modo entrevista, que dura uma semana: jantares, tempo com o time, dias na operação.
- **Onboarding de C-level: um de cada vez.** Os melhores casos passaram os três ou quatro primeiros meses grudados em um founder — viajando juntos, sentados lado a lado — até aprenderem a ler o pensamento um do outro. Dois ou três C-levels entrando ao mesmo tempo é uma bagunça garantida, porque você não consegue dar esse tempo.

### E quando o executivo é um founder de empresa adquirida?

São excelentes e são problemáticos, e a variável não é competência — é personalidade e qual papel a pessoa aceita ocupar.

**Por que são excelentes:** fazem acontecer, empurram, mudam a cultura, entendem a urgência, falam a sua língua. Você pode colocá-los em qualquer posição e a velocidade aparece.

**Por que dão errado:** mantêm a mentalidade de founder mas dentro da visão de outra pessoa. Contratam demais, constroem o que querem, criam camadas e burocracia, não repassam as mensagens — e a organização fica mais lenta. É ego, quase sempre.

> Se eu não sou o founder, eu preciso seguir a sua visão. Mas eu quero a minha visão — eu sou founder.

O caso que deu certo: entrou ajudando todo mundo, sem agressividade em relação a cargo, e hoje é CEO de uma das operações.

### Como contratar em um mundo de agentes?

Parar de pensar em "tenho quatro vagas neste projeto e dez naquele".

A pergunta passa a ser: existe trabalho a fazer; **quanto de talento humano e quanto de IA são necessários, e que tipo de talento?**

Referência citada de um laboratório com algumas centenas de pessoas onde **o custo de tokens já é quase igual ao custo total de folha** — não só de devs, total. Lá, a pergunta na contratação é: essa pessoa vai fazer os seis, oito, vinte agentes dela mudarem? Ela tem curiosidade? Ela vai achar o caminho?

E uma regra prática adotada por uma empresa: **ninguém contrata ninguém sem antes mostrar o próprio uso.** *"Mostre quanto você usou. Se não usou, vá fazer alguma coisa primeiro."*

### O que fazer com vagas júnior?

O mercado reduziu drasticamente a entrada de júniors. Duas respostas contrárias à corrente apareceram:

**Uma empresa está abrindo programa de estágio** exatamente para trazer quem aprendeu a programar já na era da IA. A aposta é que essa geração vai prosperar num ambiente onde agentes são o padrão, não a exceção.

O paralelo histórico usado: os desenvolvedores sêniores que diziam que usar IDE com autocomplete *"ia impedir de aprender de verdade"* estavam errados. A história se repete.

**Outra empresa** respondeu estruturando programas de entrada melhores, de forma intencional — reconhecendo que a diminuição de vagas júnior é um problema real que ela mesma está criando.

### Como abrir um novo mercado do zero, do ponto de vista de gente?

A sequência que funcionou:

1. **Antes de abrir:** traga para a sede as pessoas que vão liderar o novo mercado e deixe-as lá por seis meses a um ano. Elas voltam sabendo como a organização funciona.
2. **Primeira contratação local: recrutamento**, emparelhado lado a lado com o líder do mercado, para aproveitar os processos, os números de conversão e o know-how da operação original.
3. **Segunda: people operations** — folha, benefícios, fornecedores. Sem isso você não consegue pagar quem acabou de contratar.
4. **O que faria diferente: não contrataria alguém para onboarding.** Deixaria o onboarding com o time que contratou a pessoa. Teria sido mais bem-sucedido.

**[A observação mais contraintuitiva]** O melhor momento de contratação da empresa foi quando **não havia recrutadores**. Sem gente disponível, treinou-se os próprios líderes para contratar. Resultado: eles pesquisavam mais, se engajavam mais, conheciam de verdade os candidatos antes da entrada — e por isso **queriam que essas pessoas dessem certo** e dedicavam tempo a fazer isso acontecer.

### Qual o único conselho que você daria a si mesmo sobre montar o time?

**Contrate para a organização que você vai ter nos próximos 18 meses.** Não para o IPO, não para o horizonte longo que você não sabe quando chega e nem como será.

E o complemento tático que evita muita dor: **não dê o título até a pessoa merecê-lo.** Em vez de contratar um CMO, contrate um head de marketing. Se a pessoa cresce no papel, você dá o título — e ele vira algo a que ela aspira. Se não cresce, você não precisa da conversa devastadora de rebaixar alguém para trazer outro por cima.

### E times operacionais de alta rotatividade e salário baixo?

Quatro práticas:

1. Um time de recrutamento muito bom, porque o fluxo é constante e não vai parar.
2. Usar IA para reduzir o número de pessoas necessárias — e assim reduzir o tamanho do problema.
3. **Compensar muito bem os top performers**, via bônus, para garantir que os melhores fiquem.
4. Presença física. Nada de remoto. Gestores no chão, com o time, resolvendo — inclusive garantindo que as pessoas apareceram para trabalhar.

## 07. Processo e dados: a fundação invisível

### Qual é a fundação que ninguém quer discutir?

Processo e dado. Nesta ordem.

O autodiagnóstico mais honesto que apareceu, de uma empresa grande e adiantada:

> Somos ruins em entender nosso processo. Somos ruins em definir o passo a passo. Somos ruins em trazer discernimento para tomar a decisão. Somos ruins em definir quem é o dono daquela decisão. E somos ruins em voltar e registrar por que aquela decisão foi tomada.

Uma referência recomendada durante o encontro sustenta o mesmo ponto: neste momento, **o maior problema das empresas é a falta de profundidade nos processos**.

### Que pré-requisitos técnicos separam quem consegue ir a orquestração ponta a ponta?

Três, na ordem:

1. **Salve todo dado, mesmo bruto e desestruturado.** Antigamente você tinha que estruturar para salvar. Hoje você salva e estrutura depois, na hora de consumir. Muitos projetos travam simplesmente porque o dado não existe.
2. **Domine a própria arquitetura de dados.** Não basta salvar — tem que saber quais são as tabelas, como acessar, como cruzar.
3. **Camada de integração.** Muitos sistemas legados precisam ser modernizados **antes**, senão cada integração vira um parto. Vale considerar um projeto prévio só de modernização — inclusive em empresas que não são antigas.

### Qual é o gargalo real quando o agente já conversa bem com o cliente?

**Fazer o agente operar os sistemas.**

Responder de forma conversacional é fácil e resolve rápido. Emitir uma segunda via, fazer upgrade e downgrade de conta, processar um pagamento — aí a coisa fica difícil. E o gargalo não está no agente: está em **disponibilizar os endpoints de API internos**, porque a arquitetura não foi construída com essa visão.

> Em vez de fazer o chatbot de atendimento primeiro, eu teria colocado engenharia para expor os endpoints de pagamento.

### Existe um truque prático para melhorar o contexto de forma dirigida?

Sim, e é simples: **quando o agente falha na tarefa, pergunte a ele que informação faltou.**

Isso força a organização a melhorar o contexto e a infraestrutura de dados de forma incremental e dirigida — em vez de tentar arrumar tudo de uma vez sem saber por onde.

Um founder relatou que essa dica mudou o jogo nas provas de conceito dele: *"obriga a gente a se organizar melhor para dar um contexto melhor na próxima vez."*

### De onde vem o contexto de verdade?

Do processo, não da tecnologia. Este foi o achado mais subestimado do conjunto.

Numa empresa onde os agentes pessoais funcionaram excepcionalmente bem, o segredo era anterior à IA: **toda reunião tem documento de pré-leitura compartilhado. Sem exceção.** A reunião começa dois ou três dias antes — o documento circula, as pessoas comentam, o dono responde. Durante a reunião o mesmo documento é atualizado com os próximos passos.

Por causa disso, alimentar o agente com o histórico completo levou **de dez a quinze minutos**: ele acessa todas as reuniões de que a pessoa participou, todos os comentários dela e dos outros, todas as decisões, todos os posts internos.

O efeito relatado: *"fiquei abismado com os comentários dele — eram melhores que os meus."* Porque ele lembra do que foi dito há três anos e correlaciona. E como ele tem acesso aos agentes das pessoas com quem você se relaciona, **ele antecipa a objeção do outro e já contra-argumenta antes de ela ser feita.**

**[A lição transferível]** Se você quer que os agentes funcionem, comece exigindo que as decisões da empresa sejam escritas.

### O que é uma organização "legível por IA"?

O conceito apareceu em duas conversas independentes e vale carregar: pensar em produzir **sistemas que a IA consiga ler** — e, por extensão, uma organização cujas decisões, processos e contexto sejam consultáveis.

Uma empresa incluiu isso explicitamente no manifesto interno. E a observação decorrente é que empresas remotas, que já documentavam tudo por necessidade, chegam nesse ponto com muito mais facilidade — o que explica por que algumas conseguem movimentos radicais que outras não conseguem.

### O conhecimento fora da engenharia está indo para onde?

**Para silos, e essa é a preocupação declarada de quem está mais adiantado.**

Todas as áreas de negócio estão usando muitas ferramentas diferentes. Muito do que as pessoas discutem com essas ferramentas é informação valiosíssima de execução — e não entra em nenhum repositório, não ganha o protagonismo que merece.

Riscos concretos citados:

- A pessoa que montou dezenas de automações sai da empresa e ninguém sabe manter.
- A pessoa fez tudo na máquina local e o disco quebra, sem backup e sem forma de replicar.

A tentativa em curso numa empresa: forçar um **repositório único de conhecimento em markdown**, versionado, visualizado como grafo, alimentado independentemente da ferramenta usada — e construir agentes que fazem a interconexão e a síntese. Reconhecimento honesto: a ferramenta sozinha não basta, não tem interpretação semântica forte.

**Este é o próximo degrau declarado:** um "meta-repositório da companhia" com estratégia, regras de negócio, documentação técnica e especificação de produto. Para então repetir na empresa inteira o que já foi feito na engenharia — uma pessoa orquestrando um squad de agentes, em vez de uma pessoa por especialidade.

## 08. Construindo agentes: o que funciona

### Como fazer um agente aprender com o melhor humano?

**Copie o melhor humano, não a média.**

Pegue os dois ou três melhores vendedores ou atendentes e **sente eles ao lado de quem constrói o agente**. Esqueça a média e esqueça o dado agregado. Um bom vendedor vende de três a cinco vezes mais que outro — a média destrói exatamente o sinal que você quer capturar.

E há uma razão adicional: essa pessoa tem visão de processo. Ela audita o que o agente está fazendo e diz *"aqui está ruim, aqui está bom"*. Sem ela, você não tem juiz.

### Prompt deve dizer o que fazer ou o que não fazer?

Um founder que construiu agentes de venda em alto volume foi específico: **funciona melhor focar no que o agente NÃO pode fazer.**

O trabalho é vender. Existem duzentas ou trezentas coisas que ele não pode fazer. Deixe o objetivo dentro de uma visão simples e coloque a energia nas restrições.

### Qual é a arquitetura de agentes que sustenta trabalho sério?

O modelo mais detalhado apresentado usa **papéis estreitos, cada um sendo um arquivo de especificação**: produto (especialista no domínio do negócio), UX, arquiteto, engenheiro (só escreve código — não define arquitetura, não faz QA, não escreve doc), revisor de qualidade, redator técnico, gerente de tarefas e orquestrador.

**Por que papéis estreitos:** os modelos se comportam melhor com contexto focado e estrutura clara. Quando o espectro de possibilidades é amplo demais, começam as alucinações e os desvios de objetivo.

**Você conversa só com o orquestrador.** Nunca abre uma janela por agente. Ele tem a capacidade semântica de rotear: falou de arquitetura, chama o arquiteto; falou de documento, chama o redator.

> Ele é só mais um agente, não tem protagonismo real. Não gastei muito tempo construindo e não dou manutenção. O bom funcionamento não é mérito nosso — é do paradigma do próprio fornecedor. O que é nosso é ter definido bem *como trabalhar* e ter expressado isso dentro dele.

### Qual é a unidade de trabalho certa?

**O arquivo.** E cada agente acrescenta uma camada no mesmo arquivo:

1. Definição da tarefa.
2. Produto acrescenta histórias, critérios de aceite, métricas de sucesso.
3. UX acrescenta componentes e definições de acessibilidade.
4. Arquitetura acrescenta modelo de dados e relação entre APIs.
5. O engenheiro pega o arquivo pronto e faz **exatamente o que está escrito, nem mais nem menos**, com os critérios de aceite ali.
6. Qualidade acrescenta se o que foi feito reflete tudo o que foi especificado antes.

### Vibe coding ou spec-driven?

Vibe coding é muito mais rápido — **só no começo.** Depois vem o trabalho de reconstruir, e você não consegue evoluir.

Mas o problema mais grave não é a qualidade do código. É a **dependência da pessoa**. Tanta coisa foi criada em conversa com o agente, sem documentação, que fazer handover é quase impossível. Num sistema onde arquitetura, papéis e cada tarefa foram especificados, **qualquer pessoa consegue dar manutenção**.

**[A tríade que resume o método]** 1. **Input cuidadoso** — memória, agentes, documentos de especificação.
2. **Execução especializada** — nunca uma tarefa ampla e aberta. Especifique, encurte, quebre em tarefas.
3. **Ligação com o humano** nos pontos certos.

> Ela se autovalida, mas não se autossupervisiona.

### Como controlar custo sem perder qualidade?

**Aloque o modelo por etapa.** Modelo caro e mais profundo para definir arquitetura; modelo barato para escrever código. Se a definição estiver bem-feita, o código sai bom com o modelo simples.

Isso é o que torna a coisa sustentável em escala — porque se cada desenvolvedor passa a rodar um squad inteiro, o consumo vira bloqueio real.

Outra empresa resolveu no nível de plataforma: um **roteador de modelo** que manda prompt simples para modelo barato, com limite de orçamento por usuário. *"Longe do ideal, mas já dá controle."*

### Como revisar o que os agentes produzem?

**A regra mais importante descoberta na prática: o agente que valida tem que rodar em sessão totalmente limpa.** Usar a mesma sessão que desenvolveu enviesa a análise. Sessão nova, contexto zerado, "entre no modo validador".

O fluxo que funcionou:

- A branch nasce com o nome do épico. Nunca se trabalha na main.
- A pessoa faz o QA do próprio pull request em sessão limpa, encontra coisas reais, corrige, revalida.
- Envia com o **relatório de validação anexado**.
- **O revisor humano não lê mais o código.** Lê o relatório, dá uma passada de olho para ver se não há nada perigoso, e aprova. Se for algo arquitetural novo, faz uma pergunta a quem desenvolveu.
- Merge automático ainda não.

Uma empresa maior mantém regra diferente e mais conservadora: **dois humanos em todo pull request** — quem pilotou o agente mais um segundo engenheiro que faz revisão independente. E o dado tranquilizador: mesmo com muito mais deploys, **o número de incidentes se manteve estável**.

### Como habilitar não técnicos a construir sem quebrar a produção?

Duas soluções elegantes apareceram.

**Versão mockada.** Criar uma versão 100% mockada da aplicação, no mesmo repositório — o front sem o back plugado. O diretor de produto trabalha só nela: desenvolve features, comportamentos de tela, tratamento de dados de interface, tudo já sai codado. Depois alguém mais técnico conecta ao back. O papel de produto deixou de terminar antes da aplicação e passou a entregar dentro dela. Foi chamado de *"vibe coding coordenado"*.

**Regra explícita de fronteira.** Em outra empresa, o time de negócio tem ferramental no-code e constrói muito — protótipos, análises, provas de conceito. Mas **é proibido colocar coisa de negócio em produção**, porque há estruturas que sustentam a operação em escala.

**[A metáfora que organiza isso]** "Código hoje está virando o que a planilha era." Existe a planilha no seu laptop (ótimo, ninguém depende dela); existe a planilha que o financeiro usa para calcular de verdade (outro nível de exigência); e existe a planilha compartilhada. Para código, até agora só existia a camada de produção. Agora todo mundo escreve código — e a camada intermediária, de compartilhar com segurança o que o negócio construiu, **ainda não existe**.

### Como lidar com memória compartilhada entre o time?

Duas camadas: memória do projeto (compartilhada, dentro do repositório) e memória local do usuário (preferências pessoais que sobrescrevem as do time).

**A regra que importa: nunca force a memória.** Deixe o modelo decidir o que guardar — ele é razoavelmente bom nisso. Forçar contamina.

Exemplo do erro a evitar: guardar na memória do projeto um comando de setup local que só você usa. Isso contamina o contexto de todo o time.

E como o time evolui os agentes: **troca humana direta**, em dailies e reviews. Vê o que funcionou e o que não funcionou, atualiza o arquivo no repositório, e a mudança vale para todos.

### E skills? Cada um cria o seu?

Não. **Skills devem ser centralizados.**

A objeção que motivou a decisão: se cada PM criar o próprio skill de PRD, a empresa acaba com dezenas de PRDs diferentes.

Numa empresa, ao terminar de montar o agente pessoal, o sistema **sugere quais skills a pessoa precisa** — separados em obrigatórios, recomendados e opcionais. Todos vêm do repositório central.

### Como lidar com épicos que atravessam vários repositórios?

A solução do **meta-repositório**: o épico e a quebra em tarefas moram num repositório-guarda-chuva; as especificações de arquitetura e as memórias moram em cada repositório específico.

**Regra: toda tarefa é exclusiva de um único repositório e de uma única camada da aplicação.** Um épico que atravessa quatro camadas vira cinco pull requests.

Isso surgiu justamente porque arquitetar as dependências entre repositórios separados estava sendo o ponto mais difícil.

### O que é "auto-research" e por que importa?

Dê ao sistema um objetivo **quantificado**, deixe-o formular hipótese, rodar experimento, ler o resultado, ajustar a hipótese e repetir.

Isso já era conhecido em pesquisa de modelos. A descoberta foi que **funciona para trabalho de engenharia comum**.

**[O caso real]** Uma série de repositórios com pouco mais de 40% de cobertura de testes, objetivo de subir dez pontos por ciclo. Seis agentes rodaram noventa e um ciclos em um fim de semana. **Nenhum humano trabalhou.** Estimativa do que custaria: dois meses de um time de devs.

O passo seguinte em teste é o **auto-build**: entrega-se a especificação, o sistema cria o plano e passa a noite construindo; de manhã há um protótipo para o time criticar. Custo da noite: alguns dólares em tokens.

### Observabilidade de agentes: o que é obrigatório?

Três camadas, ditas por quem opera vendas conversacionais em alto volume:

1. **Observabilidade de dados** — onde está cada lead, cada ticket, se foi resolvido.
2. **Observabilidade de jornada** — quantas mensagens foram enviadas, se todos os follow-ups saíram. Isso é praticamente impossível com um time humano.
3. **Agentes que observam agentes** — mais de vinte mini-agentes gerando relatórios diários sobre as conversas, checando se o preço está correto, se a fala está adequada, se não está alucinando.

O motivo é simples: **em escala, se a IA começar a alucinar, você precisa saber. E rápido.**

### Como testar mudanças sem quebrar produção?

**Ambientes sintéticos de teste (evals) foram descritos como divisor de águas.**

O problema real: você mexe uma coisa no prompt e quebra todo o resto — e só descobre em produção. A solução foi criar um ambiente de simulação que roda uma bateria de testes simulados antes de qualquer mudança em prompt, base de conhecimento ou ferramenta.

Depois da simulação, **teste A/B em produção com fatia pequena** — algo como 5% do volume.

> Você vai gerando ambientes sintéticos para testar novas hipóteses. Esse mundo é compounding — se você tem mais ambientes e mais agentes testando mais coisas, você está muito mais na frente. E você encurta muito o ciclo de desenvolvimento de produto.

Um padrão complementar de rollout, de outra empresa: **testar sempre na mesma cidade média** antes de escalar para o país inteiro — sempre a mesma, para ter série histórica de comparação.

### Base de conhecimento (RAG): qual é a armadilha?

Vira pesadelo se não for curada.

A base fica gigante, e você acaba com documentos diferentes dizendo a mesma coisa em lugares diferentes. Resultado: alucinação. **Como você separa, como faz o chunking, como busca e como audita importa tanto quanto o prompt.**

E há um risco de segunda ordem que ficou como pergunta aberta: o que acontece quando a base de conhecimento abstrai algo errado? Como auditar para garantir que ela não acumula erros silenciosos que contaminam as decisões do agente ao longo do tempo?

### Determinismo: como responder à objeção "meu processo precisa ser determinístico"?

Esta foi a melhor resposta técnica do conjunto.

> O caminho pode ser não determinístico desde que a resposta seja consistente.

Se duas pessoas fazem a mesma pergunta sobre quantos pedidos ocorreram ontem, o agente pode escolher rotas diferentes na base — mas a resposta tem que ser a mesma. Não pode haver duas respostas.

Mecanismos práticos:

- Rodar a mesma tarefa dez vezes e adotar a resposta que aparece oito (voting).
- Tratar como problema clássico de classificação, com precision, recall e accuracy medidos.

**E o enquadramento de negócio:** esse vocabulário não é vocabulário de negócio. Ninguém no negócio pergunta o grau de determinismo — pergunta se a sessão converte melhor, se a fraude cai. **Determinismo é escolha de solução, não objetivo.**

Onde importa muito: modelo de crédito, fechamento contábil, relatório para auditoria. Aí a abordagem é outra — fonte definida, processo auditável, checagens específicas. *"É muito diferente fazer um relatório para o comercial ir à rua e entregar o relatório anual para o auditor."*

### Como vencer a resistência da área de negócio a colocar em produção?

**Rode as duas esteiras em paralelo.**

O caso: precificação de processos jurídicos que ocupava dezenas de advogados, cerca de uma semana por caso. A solução automatizada gerou resistência imediata — *"com certeza isso está errado, eu faço isso há muito tempo."*

O caminho foi manter a esteira humana rodando e mandar **os casos mais simples e menos arriscados** em paralelo para a nova esteira, comparando resultados como um backtest. Conforme a confiança cresce, tomba-se o volume.

### Os agentes aprendem sozinhos?

Não, e vale ser honesto sobre isso internamente.

Os agentes têm memória do histórico completo do cliente — quem atendeu, quando virou venda, o que aconteceu no pós-venda, e nunca esquecem. Quando chega o momento de cross-sell, todo o histórico está lá.

Mas **eles não aprendem sozinhos. Aprendem com humanos observando e corrigindo.** É por isso que a figura do juiz, do auditor, de quem olha os evals todo dia, não é opcional.

### Devo construir meu próprio harness ou usar o de mercado?

**Não é necessário construir o seu.** Dá para usar um harness de mercado e criar plugins específicos por área — growth tem o seu, atendimento o seu, engenharia o seu.

Construa o próprio só onde é core do seu produto ou onde você precisa otimizar custo e escolha de modelo. Em codificação, o harness de mercado está tão à frente que não compensa competir.

**O contraponto de quem construiu:** a resposta adotada foi "os dois", por três razões — (1) construir dá conhecimento e maturidade que se transferem para outras áreas, e código que nasceu no ferramental interno virou produção em outros produtos; (2) **option value** — quando um fornecedor fica caro ou lento, existe a camada para trocar; (3) **custo** — um agente vivo por pessoa, conectado a todos os sistemas internos, é impossível de escalar para milhares de pessoas sem controlar a tecnologia.

E uma estrutura de curadoria de ferramentas que vale copiar: uma lista **"padrão"** com tudo que qualquer pessoa pode usar, e um trilho **"um passo à frente"** — se duas ou três pessoas mencionarem uma ferramenta nova, um time vai olhar. Com o reconhecimento honesto de que metade das ferramentas pedidas é moda, e a maioria das pessoas nem usa o teto do que já tem.

### Vale usar um segundo modelo para revisar o primeiro?

Fazia sentido no passado. Depois que a disciplina de especificação, memória e processo amadureceu, um time parou — e parou inteiro. *"Não sinto mais falta de segunda opinião, não tenho blockers, não tenho subida bugada."*

A leitura de quem viveu: **o ganho veio da disciplina de spec e processo, não de desconfiar do modelo e buscar contraponto.**

## 09. Governança, segurança e custo

### Como equilibrar autonomia e governança sem matar a adoção?

Este foi o dilema mais admitido como não resolvido.

Liberar acesso amplo faz o custo escapar do controle. Encher de controle mata a adoção. **A resposta não é escolher um dos dois: é alinhamento.** Libere, mas acompanhe, meça e conecte com o objetivo do negócio. Quando não dá certo, quase sempre é porque não existe esse elo entre o que está sendo feito e as prioridades da empresa.

### Qual é o melhor reframe sobre segurança?

> O trade-off não é entre IA e segurança. É com a velocidade que você quer andar.

O exemplo que ilustra o problema novo: se uma pessoa compartilha o agente dela comigo e eu faço uma pergunta, o agente bate no banco com o token dela ou com o meu? Deveria ser o meu. Isso exige autenticação, propagação de identidade e permissão por agente — componentes que simplesmente não existiam antes. **Não é trade-off, é trabalho novo.**

E a postura adotada diante de uma ferramenta open-source arriscada: em vez de banir, o próprio líder técnico conectou tudo, avisou o time de segurança e **pediu red teaming** — *"porque se eu fiz, em uma semana vão ter vinte, depois duzentos."*

A premissa: numa empresa de milhares de pessoas, **banir nunca funciona**. Assuma que algo vai vazar e entenda o risco rápido, com colaboração aberta e restrita, em vez de fingir que dá para fechar.

### Mas então nunca se proíbe nada?

Proíbe-se sim — e a decisão oposta também apareceu, na mesma empresa e em outra área.

Uma ferramenta open-source viralizou internamente e um colaborador virou evangelista dela. O time técnico **proibiu explicitamente, com aviso de consequência para quem usasse**. A decisão foi descrita pela própria liderança como *"extremista para a nossa régua, mas necessária"*, porque era uma das ferramentas com maior risco de vazamento.

O desfecho interessante: dois meses depois a empresa tinha uma alternativa proprietária, desenvolvida justamente por causa dessa pressão. **A proibição gerou o movimento.**

### Qual é o padrão de liberação de ferramentas?

O padrão citado, escalonado: **libera para cinquenta pessoas → testa → garante os guardrails → escala para centenas.**

Regras que apareceram em várias empresas:

- Nenhuma ferramenta gratuita.
- Trava de segurança da informação ao tentar levar documentos para fora.
- Toda ferramenta nova passa por aprovação formal.
- Ferramentas não homologadas bloqueadas na rede.

E um truque tático bom: uma empresa usou a **verba individual de desenvolvimento/PDI que já existia** para liberar as ferramentas pagas dentro dos guardrails, antes de ter um processo formal.

### A área de segurança vai crescer ou encolher?

Crescer, e muito. Uma empresa global relatou que a área de segurança ganhou cerca de **dez subáreas que não existiam**.

Exemplo concreto: para criar um agente que faz crawler em sites, hoje é preciso aprovação de três agentes de verificação — se é seguro, se há risco de vazamento, se há risco de prompt injection.

Daí a tese de quem falou: **a IA vai criar mais funções do que extinguir.** Muitas ainda invisíveis. Segurança é só a mais óbvia.

### Como controlar o custo de token?

Primeiro, a calibragem de expectativa mais útil que apareceu:

> Se o CEO acha que está gastando pouco com IA, provavelmente está gastando muito pouco mesmo. A sensação correta neste momento é a de estar gastando demais.

Achar que está tendo retorno enorme com investimento baixo não é o caso comum. A etapa de experimentação é cara, e todo mundo tem que passar por ela.

Onde o custo já está: em empresas na fronteira, **na faixa de 50% a 100% da folha**. Um laboratório com algumas centenas de pessoas relatou custo de tokens quase igual ao custo total de pessoal.

O que está sendo feito:

- **Roteamento de modelo por caso de uso** — a hipótese generalizada é que o custo cai muito com isso, mas **ninguém viu isso feito em escala ainda**.
- **Limite de orçamento por usuário** dentro das ferramentas proprietárias.
- **Alocação de modelo por etapa do trabalho** (caro para arquitetura, barato para execução).
- **Medição de tokens por time** — que começou como controle de custo e virou o melhor sinal de adoção disponível.

E o que várias empresas decidiram **não** fazer: premiar quem consome mais token ("token maxing"). A competição é usar e aprender, não gastar.

### Como fica a responsabilidade legal quando um agente decide?

Fronteira aberta e sem resposta.

O modelo jurídico atual atribui responsabilidade — criminal ou financeira — a pessoas. Quando houver agentes tomando decisão, quem responde? O agente, o desenvolvedor, a empresa, o investidor?

A analogia usada foi a do veículo autônomo: não existe boa regulamentação, e quando acontece algo é difícil dizer de quem é a responsabilidade. Em saúde, onde há risco de vida, a pergunta fica mais aguda ainda.

E há uma camada anterior: **quem governa os agentes?** Quem coordena, quem controla, quem define os parâmetros. São funções que não existiam há dois ou três anos.

### O que o cenário regulatório muda na prática?

- **Estados Unidos:** optaram por quase não regular, dando autonomia às empresas para cuidarem dos próprios riscos. A lógica declarada é "deixa inovar e depois a gente conserta".
- **Europa:** regulação forte, com multas que chegam a 2% do faturamento. Já está revendo o próprio texto por ter retrocedido no desenvolvimento de soluções.
- **Brasil:** ambiente ainda livre. O texto em discussão é mais restritivo que o europeu, mas sem perspectiva de aprovação.

O efeito observado é concreto: empresas europeias estão mais lentas, muito preocupadas com regulação e com impacto social. E setores regulados vão mais devagar por razão legítima — não por má vontade.

### Como transformar jurídico, RH e compliance de barreira em aliados?

Primeiro, o dado que surpreende: **a maior fonte de resistência não são os usuários finais — são jurídico, RH e compliance, em cerca de 35% dos casos.**

O reframe que resolve: **essas áreas não resistem por gosto. O papel delas é encontrar risco.** Em setores regulados isso é indispensável, e você não quer construir uma solução que exponha a organização.

O que funcionou:

- **Mudar a meta.** "Sua meta não é mais achar risco. Sua meta é fazer este projeto dar certo — e para isso você vai ter que apontar os riscos **e** os caminhos."
- **Colocá-las na sala desde a primeira reunião**, nunca no papel de validador no fim da esteira. *"Eu desenvolvi tudo, agora te mando para você dar o check."* Isso nunca vai dar certo.

### Estamos julgando o risco da IA de forma justa?

Provocação que ficou sem resposta e vale carregar para dentro de casa:

> Somos muito mais rigorosos ao julgar o erro do agente do que o erro humano. O ser humano também erra, também alucina em alguns momentos — e ainda assim damos autonomia a ele. Não sei se a gente tem uma percepção de risco falsa que está travando a adoção.

## 10. Métricas, ROI e a conversa com o board

### Qual métrica-norte as empresas estão usando?

**Receita por colaborador** — e o detalhe que faz diferença: cobrada de **todo o C-level**, não de uma pessoa só.

Não é necessariamente a melhor forma de medir, mas é a que mais tangibiliza e a que mais se usa.

Uma variação de quebra de paradigma, comunicada à liderança sênior de uma empresa grande: historicamente, cada ponto percentual de crescimento de receita vinha acompanhado de um ponto de crescimento de headcount. A nova regra é **headcount flat, receita cresce**. E a proposta partiu da área de pessoas, não do negócio.

### Como vincular IA ao P&L quando o ganho é intangível?

Este é o problema mais honesto do conjunto, e não tem solução limpa.

A ligação com crescimento de receita é indireta — real, mas indireta. **O storytelling interno é o que convence o CFO.**

E o maior valor é justamente o mais difícil de defender: **não é a velocidade, é o aumento de ambição.** O que muda não é só quanto tempo você leva, é o **tipo de trabalho que se torna viável de fazer**.

Do outro lado da mesa, quem vende solução ouviu o recado: o ROI tem que ser mensurável, significativo e amarrado aos KPIs de quem compra. CFOs viraram peça central nesses últimos anos porque esse orçamento simplesmente não estava planejado.

### Que ganhos concretos foram medidos?

Compilado do que apareceu — ordens de grandeza, não promessas.

**[Engenharia]** - Ciclo de entrega ~28% mais rápido; qualidade de código ~16% melhor.
- Investigação de erro caindo de ~30 minutos para ~1 minuto na análise de logs e stack traces.
- Pull requests por pessoa dobrando em doze meses.
- Cobertura de testes de 42% para acima de 60% em um fim de semana, sem intervenção humana.
- Reescrita de um sistema legado inteiro: **orçado em um ano com uma ou duas squads, executado por duas pessoas em dois meses.**

**[Comercial e atendimento]** - Preparação de reunião comercial: de um dia inteiro para três horas (conta complexa) e dez minutos (conta simples).
- Um agente fazendo aquisição de cliente de ponta a ponta — do lead ao contrato assinado — com conversão **levemente acima** do time humano.
- Cerca de 95% dos clientes não pedem para falar com humano.
- Agentes cobrindo cerca de 80% do volume de atendimento com efetividade maior que a do time.

**[Organizacional]** - Ganho de entrega estimado em ~35% com incremento de custo de ~15%.
- Onboarding de novos parceiros acelerado em ~40%; throughput da equipe +65%.
- Um time de dezenas de analistas de inteligência de negócio realocado para trabalho de mais valor.

### Soluções pontuais ou orquestração ponta a ponta?

O dado mais forte de um estudo: apenas cerca de **20% dos casos usavam orquestração agêntica ponta a ponta — mas esses entregaram cerca de 71% de ganho de produtividade mediano**, cerca do dobro dos 30% a 40% das soluções pontuais.

**Ressalva importante e honesta:** eram processos mais simples. Ninguém colocou IA de ponta a ponta em processo complexo, por risco e por complexidade de desenvolvimento.

### A velocidade da empresa realmente muda 10x?

A pergunta mais desconfortável e a resposta mais honesta do conjunto, vinda de quem lidera IA numa empresa de milhares de pessoas com adoção acima de 90%:

> O dia a dia de qualquer pessoa aqui mudou, com certeza. Mas a velocidade da empresa mudou 10x? Ainda não. Nem 2x.

Onde o gargalo foi parar: adoção de ~90% entre devs, pull requests por pessoa dobrados, commits muito acima — e o cycle time não caiu proporcionalmente porque **a revisão humana virou o gargalo**.

A conclusão estrutural: **a adoção individual está resolvida. A passagem de indivíduo produtivo para time produtivo é o degrau que ninguém atravessou ainda.** E a resposta em curso não é otimizar mais a geração — é redesenhar o workflow inteiro.

O eco disso em outra empresa, de porte totalmente diferente: *"estamos entregando software pra caramba, mas as outras etapas e funções continuam rodando no ritmo antigo."*

### Onde está o novo gargalo?

**Em decidir o que fazer.**

Com a produtividade de engenharia disparando, o gargalo virou produto e decisão. A referência citada: uma big tech que operava com cerca de um PM para quatro desenvolvedores hoje trabalha em cerca de dois para um.

O trabalho difícil passou a ser **decidir o que fazer e garantir que é estratégico** — porque quando dá para construir qualquer coisa rápido, muita gente passa a resolver problema que não é problema.

### Como medir se o time está de fato usando?

Cinco mecanismos, do mais simples ao mais estrutural:

1. **Dever de casa apresentado e implementado.** Quem não fez, não apresenta.
2. **Restrição de orçamento por squad.** Sem poder contratar para escalar, o time é obrigado a usar IA para bater a meta.
3. **Consumo de tokens por time.** Começou como controle de custo, virou o melhor sinal de adoção — dá para ver quem não está usando nada.
4. **Ranking público por líder.** Percentual do time com agente ativo, publicado mensalmente ao lado dos pares. Ver "0%" ao lado dos outros criou uma corrida real.
5. **Observação qualitativa:** como as pessoas resolvem problemas, que tipo de pergunta trazem, e **quantas pessoas a mais elas pedem**.

## 11. Produto, negócio e vantagem competitiva

### O modelo virou commodity?

Praticamente. **Cerca de 42% das implementações estudadas consideram o modelo completamente intercambiável** — e muitas já construíram arquitetura que troca de modelo de propósito, para não criar dependência de fornecedor.

E nem sempre faz sentido tiro de canhão: um modelo menor resolve muita coisa por uma fração do custo.

Ponto relevante para mercados emergentes: modelos abertos de origem asiática, com custo até cerca de 80% menor e performance equivalente, estão sendo adotados na Europa e por startups — mas praticamente não pelas empresas americanas, **por razão geopolítica, não técnica**. *"Ninguém vai nos penalizar por usar um ou outro."* Isso é uma vantagem real de custo, e vale testar.

### Se o modelo é commodity, onde fica o fosso?

Duas coisas, e só duas:

1. **Dado proprietário** ao qual você tem acesso na cadeia. Os modelos são treinados em dado generalista; há muito dado proprietário que poderia gerar valor e não está sendo usado.
2. **Entender o processo do cliente tão bem ou melhor do que ele.** Porque se você não entende o processo, sua solução só vai acelerar algo que já está ruim. Se você entende, você ajuda o cliente a corrigir o processo e constrói sobre uma fundação sólida.

O exemplo de mercado citado: empresas que cresceram violentamente em nichos verticais entraram porque **entendem o processo daquele setor** — e quem adota diz que mudou a vida, não porque a tecnologia é melhor, mas porque entende o negócio.

### A aposta em modelo próprio de domínio faz sentido?

Uma empresa apostou pesado nisso: em vez de dezenas de modelos especializados que não conversam entre si — o time de busca com os modelos dele, o time de atendimento com os dele, sem se falarem —, treinar um modelo em cima de mais de uma década de dados proprietários para elevar o patamar de todos ao mesmo tempo.

O argumento de por que isso importa: perguntas de domínio e nomenclatura regional de produto são exatamente onde um modelo genérico falha e o modelo treinado em dado proprietário brilha.

### O que as corporações realmente compram de um fornecedor de IA?

**Ninguém se importa com quão sofisticada é a sua solução.** O estado da arte não vende.

Há muita startup resolvendo problema que não existe. E a distinção que importa é afiada: uma **hipótese de problema** é uma coisa; **alguém chorando com aquele problema todo dia e com linha de orçamento já alocada** é outra completamente diferente.

Foque em problemas reconhecidos dentro da organização **que já têm orçamento**. Isso muda ciclo de vendas e velocidade de adoção.

E o conselho de processo: antes de construir, faça algo como cem entrevistas com gente do ramo. *"O cliente não sabe o que quer" estava certo na boca de uma pessoa específica da história da tecnologia. A maioria de nós não é essa pessoa.*

### Como pensar build vs. buy?

**Regra simples e boa:** terceirize o que é importante mas não é core. Construa internamente só o que tem **compounding effect de IP** no longo prazo.

Escolha a batalha que vai fazer diferença no longo prazo para a sua empresa. Para o resto, o mercado já tem fornecedor — e a barra subiu muito: se você vai automatizar algo, o argumento interno vai ser sempre *"tem outra empresa ali que a gente pode alugar por uma fração do custo"*.

E a nuance de tempo: você consegue fazer um agente responder de forma conversacional rápido. Fazê-lo operar todos os sistemas e entender todos os casos de exceção é muito mais complexo — e leva perto de cinco meses até funcionar de verdade, mesmo com fornecedor.

### A IA se aplica ao meu tipo de venda?

**Não depende do ticket. Depende do canal de venda.**

Se a venda é conversacional — texto, áudio, mensageria, chat no site — a IA entra, mesmo em produtos de dezenas de milhares de reais. Foram citados casos em veículos elétricos e maquinário.

Em venda consultiva longa, com visitas e vários meses de ciclo, o ganho está em outro lugar: **na triagem e preparação de lead, e nas tarefas do gerente de vendas e do auditor de qualidade** — não na conversa em si.

> Tudo que é texto vai ser automatizado com o tempo. Isso é código, isso é venda por texto, isso é atendimento — qualquer interação que seja texto.

### O que a IA destrava no roadmap que ninguém está contando?

Um ângulo pouco discutido: funcionalidades que ficavam **anos na fila de priorização por falta de capacidade de desenvolvimento** passam a caber.

O exemplo dado por quem opera um produto de escala global: limites de funcionalidade que existiam por restrição de hardware da base de usuários agora podem virar versões diferenciadas por segmento — coisas pedidas todo ano no comitê de priorização, nunca priorizadas por falta de recursos.

**O destravamento de roadmap tem valor enorme e quase nunca entra na conta de ROI.**

### Devo me preocupar com a experiência migrar para fora do meu produto?

O termo usado por quem está lidando com isso: **paranoia produtiva.**

A postura adotada: conversar com todos os provedores de modelo, estar aberto a parcerias, **e ao mesmo tempo construir a própria versão dentro do canal onde o usuário já vive**.

E o achado prático que acalma um pouco: fazer uma jornada de compra completa dentro de um chat parece simples e não é. Mesmo internamente, com controle total do catálogo e das APIs, é **muito difícil ficar melhor do que o produto atual**.

### O que é a diferença real entre POC e produção?

Uma coisa funciona para cem usuários. Para mil. Para dez mil. **Quando vai para milhões, ou quebra, ou fica caro demais, ou lento demais.**

A diferença entre POC e produção é **trabalho estruturante de tecnologia** — e é exatamente aí que mora a barreira do "AI-native" de verdade. É o trabalho que ninguém mostra em apresentação.

### Vale confiar no que os concorrentes anunciam?

**Não sem visitar.**

Duas anedotas honestas do mesmo encontro:

- Uma empresa anunciou publicamente que tinha "disruptado" a compra de mercado via foto ou áudio da lista de compras. Ao investigar de perto, não era isso.
- Outra anunciou entregas autônomas por drone em escala e custo competitivo. Na visita, havia uma pessoa controlando remotamente pelo celular ao lado.

*"Existe muito PR embutido no que se anuncia. O mercado se ajusta depois, mas quem anunciou já fez o dinheiro."*

**O que de fato impressionou na comparação internacional não foi tecnologia mágica.** Foi escala de experimentação e granularidade de otimização — por exemplo, otimizar alocação de investimento promocional por micro-região em vez de por cidade.

### Estamos atrasados em relação aos Estados Unidos?

Uma pesquisa comparou empresas brasileiras e americanas em projetos de IA e **não encontrou nenhuma diferença de resultado.**

> Uma das dúvidas que eu tinha, meio síndrome de vira-lata, era se os projetos que eu participei aqui geraram menos resultado do que os dos Estados Unidos. Não geraram.

A tese estratégica: não vamos disputar a construção de modelos fundacionais — isso exige capital demais e vai seguir concentrado. **Mas a batalha da aplicação é totalmente disputável**, com soluções verticais em setores onde o país tem conhecimento específico e problemas reais para resolver.

E há uma vantagem regulatória: liberdade de escolher qualquer modelo, de qualquer origem, sem constrangimento geopolítico.

### Como pensar a dependência de plataformas de terceiros?

Está cada vez mais difícil ter controle — e isso vale tanto para o canal de distribuição quanto para o modelo.

Construir seu próprio app sabendo que o usuário vive dentro de outro canal é mais caro: você tem curva de aprendizado, custo de aquisição, direcionamento. Mas construir em cima do canal do outro te expõe.

**A resposta não é evitar a dependência. É ter plano B e plano C.**

> O empreendedor sempre precisou lidar com incerteza muito mais do que com risco. Só que hoje esse grau de incerteza é muito maior.

### IA para pequenos negócios funciona?

O desafio mais subestimado, na visão de quem opera isso em escala.

Agentes de atendimento gratuitos para pequenas empresas têm boa entrada e **churn alto**. Não adianta dar meia dúzia de instruções e esperar que o agente ande sozinho — *"é como colocar um funcionário novo na sua loja e falar: se vira aí."*

O caso que ilustra: um pequeno lojista abriu uma exceção e vendeu uma peça numa cor que não tinha em catálogo. O agente interpretou que aquela cor passou a fazer parte do catálogo e saiu vendendo. O lojista cancelou o serviço e disse que nunca mais usaria IA.

A aposta contrária, do mesmo interlocutor: o benefício para pequenos negócios é transformador e tem impacto de PIB. *"Em pouco tempo não vamos mais tolerar a loja da esquina que não atende 24 por 7."*

### É uma bolha?

O hype é inegável e maior do que nos ciclos anteriores — porque a velocidade das transformações é maior e o medo do investidor de perder a aposta certa também é.

Mas a avaliação de quem está dentro: **não é bolha.** Não há precedente histórico para as curvas de crescimento de receita e de adoção que estão sendo observadas.

### Como fica o outsourcing?

Com agentes fazendo o tipo de trabalho que antes ia para parceiros externos, uma empresa iniciou uma **redução incremental e transparente**: começou com 3% como experimento, **com os líderes dos fornecedores avisados antecipadamente e convidados a repensar juntos como o valor da parceria se redefine.**

A lógica declarada: fazer mudanças pequenas e observar o efeito cascata antes de qualquer decisão maior. **O sistema é complexo demais para saltos bruscos.**

## 12. Perguntas ainda em aberto

### Como avaliar e promover pessoas quando entregar código, análise ou processo deixa de ser o principal entregável?

Ninguém resolveu. Avaliação de cima para baixo infla, 360 vira caça às bruxas, matriz de competências pune quem superdesenvolveu uma habilidade. A pista mais promissora: KPIs coletivos + o modelo de "missão" no lugar de título permanente.

### Tempo de review como indicador de cultura

Quanto tempo o revisor realmente fica lendo o código? Como esse indicador varia com o volume crescente de entregas geradas por agentes — e o que ele revela sobre a ansiedade real do time e sobre a qualidade do processo?

### Erros de segunda ordem na base de conhecimento

O que acontece quando a base que alimenta todos os agentes abstrai algo errado? Como auditar e garantir que ela não acumula erros silenciosos que contaminam decisões ao longo do tempo?

### Como atravessar de indivíduo produtivo para time produtivo

A adoção individual está resolvida em várias empresas. A velocidade organizacional não mudou proporcionalmente em nenhuma. É o degrau mais importante e o menos compreendido.

### A camada intermediária de compartilhamento

Todo mundo constrói. Não existe ainda o equivalente da "planilha compartilhada" para o que o negócio constrói com IA — um lugar seguro entre o rascunho local e a produção.

### Governança do conhecimento fora da engenharia

O conhecimento está indo para silos por ferramenta e por pessoa. Ninguém tem um modelo bom de repositório vivo, versionado e consultável do que a empresa inteira está aprendendo.

### O papel de produto quando a engenharia acelera

Como integrar especificação e implementação no mesmo lugar? Como fica o ciclo de descoberta quando a entrega deixa de ser o gargalo?

### Duas tabelas salariais no mesmo lugar

Já chegam descrições de vaga de áreas de negócio que são, na prática, vagas técnicas. A pessoa entra e em trinta dias percebe que deveria estar na outra faixa. Classificado por quem vive isso como potencial de erro grande nos próximos doze meses.

### Não existe progressão de IC sênior para a camada de orquestração

Os perfis são diferentes. Em algum momento se contrata de fora — e não há caminho interno. Isso quebra a promessa implícita de carreira para os melhores individuais.

### Priorizar a transformação do negócio ou a da própria área?

O dilema mais honesto que apareceu, de um CHRO:

> Parte do meu time diz que precisamos parar e reimaginar o RH, urgente. Do outro lado, há tanta coisa para fazer com o negócio. Alguém diz "faça os dois", que é a resposta fácil. Eu acho difícil. O que eu priorizo?

## Como usar este material

1. **Não copie o playbook. Adapte.** A mesma sequência que funcionou numa empresa com infraestrutura de dados curada não funciona onde a infra não está pronta. Descubra em que nível você está antes de escolher o próximo passo.
2. **O melhor case não é o mais avançado.** Case muito inicial e as pessoas saem; avançado demais e se perde. O que ensina é o case na média ou um pouco acima do seu grupo — porque mostra caminhos diferentes para o mesmo problema que você já tem.
3. **O valor veio da abertura tática.** Os encontros que mais renderam foram aqueles em que alguém mostrou o próprio código, os próprios arquivos, os próprios erros e o que ainda não sabe.

E uma observação sobre onde estão os melhores aprendizados: os cases mais fortes não vieram necessariamente das maiores empresas. Vieram de quem está **construindo do zero de novo** ou de quem tem **restrição de recurso**.

> Não existe engenheiro melhor no mundo que o palhaço de circo. Ele faz uma bicicleta com dois pedaços de cano e um aro de barril — porque tem restrição.
