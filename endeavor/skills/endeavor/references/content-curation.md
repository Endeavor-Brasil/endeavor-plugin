# Curadoria de Conteúdo de GTM: a trilha ancorada no diagnóstico

O founder recebe uma trilha curta de conteúdos na ordem certa, ancorada no diagnóstico que ele já
fez. A seleção é do servidor (catálogo curado a mão pela Endeavor) | você só resolve a empresa,
chama a tool e apresenta o arquivo como veio. Voz do founder, separador "|", nunca travessão.

## Pré-requisito: existe diagnóstico?

A trilha nasce do diagnóstico: a frente crítica e o nível de maturidade vêm de lá. Se a empresa
nunca rodou um diagnóstico de GTM, a tool responde dizendo isso | não insista e não invente uma
trilha. Ofereça o caminho certo em 1 linha:

> "A trilha sai do seu diagnóstico de GTM | ele é que aponta onde apertar primeiro. Quer que eu
> rode o diagnóstico agora?"

Se o founder topar, vá para o Bloco 2 do SKILL.md. Se não, encerre sem insistir.

## Fluxo

### 1. Resolver a empresa

Olhe a memória e o contexto primeiro. Se achar, confirme em 1 linha. Se não achar, pergunte uma vez,
casual. Não chame `varredura_empresa` nem `dossie_empresa` aqui | a trilha não usa esse contexto.

### 2. Chamar a tool SEM `frente` na primeira vez

```
content_curation(empresa)
```

Omitir `frente` é o default e é o que você deve fazer: o servidor ancora na frente que o diagnóstico
apontou como **crítica**. Essa é a trilha que ataca o gargalo | é ela que carrega a autoridade do
diagnóstico. **Não abra o bloco oferecendo um menu de temas.**

É síncrona: devolve um resource `text/html` na mesma chamada, sem `job_id` e sem polling.

### 3. Apresentar o arquivo

Exiba o resource exatamente como veio. Não reconstrua o HTML, não aplique estilo novo, não resuma,
não reordene os conteúdos e não passe o conteúdo por outro modelo. Se o host exigir um artifact para
exibir um resource, use o texto HTML embutido byte a byte. Não há resumo textual separado.

Depois de exibir, avise o founder que a trilha está pronta e que ele já pode começar.

### 4. Oferecer os outros temas (só depois de entregar)

O `structuredContent` da resposta traz `available_fronts`: os temas que têm conteúdo **no nível
dele**. Ofereça a partir dessa lista | **nunca** de uma lista sua. O catálogo é curado a mão e muda
sem atualização do plugin, então qualquer taxonomia que você guarde fica errada.

São mais de quatro opções, então use **lista numerada**, não popup de escolha. Algo como:

> "Essa trilha ataca [frente crítica], que é onde seu diagnóstico aponta o gargalo. Se quiser
> estudar outro tema, é só dizer:
>
> 1. [label do available_fronts]
> 2. [label do available_fronts]
> ..."

Quando o founder escolher, re-chame com o slug correspondente:

```
content_curation(empresa, frente: "<slug>")
```

O servidor entrega a trilha daquele tema e o próprio HTML explica que foi escolha dele, citando qual
é a frente crítica. Cada tema gera um arquivo com nome próprio, então as trilhas convivem no chat
sem se sobrescrever.

## Contrato da tool

- `content_curation(empresa, frente?, job_id?)`: **síncrona**. Devolve um texto curto + **um**
  resource `text/html` (`trilha-gtm-{empresa}.html` no default, `trilha-gtm-{empresa}-{tema}.html`
  quando o founder escolhe o tema). Segue o mesmo design system do diagnóstico.
  - `frente` (opcional): um dos slugs `icp`, `posicionamento`, `demanda`, `comercial`, `retencao`,
    `precificacao`, `time_dados`. Omitir = frente crítica do diagnóstico (o default).
  - `job_id` (opcional): ancora num diagnóstico específico. Omita | o servidor usa o mais recente.
  - `structuredContent`: `front`, `front_label`, `front_chosen_by_founder`, `journey_level`,
    `critical_front_name`, `available_fronts` e `files`.

O **nível** de maturidade não é escolha do founder | é o estágio real da empresa, e o servidor o
resolve sozinho. Não peça, não sugira e não tente sobrepor.

## Telemetria

Chame `analise_renderizada(empresa, job_id)` logo após exibir a trilha, usando o `source_job_id` do
`structuredContent` (é o diagnóstico que ancorou a trilha). Best-effort: falha não interrompe nada.

Neste bloco **não** existe a pergunta de feedback | ela é exclusiva do Diagnóstico de GTM (Bloco 2).
Só chame `registrar_feedback` se o founder der uma nota inteira de 1 a 5 espontaneamente.

## Guardrails

- Nunca gerar, reescrever ou "melhorar" o HTML da trilha | ele vem pronto do servidor.
- Nunca inventar conteúdo, link, autor ou ordem. Se um tema não tem trilha, a tool diz | repasse.
- Nunca oferecer tema fora de `available_fronts`.
- Nunca apresentar a trilha como substituta do diagnóstico. Sem diagnóstico, não há trilha.
- Nunca pedir o nível de maturidade ao founder.
- Voz do founder | separador "|" | nunca travessão.
