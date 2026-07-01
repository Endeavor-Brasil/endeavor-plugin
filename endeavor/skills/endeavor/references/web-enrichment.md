# Enriquecimento via web

Quando a base não tem ou não confirma um campo, preencher com web_search, com a melhor acurácia
possível. Descartar resultado claramente de homônimo ou empresa trocada.

Campos a preencher/validar:

- **Modelo de mercado:** B2B | B2C | B2G
- **Perfil de cliente:** Enterprise | Mid | SMB
- **Ticket:** High | Mid | Small
- **Revenue model:** RR (recorrente) | OTR (one-time) | SF (success fee)
- **Porte aproximado:** uma noção do tamanho/estágio da empresa pela faixa de receita ou nº de
  funcionários, quando for público.
- **CEO:** mais técnico ou mais de negócios

Se uma fonte de receita for ambígua (USD vs BRL, valuation vs receita), assumir o cenário mais
plausível pelo porte/estágio e seguir. Não travar a coleta por causa de um campo secundário.
