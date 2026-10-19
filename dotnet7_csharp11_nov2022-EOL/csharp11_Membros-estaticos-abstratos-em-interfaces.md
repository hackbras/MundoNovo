# Membros estáticos abstratos em interfaces

Uma interface pode exigir um membro `static`, por exemplo um operador ou uma propriedade, de quem a implementa.

## Antes

```csharp
public struct Metro
{
    public int Valor { get; }
    public Metro(int valor) => Valor = valor;

    public static Metro operator +(Metro a, Metro b) => new(a.Valor + b.Valor);
}
```

O `+` existia no tipo, mas um método genérico não podia prometer que `T` tivesse esse operador.

## Depois

```csharp
public interface ISomavel<T> where T : ISomavel<T>
{
    static abstract T operator +(T a, T b);
}

public struct Metro : ISomavel<Metro>
{
    public int Valor { get; }
    public Metro(int valor) => Valor = valor;

    public static Metro operator +(Metro a, Metro b) => new(a.Valor + b.Valor);
}

static T Somar<T>(T a, T b) where T : ISomavel<T> => a + b;
```

## O que observar

`static abstract` descreve um membro da classe, não de cada objeto. `Somar` funciona para qualquer `T` que implemente `ISomavel<T>`, e `a + b` compila por causa dessa promessa. É a base da matemática genérica do .NET, como somar `int` e tipos numéricos seus com o mesmo método.
