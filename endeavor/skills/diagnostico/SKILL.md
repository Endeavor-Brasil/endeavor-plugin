---
name: diagnostico
description: Diagnóstico dos desafios de uma empresa da rede Endeavor. Use quando o usuário pedir diagnóstico, análise de desafios, gargalos ou prioridades de uma empresa.
---

# Diagnóstico Endeavor

Roteiro para rodar um diagnóstico de desafios de uma empresa da rede Endeavor.

1. **Empresa**: se o usuário não informou o nome da empresa, pergunte antes de prosseguir.
   Capture também qualquer contexto que ele trouxer (dúvida, desafio específico).
2. **Disparar**: chame a tool `diagnostico(empresa, contexto)` do conector Endeavor.
   Ela é assíncrona e devolve um `job_id` (a análise leva ~5-9 min, roda no servidor com dados reais).
3. **Polling**: chame `consultar_analise(job_id)`. Enquanto a resposta começar com "⏳",
   aguarde ~20-30s e chame de novo, repetindo até o resultado ficar pronto.
4. **Entrega**: apresente somente o resultado final curado que o servidor devolver.
   Não invente dados nem exponha SQL ou detalhes internos.

Exemplo de pedido: "/diagnostico AgroFuturo — queremos entender gargalos de expansão".
