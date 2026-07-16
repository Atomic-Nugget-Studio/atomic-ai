# Diretrizes de C#

Estas regras definem o padrão de código C# adotado pelo projeto.

Caso alguma regra entre em conflito com a linguagem C#, siga o comportamento da linguagem e registre a exceção na documentação do repositório. Nunca explique exceções através de comentários no código.

---

## Declarações

- Utilize sempre tipos explícitos. Nunca utilize `var`.
- Cada arquivo deve conter apenas um tipo principal.
- Tipos auxiliares (classes, structs e enums) devem ser declarados como tipos aninhados dentro do tipo principal.
- Nunca altere um membro existente de campo para propriedade (ou vice-versa), nem altere seu nome, salvo quando estritamente necessário.

---

## Nomenclatura

- Classes, structs, enums, propriedades e métodos utilizam **PascalCase**.
- Campos privados utilizam o padrão `m_Campo`.
- Nunca crie classes contendo os termos:
  - Controller
  - Manager
  - Handler

Esses nomes normalmente indicam responsabilidades excessivas.

---

## Propriedades

Sempre prefira propriedades públicas em vez de campos públicos.

Utilize campos apenas para dados privados ou quando houver necessidade técnica.

Utilize propriedades privadas apenas quando for necessário encapsular dados.

Propriedades jamais devem ter efeito colateral ou processamento pesado, para isso prefira métodos e funções.

Nunca exponha diretamente coleções mutáveis.

Em vez disso, exponha apenas interfaces somente leitura, como:

- IEnumerable<T>
- IReadOnlyCollection<T>
- IReadOnlyList<T>

---

## Fluxo de execução

Utilize sempre Early Return.

Sempre utilize chaves (`{}`), mesmo quando houver apenas uma instrução.

Não utilize blocos de uma única linha sem chaves.

Sempre utilize a biblioteca LINQ quando possível.

---

## Organização dos membros

A ordem dos membros deve ser exatamente:

1. Tipos aninhados
2. Constantes
3. Membros estáticos
4. Membros não estáticos
5. Construtores
6. Métodos estáticos
7. Métodos virtuais/abstratos
8. Overrides
9. Implementações de interfaces
10. Demais métodos

Dentro da última categoria:

- públicos
- protegidos
- privados

Não misture categorias.

---

## Comentários

Evite comentários desnecessários.

Utilize documentação XML somente em código de bibliotecas, nunca em aplicações, a menos quando pedido.

O código deve ser suficientemente claro para dispensar explicações.