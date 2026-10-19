# Padrões de lista

Dá para comparar uma lista ou um array com uma sequência escrita entre colchetes.

## Antes

```csharp
int[] numeros = { 1, 2, 3 };

if (numeros.Length == 3 && numeros[0] == 1 && numeros[2] == 3)
{
    Console.WriteLine(numeros[1]);
}
```

## Depois

```csharp
int[] numeros = { 1, 2, 3 };

if (numeros is [1, _, 3])
{
    Console.WriteLine("começa em 1 e termina em 3");
}
```

## O que observar

Cada posição do padrão é um elemento. `_` aceita qualquer valor naquela posição. `..` representa o meio, de qualquer tamanho: `[1, .., 3]` exige que comece em 1 e termine em 3. O padrão também funciona em `switch`.
