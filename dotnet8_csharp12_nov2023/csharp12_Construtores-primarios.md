# Construtores primários

Os parâmetros do construtor podem ficar na mesma linha da classe ou do struct, e o corpo usa esses nomes direto.

## Antes

```csharp
public class Produto
{
    public string Nome { get; }

    public Produto(string nome)
    {
        Nome = nome;
    }
}
```

## Depois

```csharp
public class Produto(string nome)
{
    public string Nome { get; } = nome;

    public string Descrever() => $"Produto: {nome}";
}
```

## O que observar

`nome` existe na classe inteira, nos métodos e nos inicializadores. A propriedade `Nome` é o que o restante do programa enxerga; o parâmetro `nome` fica dentro da classe. Um construtor primário convive com outro construtor, desde que esse outro chame `this(...)`.
