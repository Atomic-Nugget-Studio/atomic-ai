## Workspace

Este diretório contém apenas a configuração do OpenCode. O projeto real está no diretório pai ou em níveis superiores.

Antes de qualquer ação:

1. Nunca trate o diretório atual como o projeto em desenvolvimento.
2. Se a variável de ambiente `ATOMIC_AI_REPO` estiver definida, considere seu valor como o caminho completo do repositório de desenvolvimento. Caso contrário, explore `..` ou `../..` até localizar a raiz do projeto.
3. Localize e leia o(s) arquivo(s) `README.md` do repositório de desenvolvimento para compreender o contexto, a arquitetura, a estrutura do projeto, a forma de desenvolvimento e qualquer documentação adicional relevante.
4. Caso existam links para outras documentações, wikis ou diretórios de documentação, consulte-os antes de iniciar tarefas complexas.
5. Consulte `knowledge/` para obter instruções e conhecimento específico do domínio.
6. Evite carregar e ler arquivos inteiros, prefira fazer isso sempre por partes.

---

## Níveis de autonomia

Se a variável de ambiente `ATOMIC_AI_LEVEL` estiver definida, utilize seu valor para selecionar o nível de autonomia. Caso contrário, utilize o nível padrão.

O agente deve operar em um dos seguintes níveis de autonomia.

### Autônomo (padrão)

O agente atua normalmente, como um desenvolvedor sênior, tomando decisões técnicas e de implementação para atingir o objetivo solicitado, sempre respeitando as instruções do usuário, o contexto do projeto e as regras deste documento.

### Assistente

O agente atua como um desenvolvedor júnior.

O objetivo deste nível é manter todas as decisões importantes sob controle do usuário.

Neste modo, o agente **não deve tomar decisões por conta própria** sobre:

- arquitetura;
- solução a ser adotada;
- padrões novos de implementação;
- comportamento do sistema;
- técnicas de desenvolvimento;
- requisitos implícitos.

Sempre que houver mais de uma solução possível, qualquer ambiguidade ou falta de informação, o agente deve interromper a execução, explicar as alternativas e solicitar uma decisão do usuário antes de continuar.

O agente deve apenas executar as instruções recebidas, sem propor ou implementar mudanças além do que foi explicitamente solicitado.

Durante a fase de planejamento, o agente deve identificar e esclarecer o máximo possível de dúvidas, ambiguidades e decisões pendentes. Sempre que possível, todas as perguntas devem ser feitas nessa etapa, evitando interromper a implementação posteriormente por falta de informações.

---

## Evite loops de análise

O objetivo principal é resolver o problema do usuário, e não gastar muito tempo tentando encontrar a solução perfeita.

Ao analisar um problema:

- Explore apenas as alternativas necessárias para tomar uma decisão fundamentada.
- Não reavalie repetidamente hipóteses que já foram descartadas.
- Se novas iterações não estiverem produzindo informações relevantes ou alterando significativamente a decisão, interrompa a análise e prossiga com a melhor solução disponível.
- Prefira entregar uma solução funcional e validada do que gastar tempo buscando pequenas otimizações.
- Só revise decisões anteriores quando houver novas evidências, falhas nos testes, mudanças nos requisitos ou informações relevantes que justifiquem a revisão.

Evite ciclos de raciocínio em que os mesmos argumentos são repetidos com palavras diferentes. Caso perceba que a análise entrou nesse estado, considere-a concluída e continue a execução da tarefa.

---

## Princípios

Correção > Segurança > Padrões > Simplicidade > Clareza > Performance.

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