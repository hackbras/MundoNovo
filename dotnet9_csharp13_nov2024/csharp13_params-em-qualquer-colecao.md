# params em qualquer coleção

`params` deixou de ser só array. O parâmetro pode ser `List`, `Span` ou outra coleção.

## Antes

```csharp
void Registrar(params string[] nomes)
{
    Console.WriteLine(nomes.Length);
}

Registrar("Ana", "Bia");
```

Os argumentos sempre viravam um `string[]`.

## Depois

```csharp
void Registrar(params List<string> nomes)
{
    Console.WriteLine(nomes.Count);
}

Registrar("Ana", "Bia");
```

## O que observar

A chamada continua igual: os textos soltos entram na coleção. O corpo do método recebe uma `List<string>` e pode usar `Count` e os métodos de lista. `params ReadOnlySpan<string>` evita criar uma lista quando o método só lê os valores.
