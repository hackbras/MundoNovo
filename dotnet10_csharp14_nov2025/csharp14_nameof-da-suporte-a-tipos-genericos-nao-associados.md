# nameof de tipos genéricos não associados

`nameof` aceita um tipo genérico aberto, com `<>` vazio, e devolve o nome do tipo.

## Antes

```csharp
string nome = nameof(List<int>); // "List"
```

Era preciso inventar um argumento, como `int`, só para o `nameof` aceitar o tipo.

## Depois

```csharp
string nome = nameof(List<>); // "List"
```

## O que observar

`List<>` não é uma lista de um tipo concreto. É o tipo genérico em aberto, e `nameof` lê só o nome `List`. Serve para log e mensagem de erro em que o argumento de tipo não importa. Com um argumento, `nameof(List<int>)` continua devolvendo `"List"`.
