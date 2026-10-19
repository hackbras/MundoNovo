# Streams assíncronos

`await foreach` lê itens que vão ficando prontos. O método produz com `yield return` e pode dar `await` entre um item e outro.

## Antes

```csharp
async Task<List<string>> ListarAsync()
{
    await Task.Delay(100);
    return new List<string> { "Ana", "Bia" };
}
```

Quem chama espera a lista inteira ficar pronta.

## Depois

```csharp
async IAsyncEnumerable<string> ListarAsync()
{
    yield return "Ana";
    await Task.Delay(100);
    yield return "Bia";
}

await foreach (string nome in ListarAsync())
{
    Console.WriteLine(nome);
}
```

## O que observar

`"Ana"` pode ser impresso antes da espera terminar. `"Bia"` sai depois. O retorno é `IAsyncEnumerable<string>`, não uma `List`. Este recurso pede .NET Core 3 ou mais novo. No .NET Framework 4.8 o `await foreach` não faz parte da biblioteca padrão.
