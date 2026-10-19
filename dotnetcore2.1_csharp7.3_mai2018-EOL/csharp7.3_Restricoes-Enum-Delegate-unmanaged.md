# Restrições Enum, Delegate e unmanaged

`where` passou a aceitar `Enum`, `Delegate` e `unmanaged`. O método genérico só compila com um tipo que caiba nessa regra.

## Antes

```csharp
public static string Nome<T>(T valor) where T : struct
{
    return valor.ToString();
}
```

`where T : struct` aceita `int`, `bool` e qualquer `struct`, não só `enum`.

## Depois

```csharp
public static string Nome<T>(T valor) where T : Enum
{
    return valor.ToString();
}
```

## O que observar

`Nome(StatusPedido.Pago)` compila. `Nome(10)` não compila, porque `int` não é um `enum`. `where T : Delegate` aceita um `delegate`. `where T : unmanaged` aceita tipos sem referência dentro, como `int`, `double` e um `struct` feito só desses valores. Um `struct` com uma `string` dentro fica de fora do `unmanaged`.
