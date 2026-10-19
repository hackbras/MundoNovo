# Records struct

Um `record` também pode ser `struct`: os dados ficam na pilha e a igualdade continua comparando os valores.

## Antes

```csharp
public struct Ponto
{
    public int X { get; init; }
    public int Y { get; init; }

    public Ponto(int x, int y)
    {
        X = x;
        Y = y;
    }
}
```

Dois pontos com o mesmo `X` e o mesmo `Y` podiam ser considerados diferentes, porque a igualdade padrão do `struct` escrito à mão não vinha pronta nesse formato curto.

## Depois

```csharp
public readonly record struct Ponto(int X, int Y);

Ponto a = new(1, 2);
Ponto b = new(1, 2);
bool iguais = a == b; // true
Ponto movido = a with { X = 5 };
```

## O que observar

`record struct` compara os campos, imprime os valores no `ToString` e aceita `with`. `readonly record struct` impede alterar `X` e `Y` depois de criado. Um `record class` continua sendo um objeto na memória; o `struct` é o valor em si.
