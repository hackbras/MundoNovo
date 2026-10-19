# Padrões de propriedade

O padrão de propriedade olha os membros do objeto dentro do `is` ou do `switch`. As condições ficam entre chaves.

## Antes

```csharp
if (pedido != null && pedido.Pago && pedido.Total == 0)
{
    Console.WriteLine("quitado");
}
```

## Depois

```csharp
if (pedido is { Pago: true, Total: 0 })
{
    Console.WriteLine("quitado");
}
```

## O que observar

`pedido` precisa não ser `null` e ter `Pago` verdadeiro e `Total` zero. Dá para pedir o tipo junto: `pedido is Pedido { Pago: true }`. Um tipo com `Deconstruct` também aceita o padrão de posição: `ponto is (0, 0)`. No C# 9 as chaves passam a combinar com `>`, `<` e `and`.
