# Endeavor — Plugin para Claude

Plugin de distribuição para o **Claude do founder**. O servidor MCP (no projeto
`scaleup-ai`) expõe as tools e roda o agente; este plugin é o que o founder
instala no Claude para **consumir** essas tools.

Este repositório é, ao mesmo tempo, um **marketplace de plugins do Claude Code**
(`.claude-plugin/marketplace.json`) e contém o plugin `endeavor` em
[`./endeavor`](./endeavor).

## Instalação (Claude Code)

No Claude Code, adicione este marketplace e instale o plugin:

```
/plugin marketplace add Endeavor-Brasil/endeavor-plugin
/plugin install endeavor@endeavor
```

> `/plugin install <plugin>@<marketplace>` — aqui tanto o plugin quanto o
> marketplace se chamam `endeavor`.

Depois de instalado, o Claude do founder passa a ter:

- o conector MCP **endeavor** (HTTP) apontando para o servidor;
- as skills `diagnostico` e `matchmaking`.

## Conteúdo

```
endeavor-plugin/
├── .claude-plugin/
│   └── marketplace.json          # manifesto do marketplace (lista o plugin endeavor)
└── endeavor/                      # o plugin
    ├── .claude-plugin/plugin.json # manifesto do plugin (nome, versão, autor)
    ├── .mcp.json                  # conector MCP → URL do servidor
    └── skills/
        ├── endeavor/SKILL.md      # menu concierge /endeavor: roteia p/ a capacidade certa
        ├── diagnostico/SKILL.md   # roteiro: empresa → diagnostico() → polling → entrega
        └── matchmaking/SKILL.md   # roteiro: empresa → matchmaking() → polling → entrega
```

As skills são **client-side**: não acessam dados, apenas orientam o Claude do
founder. A skill-menu `endeavor` (`/endeavor`) é a porta de entrada: mostra o
cardápio de capacidades e roteia para `diagnostico` / `matchmaking`, que chamam
as tools e fazem polling com `consultar_analise` até o resultado curado ficar
pronto.

## Conector (`endeavor/.mcp.json`)

Aponta para o servidor MCP rodando em modo `streamable-http`:

```json
{ "mcpServers": { "endeavor": {
  "type": "http",
  "url": "https://mcp-qa.endeavor.org.br/mcp",
  "oauth": { "clientId": "endeavor-mcp-plugin" }
} } }
```

### Autenticação (OAuth com Keycloak)

Quando o servidor roda com `MCP_AUTH_ENABLED`, o founder vê a tela de login do
Keycloak ao conectar. O bloco `oauth` declara um **client público + PKCE**
(`endeavor-mcp-plugin`, sem secret — por isso é seguro distribuir).

Pré-requisitos no Keycloak (realm `mcp`):

- Client **público** `endeavor-mcp-plugin` (Client authentication **Off**, Standard
  flow On, PKCE **S256**).
- Redirect URI do callback do cliente MCP.
- Client scope `mcp` (com o Audience Mapper → `aud` = URL pública do servidor)
  atribuído como **Default** a este client, senão o `aud` do token não bate.
