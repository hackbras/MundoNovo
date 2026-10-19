# Usings globais

Um `using` pode servir para todos os arquivos do projeto, em vez de ser repetido em cada um.

## Antes

```csharp
// Produto.cs
using System.Collections.Generic;

public class Produto
{
    public List<string> Tags { get; } = new();
}

// Pedido.cs
using System.Collections.Generic;

public class Pedido
{
    public List<Produto> Itens { get; } = new();
}
```

## Depois

```csharp
// GlobalUsings.cs
global using System.Collections.Generic;

// Produto.cs e Pedido.cs não repetem o using
public class Produto
{
    public List<string> Tags { get; } = new();
}
```

## O que observar

`global using` vale para o projeto inteiro. O lugar habitual é um arquivo pequeno, só com esses usings. O compilador também pode gerar usings globais sozinho quando o projeto tem `<ImplicitUsings>enable</ImplicitUsings>`.
