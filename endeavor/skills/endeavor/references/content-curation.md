# Conteúdo de GTM: dois caminhos

O Bloco 6 entrega conteúdo de duas naturezas diferentes. Você escolhe o caminho, não o founder |
ele só pediu conteúdo. Voz do founder, separador "|", nunca travessão.

| Caminho | O que é | Tool | Exige diagnóstico? |
|---|---|---|---|
| **A. Conteúdos da Endeavor** | Peças produzidas pela Endeavor a partir do acervo de mentorias da rede, sempre anonimizado. O que só a Endeavor tem. | `conteudo_para_voce` | **Não** |
| **B. Trilha curada** | Seleção do que existe de melhor no mundo (livros, artigos, vídeos), na ordem certa, ancorada no diagnóstico. | `content_curation` | **Sim** |

## Qual caminho seguir

**Comece sempre pelo A.** Ele funciona para qualquer empresa, sem pré-requisito, e é o conteúdo
proprietário da rede. Só vá para o B quando:

- o founder pedir explicitamente "trilha", "o que estudar", "material para ler"; **ou**
- ele acabou de rodar um diagnóstico e você está oferecendo a ponte do Bloco 2.

Se você tentar o B e a tool disser que não há diagnóstico, **não encerre**: ofereça o A, que não
depende de nada. Uma linha, sem drama:

> "A trilha sai do seu diagnóstico | você ainda não rodou. Mas eu tenho o que a rede aprendeu
> sobre o seu desafio, e isso eu consigo puxar agora. Quer ver?"

---

# Caminho A. Conteúdos da Endeavor

A seleção é do servidor: um match determinístico entre o acervo e os desafios que a **sua empresa**
levou às mentorias. Você não escolhe peça, não ranqueia e não inventa o motivo | tudo vem pronto.

## Fluxo A

### A1. Resolver a empresa

Olhe a memória e o contexto primeiro. Se achar, confirme em 1 linha. Se não achar, pergunte uma
vez, casual. Não chame `varredura_empresa` nem `dossie_empresa` | a tool resolve a empresa sozinha.

### A2. Chamar a tool

```
conteudo_para_voce(empresa)
```

Síncrona: devolve JSON na mesma chamada, sem `job_id` e sem polling. Volta um `hits` com 3 peças
ranqueadas. Use `n` (até 10) só se o founder pedir mais opções.

### A3. Apresentar as opções em prosa

Para cada peça, diga o **título** e o **motivo**, e o motivo sai de `reasons[].explanation` |
literalmente o que veio. Nunca escreva um porquê seu.

> "Peguei o que a rede da Endeavor produziu sobre os seus desafios. Três que fazem sentido agora:
>
> 1. **Para quem e por onde vender** | suas mentorias trataram de "Channel Specific Sales" 9 vezes.
> 2. ...
>
> Qual você quer abrir?"

Se `degraded` vier `true`, **diga antes da lista**, sem enfeitar: não há mentoria classificada para
essa empresa, então a ordem é a da rede inteira e não uma recomendação personalizada. Use o texto
de `note`. Nunca apresente lista degradada como se fosse feita para ele.

### A4. Entregar a peça escolhida

```
conteudo_para_voce(pilar: "06")
```

Devolve o HTML completo. Exiba exatamente como veio: não reconstrua, não aplique estilo, não
resuma, não reordene e não passe por outro modelo. Se o host exigir artifact para exibir, use o
HTML byte a byte.

Depois de exibir, uma linha dizendo que está pronto. Ofereça abrir outra da lista, sem empurrar.

## Contrato da tool (caminho A)

- `conteudo_para_voce(empresa?, pilar?, n?)`: **síncrona**.
  - sem argumento: catálogo (JSON) de todas as peças disponíveis.
  - `empresa`: ranking com `hits[]` (`pillar`, `title`, `lead`, `reasons[]`), `degraded` e `note`.
  - `pilar` (ex.: `"06"`): o HTML completo da peça.
  - `n` (1..10): quantas peças no ranking. Default 3.

## O que NUNCA mostrar ao founder (campos internos)

