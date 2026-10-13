# Política de dados do plugin Endeavor

Documento voltado ao founder. O concierge apresenta este conteúdo quando o founder pergunta sobre
dados, privacidade, confidencialidade, memória, gravações ou segurança. Apresente em prosa, na voz
do founder, sem tabelas ASCII. Não invente nada que não esteja aqui; se a pergunta não estiver
coberta, diga que o time da Endeavor responde.

Versão 2 · agosto de 2026. Vale para o plugin Endeavor rodando no Claude do founder.

---

## Resumo em seis linhas

1. O plugin lê o que a Endeavor já tem registrado sobre a sua empresa e sobre a rede.
2. O plugin grava o histórico das suas análises, um dossiê vivo da empresa e a memória das suas
   conversas, para não te fazer repetir contexto.
3. O que você escreve no chat só sai do seu Claude quando você aciona uma capacidade do plugin. O
   plugin pode pedir que o seu Claude use os seus conectores, mas nunca se conecta direto na sua stack.
4. **O que está registrado sobre a empresa é visível para os sócios dela.** Vale a pena ler a seção 3.
5. Números da sua empresa não chegam a outro founder, e os deles não chegam a você.
6. Você pode contestar, corrigir ou pedir a exclusão do que gravamos.

---

## 1. Quais dados o plugin acessa

### Sobre a sua empresa, no registro da Endeavor
Dados que a Endeavor já mantém pela relação do programa — não vêm do seu Claude nem de coleta na web.

- **Cadastro**: nome, setor, vertical, modelo de negócio, estágio, descrição, ano de fundação,
  estado, site, LinkedIn, e quem é o seu contato na Endeavor.
- **Prioridades e desafios** que você e o time da Endeavor registraram, com o texto completo: o
  desafio, o contexto, o impacto, as perguntas-chave, as alternativas já testadas e os momentos
  decisivos.
- **Mentorias da empresa**: data, mentor, tema, duração, resumo, tópicos e insights.
- **Notas das sessões**, geradas automaticamente a partir da gravação, e o **link da gravação**
  quando existir. Você abre a gravação; o plugin não abre nem transcreve por você.
- **Avaliações que a empresa deu** às mentorias, com a nota e o comentário escrito.
- **Pessoas da empresa** com relação ativa com a Endeavor: nome, cargo, LinkedIn.
- **Métricas que vocês reportaram** à Endeavor, usadas na análise da própria empresa.
- **Agenda**: próximas conexões marcadas e próximos eventos da rede.

Cobertura, com honestidade: resumos ricos de sessão existem de 2023/2024 em diante. Antes disso
costuma haver só título, tema e data. Ausência de registro não significa que não aconteceu.

### Sobre você, individualmente
**Horas de giveback**, quando você doa tempo à rede. Esse dado é da pessoa logada, não da empresa —
não aparece para o seu sócio.

### Sobre a rede
- **Mentores ativos**: nome, cargo e empresa atuais, biografia, competências, histórico de cargos e
  empresas por onde passaram, e o LinkedIn.
- **Outras empresas da rede**: empreendedores Endeavor ativos e a turma atual do Scale-Up, com o que
  a empresa faz, setor, vertical, modelo, estado, ano, site, e as pessoas dela com nome, cargo e
  LinkedIn. Serve para você achar pares e benchmark.

Sobre outras empresas você **não** recebe: faturamento, captação, valuation, número de funcionários,
notas de mentoria, detalhe de sessão, nem os assuntos que aquela empresa levou à rede. E o inverso
também vale — **a sua empresa aparece para outros founders no mesmo nível**: o que ela faz, o
cadastro básico e as pessoas de contato. Nada de números, nada de histórico de conversas.

### Seus conectores e a sua stack: quem faz o quê
O plugin **pode pedir ao seu Claude** que use os conectores que **você** já autorizou ali — agenda,
e-mail, Drive, CRM — para tarefas do fluxo: agendar uma mentoria, puxar um número que você
mencionou, salvar um plano. Quem executa é o seu Claude, com as suas credenciais, dentro da sua
conversa. Você aprova ou recusa como aprova qualquer outra ação.

O plugin da Endeavor **nunca conecta direto** nas APIs, MCPs ou sistemas da sua stack. Não guarda
credencial sua, não tem token da sua ferramenta, não roda integração no servidor da Endeavor contra
os seus sistemas.

