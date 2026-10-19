# Variáveis out

A variável de um `out` pode nascer na chamada. O tipo fica do lado do argumento.

## Antes

```csharp
int qtd;
if (int.TryParse(texto, out qtd))
{
    Console.WriteLine(qtd);
}
```

## Depois

```csharp
if (int.TryParse(texto, out int qtd))
{
    Console.WriteLine(qtd);
}
```

## O que observar

`qtd` existe no `if` e também nas linhas seguintes do mesmo bloco. `out var qtd` deixa o compilador descobrir o tipo, que aqui é `int`. Se o `TryParse` devolver `false`, `qtd` ficou `0` e o `if` não entra.
