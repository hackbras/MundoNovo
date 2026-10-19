# Construtor sem parâmetros em struct

Um `struct` pode ter um construtor sem parâmetros e um valor inicial nos campos.

## Antes

```csharp
public struct Contador
{
    public int Valor; // começa em 0; não havia construtor vazio próprio
}

Contador contador = new Contador();
```

## Depois

```csharp
public struct Contador
{
    public int Valor { get; set; } = 1;

    public Contador()
    {
        Valor = 10;
    }
}

Contador criado = new Contador();   // Valor é 10
Contador zerado = default;          // Valor é 0
```

## O que observar

`new Contador()` chama o construtor e aplica o `= 1` antes do corpo. `default` e um array de `Contador` zeram a memória e não chamam esse construtor. Por isso `new` e `default` podem produzir valores diferentes.
