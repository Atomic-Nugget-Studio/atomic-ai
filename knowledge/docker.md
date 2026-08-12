# Diretrizes Docker

Regras gerais para criação e manutenção de aplicações Docker no ecossistema Atomic.

---

## Fonte única de verdade para configuração

**`appsettings.json` é a fonte única de verdade para configurações da aplicação.**

O `docker-compose.yml` não deve conter valores padrão para variáveis que já possuem default em `appsettings.json`. A única exceção são **secrets** e valores **específicos do ambiente de deploy** que não podem ser versionados.

### Por quê?

- Evita duplicação e dessincronização de valores entre arquivos
- Reduz superfície de erro: um valor alterado em um lugar e esquecido no outro
- Mantém `docker-compose.yml` focado em infraestrutura (volumes, redes, portas)
- `appsettings.json` continua funcional para `dotnet run` local sem Docker

### Regra

| Tipo de configuração | Onde define o default? | No docker-compose.yml |
|---|---|---|
| Secrets (tokens, senhas) | **Não** — nunca versionar | `${VAR}` (sem default) |
| Configurações da aplicação | `appsettings.json` | **Não incluir** como env var |
| Configurações de infraestrutura | `docker-compose.yml` | Diretamente (volumes, ports, etc.) |

### Variáveis de ambiente como override

Variáveis de ambiente ainda funcionam como override para `appsettings.json` (padrão ASP.NET Core: `Chave__Subchave`). Isso deve estar documentado no README do projeto para operadores que precisem de configuração por ambiente, mas **não deve ser o padrão** no `docker-compose.yml`.

---

## Ordem de prioridade (ASP.NET Core)

1. Argumentos de linha de comando (maior prioridade)
2. Variáveis de ambiente
3. `appsettings.{Environment}.json`
4. `appsettings.json` (menor prioridade)

---

## Volumes compartilhados

Quando uma configuração de caminho (ex: `WorkspaceBasePath`) é usada tanto pela aplicação quanto por um volume no `docker-compose.yml`:

- Hardcode o caminho no `docker-compose.yml`
- Adicione um comentário referenciando a configuração equivalente em `appsettings.json`
- **Nunca** use variáveis de ambiente no `docker-compose.yml` para valores que também existem em `appsettings.json` — isso recria o problema de duplicação

Exemplo:

```yaml
volumes:
  # Deve ser o mesmo valor de MyConfig.Path em appsettings.json.
  - /data/myapp:/data/myapp
```

---

## Secrets

- Nunca versionar secrets no repositório
- Usar `.env` (excluído do git via `.gitignore`) ou variáveis de ambiente do orchestrator
- Fornecer `.env.example` com valores placeholder descritivos
- No `docker-compose.yml`, usar `${VAR}` sem default — erro imediato se não configurado

---

## Estrutura recomendada

```
meu-app/
├── appsettings.json           # Defaults da aplicação (versionado)
├── appsettings.Development.json  # Overrides locais (versionado, opcional)
├── docker-compose.yml          # Infraestrutura Docker (versionado)
├── .env.example                # Template de secrets (versionado)
├── .env                        # Secrets reais (NÃO versionado)
└── README.md                   # Documenta como configurar
```

---

## Checklist ao criar app Docker

- [ ] Defaults de configuração em `appsettings.json`, não no `docker-compose.yml`
- [ ] Secrets via `.env` + `${VAR}` sem default no compose
- [ ] `.env.example` documenta todas as variáveis esperadas
- [ ] Volumes com caminhos hardcoded e comentário de referência
- [ ] README atualizado com instruções de configuração
- [ ] `.gitignore` exclui `.env`
