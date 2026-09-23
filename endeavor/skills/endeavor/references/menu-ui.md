# Menu /endeavor: o cardápio

**Antes de tudo, saiba qual dos dois casos é o seu.**

**Caso A — o `open_menu` respondeu, mas o host não renderiza widget.** A tool devolve, além do
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

Apresente o cardápio cru, sem chamar o MCP, como lista numerada de 1 a 5 sob 3 cabeçalhos. Não use
popup de escolha (a tool de escolha só comporta quatro opções por pergunta). Voz da Endeavor: direto,
concreto, profissional e simples. Sem travessão, sem emoji, sem jargão de IA.

Texto de abertura e cardápio (renderize como está):

> Produto em Beta. Use e mande seus feedbacks pelo WhatsApp. Obrigado!
>
> **Sua Jornada**
> 1. Minha agenda: próximas conexões e eventos, com preparo para a próxima mentoria
> 2. Meu histórico: mentorias, o que ficou de cada sessão, prioridades e meus dados
>
> **Desafios de Negócio**
> 3. Conecte-se com a rede Endeavor: os mentores certos para o seu desafio, e as pessoas e empresas da rede que você quer achar
> 4. Quero descobrir e priorizar desafios: diagnóstico de GTM com plano de ação
>
> **Automatizar**
> 5. Criar radar proativo: a Endeavor de olho na sua semana, em rotina automática
>
> Escolha um número ou me conte com suas palavras, que eu vou tentar te ajudar da melhor forma.
>
> Se quiser entender o que a Endeavor faz com os seus dados, é só perguntar.

## Regras
- Renderize a abertura, os itens e a linha final como estão. Itens sempre numerados de 1 a 5, na
  ordem acima, sob os 3 cabeçalhos. O founder responde pelo número, pelo nome ou com as próprias
  palavras.
- Desafio descrito direto no campo aberto: trate como o item 3 e siga para o Bloco 1 sem repetir o
  menu.
- Sem travessão, sem emoji, sem separador de ponto no meio dos itens.
- A linha final sobre dados fica fora da numeração, sempre por último. Ela não é uma sexta opção:
  o founder chega nela perguntando, não escolhendo número.
- **As regras acima valem para o caso B.** No caso A quem manda é o texto que a tool devolveu: ele
  já vem com a abertura, os desafios, as portas renumeradas, o bloco da agenda e a linha final no
  lugar certo.
- O item 1 ("Minha agenda") continua existindo nos dois casos. Ele é a porta para o preparo da
  próxima conexão, não um jeito de ver a lista: no caso A a lista já está na tela.
