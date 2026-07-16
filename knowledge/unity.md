# Diretrizes de Unity

Estas regras definem o padrão específico para scripts Unity.

Caso alguma regra entre em conflito com o comportamento da Unity, siga a Unity e registre a exceção na documentação do repositório.

---

## Namespaces

Os namespaces devem refletir a estrutura de diretórios localizada abaixo de `Source`.

Ignore os diretórios:

- Scripts
- Editor

---

## Serialização

Sempre prefira propriedades autoimplementadas utilizando serialização do campo de apoio.

Exemplo:

```csharp
[field: SerializeField]
public float MovementSpeed { get; private set; } = 5.0f;
```

Utilize campos somente quando estritamente necessário.

---

## Atributos

Todos os atributos devem permanecer na mesma linha da declaração.

Exemplo:

```csharp
[field: SerializeField] [field: Range(0, 100)]
public int Health { get; private set; } = 100;
```

Exceções:

`Header` e `Space` devem ficar em uma linha própria.

Exemplo:

```csharp
[field: Header("Movement")]
[field: Space]
[field: SerializeField]
public float Speed { get; private set; }
```

Sempre utilize o alvo `field:` quando aplicável.

---

## Organização do Inspector

Agrupe propriedades relacionadas por contexto.

Exemplos:

- Movement
- Combat
- Health
- Audio
- Visuals
- Debug

Separe grupos utilizando:

```csharp
[field: Space]
```

---

## Inicialização

Nunca instancie objetos derivados de `UnityEngine.Object`:

- na declaração
- no construtor

Exemplos:

- GameObject
- Component
- MonoBehaviour
- ScriptableObject
- Material
- Texture
- AudioClip

Esses objetos devem ser:

- atribuídos pelo Inspector;
- obtidos em tempo de execução;
- carregados através da API da Unity.

---

## Métodos da Unity

Todos os métodos do ciclo de vida da Unity devem permanecer dentro da região:

```csharp
#region Unity

Awake
OnEnable
Start
Update
FixedUpdate
LateUpdate
OnDisable
OnDestroy
OnCollision...
OnTrigger...

#endregion
```

Nunca misture métodos da Unity com a lógica de negócio.

---

## Código

Prefira componentes pequenos e com responsabilidade única.

Evite acoplamento entre componentes.

Sempre utilize a API da Unity apropriada ao invés de reimplementar funcionalidades existentes.

---

## Exceções

Se alguma regra deste documento entrar em conflito com limitações da Unity ou do C#, siga o comportamento correto da plataforma.

Documente a exceção na documentação do projeto.

Nunca utilize comentários no código para justificar exceções.

---

## Otimizações

Sempre utilizar `TryGetComponent` no lugar de `GetComponent` quando possível.