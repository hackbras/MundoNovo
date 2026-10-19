# Structs

`struct` guarda um valor, como um ponto ou um dinheiro. Copiar um `struct` copia os dados. Copiar uma classe copia só a referência.

## Antes

```csharp
class Ponto
{
    public int X;
    public int Y;
}

Ponto a = new Ponto();
a.X = 1;
Ponto b = a;
b.X = 5; // a.X também fica 5
```

## Depois

```csharp
struct Ponto
{
    public int X;
    public int Y;
}

Ponto a = new Ponto();
a.X = 1;
Ponto b = a;
b.X = 5; // a.X continua 1
```

## O que observar

`b = a` no `struct` leva uma cópia de `X` e de `Y`. Na classe, `a` e `b` apontam para o mesmo objeto. `struct` combina com dados pequenos. Um `struct` sozinho não aceita `null`; isso chegou no C# 2, com `Ponto?`.
