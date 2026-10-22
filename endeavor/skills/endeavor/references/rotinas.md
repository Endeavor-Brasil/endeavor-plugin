# Rotinas prontas

Seis prompts para o founder criar, no Claude dele, uma rotina que usa a Endeavor. Entregue o prompt exatamente como está aqui, sem resumir nem completar.

| Rotina | Use se você | Onde roda |
| --- | --- | --- |
| A · Rotina semanal | Quer uma revisão semanal automática a partir da sua semana (agenda, notas de reunião, second brain). | Rotina (Claude Code) ou Agendados (chat, Cowork) |
| B · Revisão quinzenal | Quer algo leve, sem ler reuniões nem emails: só o que a Endeavor já tem sobre você. | Rotina (Claude Code) ou Agendados (chat, Cowork) |
| C · Pós-reunião de diretoria | Tem reunião de diretoria ou board recorrente e quer transformar a ata em próximos passos. | Agendados ou Rotina |
| D · Second brain | Já usa um second brain e quer que ele converse com a Endeavor. | No Claude que mantém o seu second brain |
| E · Chief of staff de IA | Já tem um chief of staff de IA e quer um passo da Endeavor na revisão dele. | Na rotina do seu chief of staff |
| F · Sem rotina nenhuma | Não tem rotina e quer o mínimo: um lembrete mensal e uma instrução permanente. | Preferências + Agendados |

## A · Rotina semanal

**Use se você:** Quer uma revisão semanal automática a partir da sua semana (agenda, notas de reunião, second brain).

**Onde roda:** Rotina (Claude Code) ou Agendados (chat, Cowork)

```text
Quero uma rotina semanal com o plugin da Endeavor. Antes de criar, me mostre a rotina completa, com um exemplo de como o resumo vai chegar, e espere o meu "sim".
 
REGRAS (copie dentro da rotina, sem mudar)
- Só lê. Não registra, não altera nem arquiva desafio na Endeavor, não pede conexão e não manda mensagem para ninguém além de mim.
- Só usa as fontes que eu escolher agora. Não conecta ferramenta nova.
- Minhas reuniões, emails e notas não vão para a Endeavor. Para buscar pessoas, só vai uma descrição curta do desafio.
 
PARA MONTAR
1. Veja se o plugin da Endeavor responde (se não, pare e me diga como ativar), que ferramentas estão conectadas aqui e se tenho um second brain ou pasta de notas.
2. Numa rodada só, me pergunte: quais fontes ler (sugira agenda e notas de reunião), onde receber o resumo (DM no Slack, email para mim ou só aqui; com Slack e email, o Slack leva a versão curta e o email a completa) e dia e horário (sugira sexta, 16h). Sem fontes, a rotina usa só meus desafios e conexões na Endeavor e termina perguntando o que pesou na semana.
3. Me mostre a rotina, diga qual recurso de agendamento vai usar e o que acontece se o computador estiver fechado. Com o meu sim, crie e ofereça rodar uma vez agora.
 
A ROTINA (escreva isto dentro dela)
1. Ler a semana útil (segunda a sexta) nas fontes escolhidas; se rodar fora do dia combinado, a última semana completa. Com second brain, começar por ele: o que eu corrigi ou confirmei vale mais que resumo automático. Se o resumo da semana já foi enviado, não mandar de novo.
2. Achar de 1 a 3 desafios que pedem mentoria, entre os que mais apareceram (frequência e peso), com onde e quando. Entra decisão estratégica ou tática em aberto, em que a experiência de quem já passou muda o resultado nas próximas semanas (ex.: sair de founder-led sales, contratar ou não um head comercial). Fica de fora tarefa, problema técnico ou operacional que o time resolve sozinho e o que se resolve em poucos dias. Se nada passar, dizer "Nenhum desafio para mentoria esta semana" e não buscar nomes.
3. Ler meus desafios registrados na Endeavor e ligar cada desafio da semana a um deles pelo conteúdo, não só pelo título, ou marcar como novo. Registrado que não apareceu ou não passou no filtro fica de fora.
4. Para a decisão que vou tomar mais cedo e que mais pesa: pedir os mentores à Endeavor (se registrada) ou buscar na rede (se nova, ou se a Endeavor não devolver nomes, avisando numa linha). Usar os 3 primeiros nomes, na ordem, com o porquê em 1 frase e só informação pública. Nunca escolher, reordenar nem acrescentar nomes. Conferir a grafia de nomes e empresas.
5. Mandar o resumo em até 15 linhas antes do bloco: 1 linha com a semana e a contagem (desafios, quantos mudaram, quantos novos); o mais urgente, com prazo, o que trava e os 3 nomes com empresa e porquê; 1 linha por desafio (registrado ou novo, o que mudou, data); e "Nada foi registrado nem enviado." No email, versão visual: o mais urgente em destaque, um bloco por desafio e o texto para colar no fim.
6. Fechar com o bloco para eu colar no Claude, ou "Nada a registrar esta semana.":
/endeavor:endeavor Registrar os desafios da semana.
Atualizar: <título exato do desafio registrado>. O que mudou: "<1 a 2 frases, com a data>"
Novo: <título provisório>. Contexto: "<onde apareceu, quando e o que trava>"
7. Se a Endeavor falhar, mandar só os desafios da semana, sem nomes nem bloco, e dizer isso numa linha. Se outra fonte falhar, mandar o que deu e dizer o que faltou.
```

