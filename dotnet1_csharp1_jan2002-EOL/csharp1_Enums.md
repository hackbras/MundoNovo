# Enums

`enum` dá nome a um grupo pequeno de valores fixos, no lugar de números soltos.

## Antes

```csharp
int status = 1; // 0 novo, 1 pago, 2 enviado
```

Quem lê `1` precisa adivinhar o que ele significa.

## Depois

```csharp
enum StatusPedido
{
    Novo,
    Pago,
    Enviado
}

StatusPedido status = StatusPedido.Pago;
```

## O que observar

O primeiro nome vale `0`, o segundo vale `1`, e assim por diante. Dá para escolher o número: `Pago = 1`. Compare com `status == StatusPedido.Pago`. O `enum` continua sendo um número por baixo, com um nome em volta.
