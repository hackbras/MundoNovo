# Membros com corpo de expressão

Um método ou uma propriedade de uma linha só pode ser escrito com `=>`, sem chaves e sem `return`.

## Antes

```csharp
public class Produto
{
    public string Nome { get; set; }

    public string Descrever()
    {
        return "Produto: " + Nome;
    }
}
```

## Depois

```csharp
public class Produto
{
    public string Nome { get; set; }

    public string Descrever() => "Produto: " + Nome;
    public string Rotulo => Nome;
}
```

## O que observar

`Descrever()` devolve o texto. `Rotulo` é uma propriedade só de leitura, calculada cada vez que alguém lê. Os dois são uma expressão só. No C# 7 o mesmo `=>` passou a servir em construtor, `get` e `set`.