Consequência prática: o que voltar de um conector seu entra na conversa e pode ser usado ali. Se
alimentar uma análise que você pediu, vai junto no contexto — e aí vale a seção 4.

### O que o plugin não acessa
- Nada seu por iniciativa própria: não varre sua caixa de entrada, sua agenda ou seus arquivos, e
  não puxa dado de conector nenhum fora do que você acabou de pedir.
- Dados de outras empresas além do descrito acima.
- Dados financeiros de mentores ou das empresas deles.

---

## 2. Isto é IA, e IA erra

As análises, recomendações e sessões simuladas são geradas por um modelo de linguagem sobre os dados
descritos aqui. Podem conter imprecisão, podem inferir demais a partir de pouco, e não substituem
julgamento seu, do seu board ou de um profissional.

- **As notas de sessão são automáticas**, geradas da gravação. Trate como notas, não como ata oficial.
- **A sessão simulada com mentor é uma simulação** construída a partir de material público e de
  mentorias registradas. Não é o mentor falando, e não deve ser citada como se fosse.
- **A recomendação de mentores é uma sugestão.** A introdução real acontece sempre via Endeavor.

---

## 3. O que os seus sócios enxergam

Esta é a parte que mais gera surpresa, então vai direto.

**O registro é da empresa, não da pessoa.** Qualquer sócio ou executivo cadastrado da sua empresa
que use o plugin enxerga o mesmo conjunto: o cadastro, **as prioridades com o texto completo**, o
histórico de mentorias com **as notas de sessão e os links de gravação**, as avaliações com
comentário, e o dossiê de Go-to-Market. Não há separação por pessoa dentro da empresa.

**O que é individual e não chega ao seu sócio:** as suas horas de giveback, a memória das suas
conversas com o plugin e o perfil que o plugin monta sobre você ao longo do tempo.

Duas recomendações honestas:

- Se um assunto é seu e não da sociedade, **o plugin não é o canal**. Fale com o seu contato de
  relacionamento na Endeavor. O produto foi feito para ser previsível e compartilhado, não para
  guardar segredo de um sócio em relação ao outro.
- O que você conta ao plugin durante um diagnóstico pode ser incorporado ao dossiê da empresa e,
  portanto, ficar visível aos sócios. Considere isso antes de detalhar assunto sensível.

---

## 4. Quais dados o plugin grava, e onde

Dois destinos, e nenhum deles é o registro oficial da Endeavor: o plugin **nunca escreve** no banco
de dados corporativo. Ele só lê de lá.

### Banco do produto, na infraestrutura da Endeavor
- **Dossiê vivo da empresa**: documento em texto com o retrato de Go-to-Market que as análises vão
  construindo. Cada alteração fica registrada com autor e data.
- **Suas contribuições ao dossiê**: quando você adiciona ou contesta uma informação, o texto que
  você escreveu fica guardado com o seu e-mail. A adição entra rotulada como declaração sua; a
  contestação marca o trecho como contestado. **Nada é apagado.**
- **Resultado das suas análises**: o texto e os documentos finais de cada diagnóstico e de cada
  recomendação de mentores, para você consultar depois.
- **Memória das suas conversas**: os eventos do seu fluxo — pedido de análise, escolhas de conexão,
  marcos do processo — e um **perfil consolidado seu**, em texto, que o plugin relê no início de
  cada sessão para não te pedir o mesmo contexto duas vezes.

### Telemetria de produto
Registro de uso, para sabermos se o produto funciona e onde falha: qual capacidade você acionou,
quanto tempo levou, se deu erro, se a entrega chegou à sua tela, e a nota e o comentário que você deu.

Com transparência sobre o alcance: hoje essa telemetria também guarda **o conteúdo** do que passou
pelo produto — o texto da análise entregue, a pergunta que você fez à rede, o seu comentário livre.
Está no roteiro reduzir isso ao mínimo necessário. Até lá, o acesso a essa base é restrito conforme
a seção 6.

---

## 5. Como os dados são utilizados

- **Para responder você.** O dado da sua empresa entra no contexto da análise que você pediu e sai
  na resposta que só você recebe.
- **Para não te fazer repetir contexto.** A memória e o dossiê existem para que a segunda conversa
  comece mais adiante que a primeira.
- **Para comparar com a rede, sempre de forma anônima e agregada.** O diagnóstico posiciona você
  contra padrões extraídos de centenas de mentorias, construídos a partir de material
  **anonimizado**: nomes de pessoas e empresas substituídos, valores, percentuais e múltiplos
  removidos. Você recebe o padrão, nunca o caso nominal.
