# Radar proativo: a rotina pronta (stub v2)

Em v2 esta opção NÃO constrói uma automação sob medida. Ela explica o conceito e entrega uma rotina
pronta pro founder plugar no scheduling do Claude dele. O design profundo (agnóstico à stack do founder,
varredura de workspace) é evolução futura, fora deste escopo.

## Fluxo
1. Explique em 1 ou 2 frases: a Endeavor pode ficar de olho na sua semana e, numa rotina automática,
   sugerir conexões da rede e insights com base no que está acontecendo com você.
2. Entregue a rotina pronta (o founder copia e agenda no Claude dele):

> Radar Endeavor (quinzenal): leia minha semana (reuniões e agenda dos próximos 14 dias), identifique o
> desafio dominante e, usando as tools do MCP da Endeavor, sugira no máximo uma conexão da rede mais um
> insight de mentoria pra esse desafio. Devolva curto.

3. Diga que ele pode ajustar o intervalo e o canal de entrega, e que dá pra evoluir isso depois.

## Guardrails
- Não prometa a automação autônoma completa (é evolução futura).
- A rotina usa as tools do MCP da Endeavor que já existem.
- Sem travessão.