## B · Revisão quinzenal

**Use se você:** Quer algo leve, sem ler reuniões nem emails: só o que a Endeavor já tem sobre você.

**Onde roda:** Rotina (Claude Code) ou Agendados (chat, Cowork)

```text
Quero uma revisão quinzenal com o plugin da Endeavor, só com o que a Endeavor já tem sobre mim. Antes de criar, me mostre a revisão completa e espere o meu "sim".
 
REGRAS (copie dentro da revisão, sem mudar)
- Só lê. Não registra, não altera nem arquiva desafio na Endeavor, não pede conexão, não se inscreve em encontro e não manda mensagem para ninguém além de mim.
- Não lê reuniões, emails, notas nem outras ferramentas. Não conecta ferramenta nova.
 
PARA MONTAR
1. Veja se o plugin da Endeavor responde. Se não, pare e me diga como ativar.
2. Numa rodada só, me pergunte onde receber o resumo (DM no Slack, email para mim ou só aqui) e dia e horário (sugira segunda, 8h, a cada 15 dias).
3. Me mostre a revisão, diga qual recurso de agendamento vai usar e o que acontece se o computador estiver fechado. Com o meu sim, crie e ofereça rodar uma vez agora.
 
A REVISÃO (escreva isto dentro dela)
1. Ler na Endeavor meus desafios registrados, minhas conexões e os próximos encontros.
2. Apontar os desafios sem conexão pedida nem marcada e as conexões ainda sem horário.
3. Para o desafio mais urgente, pedir os mentores à Endeavor. Usar os 3 primeiros nomes, na ordem, com o porquê. Nunca escolher por conta própria.
4. Listar os encontros das próximas 2 semanas que combinam com algum desafio, com data e porquê.
5. Mandar o resumo em até 15 linhas, terminando com "O que mudou nesses 15 dias? Nada foi registrado nem enviado."
6. Fechar com o bloco para eu colar no Claude:
/endeavor:endeavor Atualizar meus desafios.
Atualizar: <título>. O que mudou: "<1 a 2 frases>"
7. Se algo falhar, mandar o que deu e dizer numa linha o que faltou.
```

## C · Pós-reunião de diretoria

**Use se você:** Tem reunião de diretoria ou board recorrente e quer transformar a ata em próximos passos.

**Onde roda:** Agendados ou Rotina

