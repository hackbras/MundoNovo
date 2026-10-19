# Funções locais

Uma função local é um método declarado dentro de outro. Ela só existe ali e enxerga as variáveis do método de fora.

## Antes

```csharp
string Rotulo(Pedido pedido)
{
    return pedido.Id + " - " + pedido.Total;
}

void Imprimir(Pedido pedido)
{
    Console.WriteLine(Rotulo(pedido));
}
```

`Rotulo` fica visível para a classe inteira.

## Depois

```csharp
void Imprimir(Pedido pedido)
{
    string Rotulo() => pedido.Id + " - " + pedido.Total;

    Console.WriteLine(Rotulo());
}
```

## O que observar

`Rotulo` usa `pedido` sem receber parâmetro, porque a função local está dentro de `Imprimir`. Outros métodos da classe não chamam `Rotulo`. Ela pode ficar embaixo da primeira chamada; o compilador aceita.
