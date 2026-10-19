# Literal default

`default` sozinho usa o tipo que o lugar já espera. Não precisa repetir o tipo entre parênteses.

## Antes

```csharp
int qtd = default(int);
List<string> nomes = default(List<string>);
```

## Depois

```csharp
int qtd = default;
List<string> nomes = default;
```

## O que observar

Para `int`, `default` é `0`. Para `bool`, é `false`. Para uma classe, é `null`, então `nomes` aqui ficou `null`. Dentro de um método genérico, `return default;` devolve o valor padrão de `T` sem escrever `default(T)`.