```text
Quero uma rotina com o plugin da Endeavor que rode no dia seguinte a cada reunião de [diretoria/board]. Antes de criar, me mostre a rotina completa e espere o meu "sim".
 
REGRAS (copie dentro da rotina, sem mudar)
- Só lê. Não registra, não altera nem arquiva desafio na Endeavor, não pede conexão e não manda mensagem para ninguém além de mim.
- Só lê a ata ou as notas da reunião que eu indicar agora. Não conecta ferramenta nova.
- A ata e as notas não vão para a Endeavor. Para buscar pessoas, só vai uma descrição curta da decisão.
 
PARA MONTAR
1. Veja se o plugin da Endeavor responde (se não, pare e me diga como ativar), quais reuniões recorrentes da agenda parecem de diretoria ou board e onde ficam as atas ou notas.
2. Numa rodada só, me pergunte: qual é a reunião (ou a recorrência, se a agenda não estiver conectada), onde fica a ata, onde receber o resumo (DM no Slack, email para mim ou só aqui) e o horário no dia seguinte (sugira 9h).
3. Me mostre a rotina, diga qual recurso de agendamento vai usar e o que acontece se o computador estiver fechado. Com o meu sim, crie e ofereça rodar uma vez agora, com a ata da última reunião.
 
A ROTINA (escreva isto dentro dela)
1. Achar a ata ou as notas da reunião. Se não achar, me pedir a ata numa linha e parar.
2. Listar até 5 decisões em aberto ou problemas sem dono, com uma frase de contexto cada.
3. Ler meus desafios registrados na Endeavor e ligar cada item a um registrado, ou marcar como novo.
4. Para a decisão mais crítica, pedir os mentores à Endeavor (se ligada a um desafio registrado) ou buscar na rede (se nova). Usar os 3 primeiros nomes, na ordem, com o porquê. Nunca escolher por conta própria.
5. Mandar o resumo em até 20 linhas, terminando com "Nada foi registrado nem enviado."
6. Fechar com o bloco para eu colar no Claude:
/endeavor:endeavor Registrar os desafios da reunião de [diretoria/board].
Atualizar: <título>. O que mudou: "<1 a 2 frases>"
Novo: <título provisório>. Contexto: "<o que ficou em aberto e o que trava>"
7. Se algo falhar, mandar o que deu e dizer numa linha o que faltou.
```

## D · Second brain

**Use se você:** Já usa um second brain e quer que ele converse com a Endeavor.

**Onde roda:** No Claude que mantém o seu second brain

```text
Quero ligar o meu second brain ao plugin da Endeavor. Antes de mudar qualquer coisa, me mostre a regra e espere o meu "sim".
 
REGRAS (copie dentro da regra, sem mudar)
- Só lê. Não registra, não altera nem arquiva desafio na Endeavor, não pede conexão e não manda mensagem para ninguém.
- Não muda as outras regras do second brain. Não conecta ferramenta nova.
- O conteúdo do second brain não vai para a Endeavor. Para buscar pessoas, só vai uma descrição curta do desafio.
 
PARA MONTAR
1. Veja se o plugin da Endeavor responde (se não, pare e me diga como ativar), onde está o meu second brain e onde ficam as instruções dele (CLAUDE.md, schema, README ou equivalente). Se não achar, me pergunte.
2. Numa rodada só, me pergunte em quais momentos a regra entra (sugira: ao ingerir nota de reunião ou ata e na revisão semanal) e onde fica a página de desafios ativos (sugira um nome no padrão do brain).
3. Me mostre o texto da regra, o arquivo e o ponto onde ela entra e como fica a página. Com o meu sim, salve e ofereça testar com a última nota de reunião.
 
A REGRA (escreva isto dentro dela)
1. Nesses momentos, procurar até 3 desafios de negócio em aberto (não tarefas).
2. Ler meus desafios registrados e minhas conexões na Endeavor e ligar cada desafio a um registrado, ou marcar como novo.
3. Atualizar a página de desafios ativos: título, se está registrado na Endeavor, mentor sugerido, conexão pedida e data da última menção.
4. Só se eu pedir, buscar pessoas: pedir os mentores à Endeavor (se registrado) ou buscar na rede (se novo). Usar os 3 primeiros nomes, na ordem, com o porquê. Nunca escolher por conta própria.
5. Fechar com o bloco para eu colar no Claude:
/endeavor:endeavor Registrar os desafios do meu second brain.
Atualizar: <título>. O que mudou: "<1 a 2 frases>"
Novo: <título provisório>. Contexto: "<onde apareceu e o que trava>"
6. Se o plugin falhar, seguir com a ingestão normal e dizer numa linha o que faltou.
```

## E · Chief of staff de IA

**Use se você:** Já tem um chief of staff de IA e quer um passo da Endeavor na revisão dele.

**Onde roda:** Na rotina do seu chief of staff

