# Instruções de nível superior

O programa pode começar direto nos comandos. A classe `Program` e o método `Main` ficam por conta do compilador.

## Antes

```csharp
using System;

class Program
{
    static void Main()
    {
        Console.WriteLine("Olá");
    }
}
```

## Depois

```csharp
using System;

Console.WriteLine("Olá");
```

## O que observar

Só um arquivo do projeto pode ter comandos soltos nesse formato. Esse arquivo vira o ponto de entrada. Dá para declarar uma função local e uma classe no mesmo arquivo, abaixo dos comandos. Os `using` continuam no topo. A partir do .NET 6, um projeto novo de console já nasce assim.
