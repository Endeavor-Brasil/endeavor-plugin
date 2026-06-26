---
name: matchmaking
description: Recomenda os mentores que dão match para uma empresa da rede Endeavor. Use quando o usuário pedir mentores, match, conexões ou indicação de mentoria para uma empresa.
---

# Matchmaking Endeavor

Roteiro para recomendar mentores que dão match para uma empresa da rede Endeavor.

1. **Empresa**: se o usuário não informou o nome da empresa, pergunte antes de prosseguir.
   Capture também qualquer contexto que ele trouxer (dúvida, desafio específico).
2. **Disparar**: chame a tool `matchmaking(empresa, contexto)` do conector Endeavor.
   Ela é assíncrona e devolve um `job_id` (a análise leva ~5-9 min, roda no servidor com dados reais).
3. **Polling**: chame `consultar_analise(job_id)`. Enquanto a resposta começar com "⏳",
   aguarde ~20-30s e chame de novo, repetindo até o resultado ficar pronto.
4. **Entrega**: apresente somente o resultado final curado que o servidor devolver
   (perfil-alvo → top mentores → top 3). Não invente dados nem exponha SQL ou detalhes internos.

Exemplo de pedido: "/matchmaking TechCorp — buscamos mentor com experiência em fundraising série A".
