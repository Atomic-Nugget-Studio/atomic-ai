# AGENTS.md

Este documento define **como trabalhar** neste repositório.

Não contém conhecimento específico de tecnologias. Consulte os documentos em `knowledge/` e `standards/` quando necessário.

---

# Objetivo

Entregue software correto, simples e fácil de manter.

Prioridades:

1. Correção
2. Segurança
3. Simplicidade
4. Clareza
5. Performance

Nunca sacrifique um item superior para melhorar um inferior.

---

# Processo

Antes de modificar qualquer arquivo:

1. Compreenda completamente a solicitação.
2. Leia apenas o contexto necessário.
3. Identifique restrições.
4. Procure soluções existentes.
5. Só então implemente.

Não comece escrevendo código.

---

# Hipóteses

Nunca assuma requisitos silenciosamente.

Se houver incertezas relevantes:

* explique as hipóteses;
* apresente alternativas quando necessário;
* peça esclarecimentos somente quando a resposta alterar significativamente a implementação.

---

# Escopo

Implemente somente o que foi solicitado.

Evite:

* refatorações paralelas;
* mudanças cosméticas;
* renomeações sem benefício;
* alterações em áreas não relacionadas.

Se identificar outros problemas, registre-os ao final em vez de corrigi-los automaticamente.

---

# Leitura do projeto

Antes de criar algo novo:

* procure implementações semelhantes;
* reutilize componentes existentes;
* respeite padrões já adotados.

Prefira consistência ao invés de introduzir uma arquitetura diferente.

---

# Mudanças

Prefira:

* mudanças pequenas;
* commits conceituais;
* baixo risco;
* compatibilidade.

Evite alterar APIs públicas sem necessidade.

---

# Código

Todo código deve ser:

* previsível;
* consistente;
* fácil de ler;
* fácil de modificar.

Evite engenharia excessiva.

Quando duas soluções resolverem o problema, escolha a mais simples.

---

# Ferramentas

Sempre utilize as ferramentas mais apropriadas disponíveis.

Não invente comandos.

Quando existirem scripts oficiais do projeto, utilize-os.

---

# Validação

Sempre que possível:

* execute testes relevantes;
* execute lint quando existir;
* valide a compilação;
* confirme que a alteração resolveu o problema.

Nunca afirme que algo funciona sem algum tipo de verificação.

---

# Documentação

Atualize documentação quando uma mudança alterar:

* comportamento;
* arquitetura;
* comandos;
* fluxo de desenvolvimento.

---

# Conhecimento especializado

Quando a tarefa envolver um domínio específico, consulte os documentos relevantes em `knowledge/`.

Exemplos:

* Unity
* Blender
* Docker
* Git
* C#
* Infraestrutura

Leia somente os documentos necessários para a tarefa atual.

---

# Standards

As convenções da Atomic estão em `standards/`.

Sempre siga esses documentos antes de utilizar conhecimento genérico.

---

# Agentes

Cada agente possui responsabilidades próprias.

* Build → Implementa mudanças.
* Plan → Planeja soluções.
* Review → Revisa implementações.
* Ask → Responde perguntas.

Nunca execute responsabilidades pertencentes a outro agente.

---

# Comunicação

Explique decisões importantes.

Prefira explicar:

* por que;
* impacto;
* limitações.

Evite descrever cada pequena alteração.

---

# Conclusão

Antes de finalizar qualquer tarefa, confirme mentalmente:

* O problema foi realmente resolvido?
* A mudança é a menor possível?
* O código segue o padrão existente?
* Há risco evidente de regressão?
* Existe documentação que precisa ser atualizada?

Se alguma resposta for negativa, resolva antes de concluir.