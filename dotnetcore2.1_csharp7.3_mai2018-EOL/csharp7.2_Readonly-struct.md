# readonly struct

`readonly struct` promete que o valor não muda depois de criado. Os campos ficam somente leitura.

## Antes

```csharp
public struct Ponto
{
    public int X { get; set; }
    public int Y { get; set; }
}

Ponto ponto = new Ponto();
ponto.X = 5;
```

`X` e `Y` podem ser trocados em qualquer momento da vida do valor.

## Depois

```csharp
public readonly struct Ponto
{
    public int X { get; }
    public int Y { get; }

    public Ponto(int x, int y)
    {
        X = x;
        Y = y;
    }
}
```

## O que observar

`X` e `Y` recebem valor no construtor. `ponto.X = 5` não compila. Um método desse struct também não pode alterar os campos. Isso evita cópia à toa quando o `struct` é passado para um método que só lê, principalmente junto com o parâmetro `in`.
