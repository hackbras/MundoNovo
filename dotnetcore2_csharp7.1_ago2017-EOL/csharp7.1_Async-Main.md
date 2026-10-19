# async Main

`Main` pode ser `async` e devolver `Task`. O programa espera essa tarefa acabar.

## Antes

```csharp
static void Main()
{
    MainAsync().GetAwaiter().GetResult();
}

static async Task MainAsync()
{
    await Task.Delay(100);
    Console.WriteLine("Olá");
}
```

## Depois

```csharp
static async Task Main()
{
    await Task.Delay(100);
    Console.WriteLine("Olá");
}
```

## O que observar

`Main` também pode devolver `Task<int>`. O número vira o código de saída do programa. `async void` no `Main` não é o caminho: ninguém espera o fim, e um erro dentro dele se perde. Para usar este `Main`, o projeto precisa da linguagem C# 7.1 ou mais nova.
