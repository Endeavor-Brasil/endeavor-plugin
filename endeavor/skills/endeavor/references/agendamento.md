# Agendar conexão síncrona com o mentor

Você chega aqui depois que o founder escolheu "conexão síncrona" no menu de caminhos do Bloco 1
(`references/experts.md`, seção 8) e escolheu com quem falar.

## Entrada
1. Pergunte a disponibilidade do founder em texto livre ("quais dias/horários funcionam pra
   você nos próximos dias?"). Converta para 2 a 5 horários candidatos em ISO 8601 com timezone
   (assuma o timezone informado na conversa; se não houver pista, pergunte).
2. Pergunte, opcionalmente, se há preferência de período ou observação (ex. "prefiro de manhã").
3. Confirme com o founder os horários e a observação ANTES de chamar a tool — ele precisa
   reconhecer o que vai ser enviado.
4. Chame `agendar_conexao(empresa, disponibilidade, observacao?, mentor_nome, mentor_email?)`.
   `mentor_nome` é o mentor já escolhido. `mentor_email` só se a conversa já tiver esse dado —
   nunca invente. A resposta HTTP é imediata, mas só confirma que o PEDIDO foi registrado — o
   convite ao mentor sai depois, em segundo plano.

## Depois de chamar
- Sucesso: confirme ao founder que o pedido foi enviado e que o time vai acionar o mentor para
  fechar o horário em breve. NÃO prometa uma data/hora específica como certa, nem diga que o
  mentor já foi avisado — isso ainda vai acontecer.
- Erro: avise que não deu para agendar agora e ofereça tentar de novo, ou usar a conexão
  assíncrona como alternativa.

## Guardrails
- Nunca chame `agendar_conexao` sem antes mostrar e ter os horários/observação confirmados pelo
  founder.
- Nunca invente disponibilidade — se o founder não decidiu, pergunte de novo.