```text
Quero incluir o plugin da Endeavor na revisão [semanal] do meu chief of staff de IA. Antes de mudar qualquer coisa, me mostre a alteração e espere o meu "sim".
 
REGRAS (copie dentro da rotina, sem mudar)
- Só lê. Não registra, não altera nem arquiva desafio na Endeavor, não pede conexão e não manda mensagem para ninguém além de mim.
- Não muda os outros passos da rotina. Não abre fonte nova nem conecta ferramenta nova.
- O que o chief of staff lê não vai para a Endeavor. Para buscar pessoas, só vai uma descrição curta da decisão.
 
PARA MONTAR
1. Veja se o plugin da Endeavor responde (se não, pare e me diga como ativar) e onde a rotina do chief of staff está configurada, com que frequência roda e onde o resumo chega. Se não achar, me pergunte.
2. Numa rodada só, me pergunte em qual revisão o passo entra (sugira a semanal) e se o bloco da Endeavor vai no fim do resumo de sempre ou numa mensagem separada (sugira no fim).
3. Me mostre o antes e o depois do trecho que muda. Com o meu sim, aplique e ofereça rodar a revisão uma vez agora.
 
O PASSO NOVO (escreva isto dentro da rotina)
1. Usar só o que o chief of staff já leu nesta revisão e encontrar a decisão mais difícil em aberto.
2. Ler meus desafios registrados e os próximos encontros na Endeavor e ligar a decisão a um desafio, ou marcar como nova.
3. Pedir os mentores à Endeavor (se ligada a um desafio) ou buscar na rede (se nova). Usar os 3 primeiros nomes, na ordem, com o porquê. Nunca escolher por conta própria.
4. Escrever o bloco da Endeavor em até 8 linhas, com os encontros que combinam, terminando com "Nada foi registrado nem enviado na Endeavor."
5. Se algo mudou, fechar com o bloco para eu colar no Claude:
/endeavor:endeavor Atualizar meus desafios.
Atualizar: <título>. O que mudou: "<1 a 2 frases>"
Novo: <título provisório>. Contexto: "<onde apareceu e o que trava>"
6. Se o plugin falhar, seguir com o resto da revisão e dizer numa linha o que faltou.
```

## F · Sem rotina nenhuma

**Use se você:** Não tem rotina e quer o mínimo: um lembrete mensal e uma instrução permanente.

**Onde roda:** Preferências + Agendados

```text
Quero usar o plugin da Endeavor sem montar uma rotina complexa. Antes de salvar qualquer coisa, me mostre e espere o meu "sim".
 
O QUE CRIAR
1. Uma instrução permanente: quando eu discutir uma decisão difícil de negócio (contratação de executivo, pricing, expansão, captação, go-to-market), você me pergunta se quero buscar na rede Endeavor quem já viveu isso.
2. Um lembrete mensal com os meus desafios registrados na Endeavor.
 
REGRAS (copie dentro do lembrete, sem mudar)
- Nada é registrado, alterado ou arquivado na Endeavor sem eu pedir. Ninguém recebe convite nem mensagem além de mim.
- Minhas conversas não vão para a Endeavor. Se eu aceitar buscar na rede, só vai uma descrição curta da decisão.
 
PARA MONTAR
1. Veja se o plugin da Endeavor responde (se não, pare e me diga como ativar), onde dá para salvar uma instrução permanente aqui e qual recurso de agendamento existe.
2. Numa rodada só, me pergunte onde receber o lembrete (DM no Slack, email para mim ou só aqui) e dia e horário (sugira o primeiro dia útil do mês, 9h).
3. Me mostre a instrução, onde ela fica salva e o lembrete. Com o meu sim, salve, crie e ofereça rodar o lembrete uma vez agora.
 
O LEMBRETE (escreva isto dentro dele)
1. Ler meus desafios registrados e minhas próximas conexões na Endeavor.
2. Uma linha por desafio: título e se tem conexão pedida ou marcada.
3. Perguntar "Algum desses mudou ou já foi resolvido?", em até 10 linhas, terminando com "Nada foi registrado nem enviado."
4. Fechar com o bloco para eu colar no Claude:
/endeavor:endeavor Atualizar meus desafios.
Atualizar: <título>. O que mudou: "<1 a 2 frases>"
Arquivar: <título do desafio resolvido>
5. Se o plugin falhar, dizer numa linha o que faltou.
```

## Instalar o MCP Endeavor

1. No Claude, clique no seu perfil e vá em Configurações.
2. No menu lateral, em Personalizar, abra Plugins.
3. Adicionar → Adicionar marketplace → Adicionar de um repositório, e cole: Endeavor-Brasil/endeavor-plugin
4. O plugin aparece na aba Pessoal: clique no + e depois na engrenagem.
5. Na aba Conectores: Instalar → Adicionar → Vincular. Entre com o seu e-mail e a senha inicial do acesso.
6. No chat, digite /endeavor.
