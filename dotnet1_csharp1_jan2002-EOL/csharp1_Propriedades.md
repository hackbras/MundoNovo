# Propriedades

Uma propriedade parece um campo para quem usa a classe, e por dentro pode ter código no `get` e no `set`.

## Antes

```csharp
public class Produto
{
    public string Nome;
}
```

Qualquer código podia gravar `Nome` direto, sem validação.

## Depois

```csharp
public class Produto
{
    private string _nome;

    public string Nome
    {
        get { return _nome; }
        set { _nome = value; }
    }
}
```

## O que observar

Quem usa a classe continua escrevendo `produto.Nome`. A diferença fica dentro da classe: o `set` pode recusar um texto vazio, e o campo `_nome` fica escondido. `value` é o valor que chegou na atribuição.
