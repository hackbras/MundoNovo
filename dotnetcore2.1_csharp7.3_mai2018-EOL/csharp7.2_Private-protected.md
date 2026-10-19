# private protected

`private protected` abre o membro para a classe filha que está no mesmo projeto. Uma filha em outro projeto não enxerga.

## Antes

```csharp
public class Pedido
{
    protected decimal Total;
}
```

`protected` deixa qualquer classe filha ler `Total`, inclusive um projeto que só referencia esta biblioteca.

## Depois

```csharp
public class Pedido
{
    private protected decimal Total;
}

public class PedidoComTaxa : Pedido
{
    public decimal ValorFinal() => Total * 1.1m;
}
```

## O que observar

`PedidoComTaxa` lê `Total` porque herda de `Pedido` e está no mesmo projeto. A mesma classe filha, compilada em outro projeto, não compila ao usar `Total`. `protected` libera a filha em qualquer projeto. `private` esconde até da filha. `protected internal` é outro modificador: libera a filha ou qualquer classe do mesmo projeto.
