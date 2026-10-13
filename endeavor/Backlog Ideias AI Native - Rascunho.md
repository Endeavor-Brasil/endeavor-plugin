# Backlog de ideias — AI Native (rascunho para priorização)

> Gerado em 04/07/2026. Consolidação de: Pre-read Comitê 08/07, kanban GitHub (projects/3), calls da squad (jun–jul/2026), testes com founders (Avenia, Hubbi, time interno 03/07), Slack e conversas com a rede (deck 2025, era WhatsApp).
> **Sem prioridade atribuída** — coluna `Prioridade` em branco para preencher. Itens já no board do GitHub estão marcados.

---

## Engenharia

| Prioridade | Ideia                                                                                                                                                                                                                                          | Contexto / fonte                                                                 | Já no board?                                        |
| ---------- | ---------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------- | -------------------------------------------------------------------------------- | --------------------------------------------------- |
|            | **Instalação em Claude corporativo gerenciado**: guia para admins, release/zip do plugin, revisar allowlist de e-mail no OAuth                                                                                                                 | Bloqueou 100% do teste Hubbi (03/07); ICP tende a ter conta corporativa          | Não                                                 |
|            | **Bug de identidade/cofundador**: output com dados da empresa renderiza antes do bloqueio                                                                                                                                                      | Risco de vazamento de dados; teste interno 03/07 (Natan)                         | Não                                                 |
|            | **Latência do diagnóstico (~3 min)**: modelo por função (Sonnet p/ queries, forte só no rerank) + curadoria estática de frameworks                                                                                                             | Motivo nº 1 de abandono assíncrono (Avenia)                                      | Não                                                 |
|            | **Persistência de estado**: gravar diagnóstico, buscas e conexões submetidas (4 entidades) em banco externo (Mongo vs BQ em aberto; BQ descartado como transacional)                                                                           | GitHub read-only em produção; sem isso o produto não captura intenção            | Parcial (#11 "definição da camada de persistência") |
|            | **Menu interativo renderiza inconsistente** (ora botões, ora texto livre)                                                                                                                                                                      | Teste interno 03/07 (Paula vs Natan)                                             | Não                                                 |
|            | **Formato de conexão pedido antes do match** (spec 0.2.5 diz depois dos 3 nomes)                                                                                                                                                               | Slack 03/07                                                                      | Não                                                 |
|            | **Cap de caracteres corta retorno das tools**                                                                                                                                                                                                  | Call Consolidação 30/06                                                          | Não                                                 |
|            | **Guardrails de dados**: campo `functional_skills_description` (info não pública), mentores super high profile no Search, concorrentes retornando como recomendação                                                                            | Slack 03/07 + call 30/06; rede (Galoppini 2025): proteger a rede e eliminar viés | Não                                                 |
|            | **Reduzir escopos do consentimento OAuth**: tela do Keycloak pede telefone, endereço, grupos e roles — desnecessários e minam confiança do founder (bastam e-mail/perfil + mcp + offline access). Configuração no client `endeavor-mcp-plugin` | Encontrado no teste local do Aruã, 04/07                                         | Não                                                 |
|            | **Tema da tela de login/consentimento**: Keycloak genérico "MCP" em inglês → marca Endeavor, português, frase explicando a autorização                                                                                                         | Encontrado no teste local do Aruã, 04/07                                         | Não                                                 |
|            | **Observabilidade do reasoning server-side**: ver qual modelo/query rodou e resultado intermediário                                                                                                                                            | Pichu sem visibilidade hoje (calls 30/06 e 01/07)                                | Não                                                 |
|            | **Acúmulo de client IDs do workaround DCR** (manutenibilidade; some quando Anthropic corrigir o bug)                                                                                                                                           | Call 30/06 (Brunão)                                                              | Não                                                 |
|            | Dashboards PostHog + eventos de jornada                                                                                                                                                                                                        | Em andamento (Kevin)                                                             | Sim (#10, #13, scaleup-ai #11)                      |
|            | Instrumentação Mastra AI                                                                                                                                                                                                                       | Em andamento (Brunão)                                                            | Sim (#15)                                           |
|            | Impedir founder de iniciar fluxo com empresa alheia                                                                                                                                                                                            | Em andamento (Brunão)                                                            | Sim (#16)                                           |
|            | Design pattern do projeto                                                                                                                                                                                                                      | Kevin + Diego + Brunão                                                           | Sim (#12)                                           |
|            | Publicação no Claude Marketplace oficial                                                                                                                                                                                                       | ⚠ Possivelmente morto: Brunão apurou que não dá para ser parceiro Anthropic hoje | Sim (#6)                                            |
|            | API de eventos para disparos futuros (criar meeting, e-mail ao mentor, agente de agendamento WhatsApp)                                                                                                                                         | Pós-MVP, mas arquitetura deve prever (call 30/06)                                | Não                                                 |

## Produto — experiência do MVP

| Prioridade | Ideia | Contexto / fonte |
|---|---|---|
| | **Pré-diagnóstico enviado antes da call/uso** (testar A/B com parte dos testers) | Aprendizado Avenia: output quase não usou respostas do founder; mandar antes gera efeito "como sabem tudo isso?" |
| | **Encurtar o fluxo**: IA infere e confirma em vez de perguntar tudo | Natan/Paula 03/07: founder não tolera back-and-forth; Alessio (2025): não dependa de bom prompt do founder |
| | **Clareza do output**: explicações inline (GCEP, escalas, hunting vs farming) + benchmark com pares da rede | Pedido direto do Leandro (Avenia); benchmark é diferencial exclusivo Endeavor |
| | **Pitch inicial no menu** ("o que você ganha ao final") | Encaminhamento 03/07 |
| | **Voice system menos robótico, mais vendedor** | Encaminhamento 03/07 |
| | **Mecânica do "seguir com intros"**: notificar growth partner, criar Connect/meeting — fluxo operacional da mediação humana | Decisão de mediação humana tomada (03/07); sem fluxo definido o loop de valor não fecha |
| | **Resposta padrão de privacidade/dados** para founders | Pergunta do Gustavo/Konasense; Alessio (2025): founder precisa sentir controle dos dados |
| | **Nomes de tools/skills mais intuitivos** para o usuário | Natan 03/07: "o resto não me diz nada" |

## Produto — aprendizado e retenção (pós-beta)

| Prioridade | Ideia | Contexto / fonte |
|---|---|---|
| | **Feedback embutido na ferramenta**: thumbs up/down por recomendação + sinais implícitos (clique, perfil visto, meeting realizado); separar métricas de corretude vs qualidade | SuperLinked (2025); resolve "beta tester ignora pergunta final" (call 01/07) |
| | **Skill "acessar meus dados"**: founder vê/corrige o próprio perfil (human-in-the-loop contra alucinação + canal de captura de updates) | Priorizada na call 29/06; autenticação por e-mail já suporta |
| | **Curadoria de playbooks/frameworks "selo Endeavor"** (estilo YC / Insight Scale Up Academy), de mentorias anonimizadas | Call 29/06 + Alessio (2025); também reduz latência do diagnóstico |
| | **Pré-mentoria automática**: briefing para founder e mentor antes de cada conexão | Gabriel Menezes (2025): low-hanging fruit; conecta MVP ao fluxo real de mentorias |
| | **Desenviesar o assessment**: incorporar padrões dos top mentores da rede via transcrições (hoje modelo = premissas Bazzi/Escala) | Em andamento (Bazzi); bloqueio: custo de tokens (675 transcrições estouram contexto) |
| | **Rotatividade e anti-viés no match**: visibilidade para mentores novos, perfis atualizados continuamente | Galoppini (2025) |
| | **Coleta por gatilhos/milestones** (captação, internacionalização) em vez de ciclos fixos | Alessio (2025) |
| | Automação de intros com supervisão humana (reaproveitar agentes WhatsApp do Sprint 1: scheduling, briefing, feedback) | Compromisso do Pre-read do Comitê (até o lançamento) |

## Produto — visão MLP e além (EEE outubro →)

| Prioridade | Ideia | Contexto / fonte |
|---|---|---|
| | **Mentoria async multi-mentor**: founder manda pergunta para conjunto de mentores responderem em uma semana | Pre-read Comitê; Aruã usou no pitch para a Hubbi |
| | **Mentoria "empacotada por AI"**: o que o mentor X diria, baseado nas mentorias passadas dele | Pre-read Comitê; idêntico ao caso de uso do Roveda (2025): "o que os top 5 mentores de branding diriam?" |
| | **Assessment v2**: árvores estatísticas/grafo direcionando desafio por histórico da base | Pre-read Comitê |
| | **Memória organizacional do founder**: relatório anual de desafios + insights de mentorias + desfechos (founder manda áudio com desfecho) | Roveda (2025); retenção + dado proprietário + onboarding de novos executivos do founder |
| | **Proatividade tailor-made**: advice periódico sem o founder pedir (e-mail com sugestões acionáveis cruzando base da rede + contexto vivo) | O que "brilharia os olhos" do Leandro (Avenia, 03/07) |
| | **Expansão além de GTM** (próximo tema por demanda da base) | Menu já preparado; Hubbi perguntou |
| | **Empacotamento por público**: EE ativo, alumni, C-levels ("extra seats"), long tail / pipeline de seleção — produto entry-level pré-qualifica o funil do Scale-Up | Gabriel Menezes + Roveda (2025); conecta com matriz de seleção (Camila) |
| | **Busca na rede cobrindo empresas** (hoje só mentores) | Call 30/06 |
| | **Caso de uso "análogos de outras indústrias"**: descrever teste de modelo de negócio e buscar quem já passou por situação análoga | Pedido verbatim do Kenny (Genial Care, WhatsApp jul/2026) |

## Processo / gestão (não é feature)

| Prioridade | Ideia | Contexto / fonte |
|---|---|---|
| | Criar view/board de produto (hoje só engenharia tem board) | Gap identificado 04/07 |
| | Atribuir prioridade aos itens do board (campo existe, 100% vazio) | Gap identificado 04/07 |
| | Rotina de captura pós-call: notas de reunião → issues propostas | Cada call gera 5–10 compromissos que evaporam |
| | Dicionário de dados por skill (regra permanente) | Call 29/06 |
| | Definição padronizada de escrita nas bases (várias skills escrevem nas mesmas tabelas) | Call 29/06 |

---

*Princípios que a rede validou (2025) e seguem valendo: não queimar cartucho com versão imatura (Lopes); entrega semanal, squad protegida (Fluency); humano no loop até confiar (Taqtile); cada feature precisa ser drasticamente melhor que o founder perguntar ao Claude puro — a resposta é sempre o dado exclusivo (Galoppini).*
