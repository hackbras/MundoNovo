# Iteradores com yield

`yield return` devolve um item e pausa o método. Na próxima leitura, o método continua de onde parou.

## Antes

```csharp
List<int> ParesAte(int limite)
{
    List<int> pares = new List<int>();
    for (int i = 0; i <= limite; i += 2)
        pares.Add(i);
    return pares;
}
```

A lista inteira é montada antes de alguém ver o primeiro número.

## Depois

```csharp
IEnumerable<int> ParesAte(int limite)
{
    for (int i = 0; i <= limite; i += 2)
        yield return i;
}
```

## O que observar

Cada `yield return` entrega um número. O `for` só anda quando alguém pede o próximo, por exemplo num `foreach`. `yield break` encerra antes do fim. O método não devolve a lista pronta: devolve um `IEnumerable` que produz os itens na hora.
