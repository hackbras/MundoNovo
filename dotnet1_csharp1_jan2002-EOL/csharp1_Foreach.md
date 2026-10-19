# foreach

`foreach` percorre uma lista, um array ou outra coleção, um item de cada vez, sem você cuidar do índice.

## Antes

```csharp
string[] nomes = new string[] { "Ana", "Bia" };

for (int i = 0; i < nomes.Length; i++)
{
    Console.WriteLine(nomes[i]);
}
```

## Depois

```csharp
string[] nomes = new string[] { "Ana", "Bia" };

foreach (string nome in nomes)
{
    Console.WriteLine(nome);
}
```

## O que observar

`foreach` vai do primeiro ao último. Dentro do laço, `nome` é o item da vez, e não dá para trocar a coleção no meio (adicionar ou remover quebra a leitura). Quando o índice importa, o `for` continua útil. A partir do .NET Framework 1.1, se o enumerador da coleção tiver `Dispose`, o `foreach` chama esse método no fim.