- **Para melhorar o produto.** A telemetria de uso e o seu feedback orientam o roadmap.

### Filtro de confidencialidade antes de cada entrega
Toda análise passa por uma etapa separada de curadoria antes de chegar a você. Ela remove:
identidade e números de outras empresas, benchmarks nominais, notas e volume de mentoria, sinais
internos de staff da Endeavor e dados financeiros de terceiros. No diagnóstico, os números e scores
da **sua própria** empresa são liberados — são seus.

### O que não fazemos
- Não usamos seus dados para treinar modelos de IA.
- Não vendemos, não licenciamos e não compartilhamos seus dados com terceiros comerciais.
- Não mostramos sua empresa como caso nominal a outro founder sem sua autorização explícita.
- Não passamos telefone nem e-mail de ninguém da rede. A introdução é sempre via Endeavor.

---

## 6. Quem tem acesso

- **Você**: tudo que é seu.
- **Sócios e executivos cadastrados da sua empresa**: o registro da empresa, conforme a seção 3.
  Não a sua memória nem o seu perfil individual.
- **Founders de outras empresas**: só o perfil da sua empresa descrito na seção 1. A autorização do
  plugin é pelo vínculo entre o e-mail do seu login e a sua empresa no cadastro da Endeavor; pedido
  para outra empresa é recusado.
- **Time da Endeavor**: o squad do produto e os analistas que curam os dossiês, para operar e
  melhorar o serviço, sujeitos às políticas internas de confidencialidade.
- **Parceiro de engenharia contratado pela Endeavor**: acesso técnico à infraestrutura para
  desenvolvimento e suporte, sob contrato.
- **Provedores de infraestrutura**, como subprocessadores: Anthropic (modelo), Google Cloud (banco
  analítico), AWS (banco do produto), PostHog (telemetria), Fireflies (gravação e transcrição das
  sessões).

---

## 7. Seus direitos, e como exercer

- **Ver**: peça ao plugin o histórico da sua empresa, o dossiê ou as análises anteriores.
- **Corrigir e contestar**: se algo está errado, diga ao plugin. A correção entra registrada como
  declaração sua e um analista processa. O registro original não é apagado.
- **Excluir**: peça a exclusão da memória das suas conversas, do seu perfil consolidado ou do
  dossiê. O pedido vai ao time da Endeavor e é executado por lá.
- **Recusar a memória**: você pode usar o plugin sem que o histórico das conversas seja gravado.
  Nesse caso, precisa recontextualizar a cada sessão.
- **Falar com alguém**: qualquer pedido ou dúvida sobre dados vai ao time do programa, pelo canal do
  seu contato de relacionamento.

---

## Guardrails para o concierge

- Não prometa prazo de exclusão, fornecedores fora da lista da seção 6, nem certificação de
  segurança. Se perguntarem, diga que o time da Endeavor responde.
- Não afirme que a telemetria não guarda conteúdo — hoje guarda, conforme a seção 4.
- Se o founder perguntar se a Endeavor "integra com o meu CRM/ERP/agenda", responda pela seção 1:
  quem integra é o Claude dele, com as credenciais dele. Nunca sugira que ele passe credencial ao time.
- Se o founder pedir dado de outra empresa além do descrito na seção 1, recuse e ofereça a Busca na
  rede ou o benchmark anônimo do Diagnóstico.
- Se o founder pedir exclusão, confirme que registrou o pedido e diga que passa ao time. Não afirme
  que já apagou.
- Sobre gravações: entregue o link para o founder abrir. Não abra nem transcreva. Se ele não
  conseguir acessar, explique que a gravação fica no Fireflies da Endeavor e o acesso é de quem
  participou.
- Pergunta sobre o que o sócio enxerga: responda pela seção 3, sem suavizar. É melhor o founder
  saber antes.

<!-- MANUTENÇÃO — não exibir ao founder.
     A seção 1 afirma que o founder NÃO recebe "os assuntos que outra empresa levou à rede". Isso
     descreve o estado correto, não o estado atual: hoje a busca na rede ainda projeta o campo de
     temas por empresa. Este documento só pode ir ao MOU e ao onboarding depois que esse campo sair
     da projeção do recorte de empresas no servidor e da instrução de apresentação em
     references/buscar-rede.md. Ver o card correspondente na análise de dados e personalização. -->