`score`, `provisionalMapping`, `thesisId`, `mapping_source` e qualquer marcador de estado editorial
que apareça dentro do HTML. São controle interno da Endeavor. Se você vir um selo de estado na
peça, **não comente e não explique** | apenas exiba o arquivo.

## Guardrails (caminho A)

- Nunca gerar, reescrever ou "melhorar" o HTML | ele vem pronto do servidor.
- Nunca inventar peça, número de pilar ou motivo de recomendação.
- Nunca oferecer peça fora do que a tool devolveu.
- Nunca chamar de personalizado o que veio `degraded`.
- Não há telemetria de client aqui: **não** chame `analise_renderizada` (não existe `job_id` neste
  fluxo). O servidor já registra sozinho.

---

# Caminho B. Trilha curada (ancorada no diagnóstico)

O founder recebe uma trilha curta de conteúdos na ordem certa, ancorada no diagnóstico que ele já
fez. A seleção é do servidor (catálogo curado a mão pela Endeavor) | você só resolve a empresa,
chama a tool e apresenta o arquivo como veio.

## Pré-requisito: existe diagnóstico?

A trilha nasce do diagnóstico: a frente crítica e o nível de maturidade vêm de lá. Se a empresa
nunca rodou um diagnóstico de GTM, a tool responde dizendo isso | não insista e não invente uma
trilha. Ofereça o **caminho A** (que não depende de diagnóstico) ou rodar o diagnóstico:

> "A trilha sai do seu diagnóstico de GTM | ele é que aponta onde apertar primeiro. Quer que eu
> rode o diagnóstico agora? Ou posso te mostrar o que a rede já produziu sobre o seu desafio."

Se o founder topar o diagnóstico, vá para o Bloco 2 do SKILL.md.

## Fluxo B

### B1. Resolver a empresa

Olhe a memória e o contexto primeiro. Se achar, confirme em 1 linha. Se não achar, pergunte uma vez,
casual. Não chame `varredura_empresa` nem `dossie_empresa` aqui | a trilha não usa esse contexto.

### B2. Chamar a tool SEM `frente` na primeira vez

```
content_curation(empresa)
```

Omitir `frente` é o default e é o que você deve fazer: o servidor ancora na frente que o diagnóstico
apontou como **crítica**. Essa é a trilha que ataca o gargalo | é ela que carrega a autoridade do
diagnóstico. **Não abra o bloco oferecendo um menu de temas.**

É síncrona: devolve um resource `text/html` na mesma chamada, sem `job_id` e sem polling.

### B3. Apresentar o arquivo

Exiba o resource exatamente como veio. Não reconstrua o HTML, não aplique estilo novo, não resuma,
não reordene os conteúdos e não passe o conteúdo por outro modelo. Se o host exigir um artifact para
exibir um resource, use o texto HTML embutido byte a byte. Não há resumo textual separado.

Depois de exibir, avise o founder que a trilha está pronta e que ele já pode começar.

### B4. Oferecer os outros temas (só depois de entregar)

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

## Contrato da tool (caminho B)

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

## Telemetria (caminho B)

Chame `analise_renderizada(empresa, job_id)` logo após exibir a trilha, usando o `source_job_id` do
`structuredContent` (é o diagnóstico que ancorou a trilha). Best-effort: falha não interrompe nada.

Neste bloco **não** existe a pergunta de feedback | ela é exclusiva do Diagnóstico de GTM (Bloco 2).
Só chame `registrar_feedback` se o founder der uma nota inteira de 1 a 5 espontaneamente.

## Guardrails (caminho B)

- Nunca gerar, reescrever ou "melhorar" o HTML da trilha | ele vem pronto do servidor.
- Nunca inventar conteúdo, link, autor ou ordem. Se um tema não tem trilha, a tool diz | repasse.
- Nunca oferecer tema fora de `available_fronts`.
- Nunca apresentar a trilha como substituta do diagnóstico. Sem diagnóstico, não há trilha |
  ofereça o caminho A, que não depende dele.
- Nunca pedir o nível de maturidade ao founder.
- Voz do founder | separador "|" | nunca travessão.
