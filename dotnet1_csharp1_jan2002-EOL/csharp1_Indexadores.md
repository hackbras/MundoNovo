# Indexadores

O indexador deixa um objeto ser usado com colchetes, como um array: `pedido[0]`.

## Antes

```csharp
public class Pedido
{
    private string[] _itens = new string[2];

    public string Pegar(int indice)
    {
        return _itens[indice];
    }
}

string primeiro = pedido.Pegar(0);
```

## Depois

```csharp
public class Pedido
{
    private string[] _itens = new string[2];

    public string this[int indice]
    {
        get { return _itens[indice]; }
        set { _itens[indice] = value; }
    }
}

string primeiro = pedido[0];
pedido[1] = "Cafe";
```

## O que observar

`this[...]` é a propriedade da posição. Pode ter `get`, `set`, ou os dois. O índice não precisa ser `int`: um pedido pode buscar por código com `pedido["A1"]`, se o indexador receber `string`.
