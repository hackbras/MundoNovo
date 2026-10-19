# ref struct

`ref struct` é um `struct` que só vive na pilha. Ele não pode ser guardado num campo de classe nem ir para o heap.

## Antes

```csharp
public struct Ticket
{
    public int Numero;
}

public class Caixa
{
    public Ticket Atual;
}
```

Um `struct` comum pode ser campo de classe, item de array e variável de um método `async`.

## Depois

```csharp
public ref struct Ticket
{
    public int Numero;
}

Ticket ticket = new Ticket();
ticket.Numero = 10;
```

## O que observar

`Ticket` como campo de `Caixa` não compila. Também não pode ser elemento de um array, não pode aparecer num método `async` e não pode ser convertido para `object`. A regra existe por causa de tipos como `Span<char>`, que apontam para memória da pilha: se fossem para o heap, apontariam para um lugar que já acabou.
