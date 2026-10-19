# using static

`using static` importa os membros estáticos de uma classe. Os métodos são chamados sem repetir o nome da classe.

## Antes

```csharp
decimal valor = Math.Round(10.456m, 2);
```

## Depois

```csharp
using static System.Math;

decimal valor = Round(10.456m, 2);
```

## O que observar

O `using static` fica no topo do arquivo, junto dos outros `using`. Entram métodos e constantes estáticos. Também funciona com `enum`: `using static StatusPedido;` deixa escrever `Pago` em vez de `StatusPedido.Pago`. Se dois tipos importados tiverem o mesmo método, a chamada precisa do nome do tipo para o compilador escolher.
