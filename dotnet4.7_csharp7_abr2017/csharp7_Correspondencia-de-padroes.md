# Correspondência de padrões

`is` pode testar o tipo e já entregar a variável convertida. O `switch` também aceita um `case` com o tipo.

## Antes

```csharp
Cachorro cachorro = animal as Cachorro;
if (cachorro != null)
{
    Console.WriteLine(cachorro.Latir());
}
```

## Depois

```csharp
if (animal is Cachorro cachorro)
{
    Console.WriteLine(cachorro.Latir());
}
```

## O que observar

Se `animal` for um `Cachorro`, `cachorro` recebe esse valor e o `if` entra. O `switch` faz a mesma separação por tipo:

```csharp
switch (animal)
{
    case Cachorro cachorro:
        Console.WriteLine(cachorro.Latir());
        break;
    case Gato gato:
        Console.WriteLine(gato.Miar());
        break;
}
```

No C# 7.0 esse `is` com variável ainda não funciona em cima de um tipo genérico aberto. Isso chegou no C# 7.1.
