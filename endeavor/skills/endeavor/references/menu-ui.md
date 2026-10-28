# Menu /endeavor: o cardápio

**Antes de tudo, saiba qual dos dois casos é o seu.**

**Caso A — o `open_menu` respondeu, mas o host não renderiza widget.**

**Menu novo.** Se o texto da tool tiver o bloco **Explore**, é o menu novo: saudação, **Seus desafios**
numerados com as conexões sugeridas embaixo de cada um, **Explore** continuando a numeração (Explorar a
Rede, Buscar Conhecimento, Benchmark AI B2B, Criar Rotina, Mandar feedback ou ideia), a linha do "Saber
mais" com o link, **Sua agenda** (Suas conexões e Próximos encontros Endeavor, sem número), as outras
empresas e a linha dos dados. Renderize como veio. Número de desafio: siga com aquele desafio,
perguntando se ele quer conexões, insights ou atualizar. Número do Explore: o atalho, como nas frases do
menu novo do Bloco 0.

**Menu de hoje** (sem o bloco **Explore**). A tool devolve, além do
payload, um cardápio em TEXTO já pronto, e ele **já lista os desafios do founder numerados no
topo**, com as portas continuando a numeração (se ele tem 3 desafios, as portas vão de 4 a 8).
Depois das portas ele traz o bloco **Sua agenda**, com duas seções — **Conexões** e **Eventos**,
até 3 linhas em cada, no mesmo recorte do widget. Seção sem dado leva uma linha honesta em vez de
sumir, e agenda que não pôde ser lida vira a frase de indisponível: nunca as duas coisas juntas.
As linhas da agenda **não entram na numeração**, porque são informação e não alvo de escolha.
**Renderize o texto que a tool devolveu, como está.** Não use o cardápio estático deste arquivo:
a numeração seria outra, e o founder respondendo "4" cairia no fluxo errado.

Sem widget não existe detalhe local: ver a ficha de um desafio custa um turno, chamando `priority`
com `acao: "listar"`. É degradação aceita — diga ao founder que você abre a ficha, em vez de
deixá-lo esperando um clique que naquele host não existe.

**Caso B — o `open_menu` não está no catálogo, falhou, ou demorou demais.** Aí não há desafio
nem agenda para listar (os dois vêm no payload da tool), e o cardápio é o de sempre, abaixo.

---

Apresente o cardápio cru, sem chamar o MCP, como lista numerada de 1 a 5 sob um cabeçalho. Não use
popup de escolha (a tool de escolha só comporta quatro opções por pergunta). Voz da Endeavor: direto,
concreto, profissional e simples. Sem travessão, sem emoji, sem jargão de IA.

Texto de abertura e cardápio (renderize como está):

> Produto em Beta. Mande seus feedbacks por aqui, no item Mandar feedback ou ideia. Obrigado!
>
> **Explore**
> 1. Explorar a Rede: os mentores e as pessoas da rede certos para o seu desafio
> 2. Buscar Conhecimento: o que a rede já aprendeu, no Cérebro Endeavor
> 3. Benchmark AI B2B: como startups B2B de IA se comparam
> 4. Criar Rotina: um prompt pronto para a Endeavor entrar na rotina do seu Claude
> 5. Mandar feedback ou ideia: sobre o plugin, uma conexão ou a Endeavor. O time lê tudo
>
> Saber mais sobre o plugin e o programa: https://scaleup.endeavor.org.br
>
> Escolha um número ou me conte com suas palavras, que eu vou tentar te ajudar da melhor forma.
>
> Se quiser entender o que a Endeavor faz com os seus dados, é só perguntar.

## Regras
- Renderize a abertura, os itens e a linha final como estão. Itens sempre numerados de 1 a 5, na
  ordem acima, sob um cabeçalho. O founder responde pelo número, pelo nome ou com as próprias
  palavras.
- Desafio descrito direto no campo aberto: trate como o item 1 e siga para o Bloco 1 sem repetir o
  menu.
- Sem travessão, sem emoji, sem separador de ponto no meio dos itens.
- A linha do "Saber mais" fica fora da numeração, logo depois do item 5, com o link como está.
- A linha final sobre dados fica fora da numeração, sempre por último. Ela não é uma sexta opção:
  o founder chega nela perguntando, não escolhendo número.
- **As regras acima valem para o caso B.** No caso A quem manda é o texto que a tool devolveu: ele
  já vem com a abertura, os desafios, as portas renumeradas, o bloco da agenda e a linha final no
  lugar certo.
- No caso B a agenda não tem número: quem pedir a próxima conexão, os eventos ou o preparo vai para o
  Bloco 6. No menu de hoje do caso A, o item "Minha agenda" continua sendo a porta para o preparo da
  próxima conexão, não um jeito de ver a lista, que já está na tela.
