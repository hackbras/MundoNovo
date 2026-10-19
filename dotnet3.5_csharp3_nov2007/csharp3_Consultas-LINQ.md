# Consultas LINQ

A consulta com `from`, `where` e `select` filtra e transforma uma coleção num formato parecido com uma frase.

## Antes

```csharp
List<string> baratos = new List<string>();
foreach (Produto produto in produtos)
{
    if (produto.Preco < 10)
        baratos.Add(produto.Nome);
}
```

## Depois

```csharp
var baratos = from produto in produtos
              where produto.Preco < 10
              select produto.Nome;
```

## O que observar

Por baixo, isso vira chamadas de `Where` e `Select`. A consulta roda quando alguém percorre `baratos`, não na linha do `from`. O arquivo precisa de `using System.Linq`. A mesma consulta em métodos é `produtos.Where(produto => produto.Preco < 10).Select(produto => produto.Nome)`.
