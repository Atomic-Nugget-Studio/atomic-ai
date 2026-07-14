## Workspace

Este diretório é apenas configuração do OpenCode. O projeto real está no diretório pai ou superior.

Antes de qualquer ação, explore `..` ou `../..` até localizar a raiz do projeto. Nunca trate este diretório como o projeto em desenvolvimento.

As instruções estão em inglês / português. Consulte `knowledge/` para domínio específico.

---

## Princípios

Correção > Segurança > Simplicidade > Clareza > Performance.

Nunca sacrifique um item superior para melhorar um inferior.

Mudanças pequenas, baixo risco, compatibilidade. Preferir reutilização, evitar engenharia excessiva.

---

## Processo

Antes de modificar qualquer arquivo: entenda o pedido → leia contexto necessário → identifique restrições → procure soluções existentes → implemente.

Não comece escrevendo código. Não assuma requisitos silenciosamente — explique hipóteses e apresente alternativas.

---

## Escopo

Implemente somente o que foi solicitado. Evite refatorações paralelas, mudanças cosméticas e alterações não relacionadas.

Se identificar outros problemas, registre-os ao final em vez de corrigir automaticamente.

---

## Código

Todo código deve ser previsível, consistente, fácil de ler e fácil de modificar. Quando duas soluções resolverem o problema, escolha a mais simples.

Sempre utilize ferramentas mais apropriadas existentes. Não invente comandos.

---

## Validação

Sempre que possível, execute testes, lint, valide a compilação e confirme que a alteração resolveu o problema.

Nunca afirme que algo funciona sem algum tipo de verificação.

---

## Documentação

Atualize documentação quando comportamento, arquitetura, comandos ou fluxo de desenvolvimento mudarem.

---

## Agents

- **Build** → Implementa mudanças (primary, todas as ferramentas)
- **Plan** → Planeja soluções (primary, read-only via permissions)
- **Review** → Revisa implementações (subagent, read-only via permissions)

Nunca execute responsabilidades pertencentes a outro agente.