## Inicialização obrigatória

**Antes de qualquer resposta, tarefa ou análise, execute integralmente todas as etapas desta seção na ordem apresentada.**

**Atenção: para ler o valor de uma variável de ambiente utilize sempre "echo $env:EXEMPLO", sem nenhum outro comando, pois pode não haver permissão para ele.**

### Projeto

O opencode inicia na raiz do repositório de desenvolvimento. O diretório de trabalho atual é o projeto.

1. Localize e leia o(s) arquivo(s) `README.md` para compreender o contexto, a arquitetura, a estrutura do projeto, a forma de desenvolvimento e qualquer documentação adicional relevante.
2. Caso existam links para outras documentações, wikis ou diretórios de documentação, consulte-os antes de iniciar tarefas complexas.
3. Consulte `{OPENCODE_CONFIG_DIR}/knowledge/` para obter instruções e conhecimento específico do domínio, onde `OPENCODE_CONFIG_DIR` é o diretório pai do caminho em `OPENCODE_CONFIG`.
4. Evite carregar e ler arquivos inteiros, prefira fazer isso sempre por partes.

**Confirmação:** Ao final, informe brevemente ao usuário:
- Se o README foi lido
- Se existe documentação adicional consultada

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