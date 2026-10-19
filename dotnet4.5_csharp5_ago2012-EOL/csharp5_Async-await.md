# async e await

`await` espera uma tarefa terminar sem travar o método numa sequência de callbacks. `async` marca o método que usa `await`.

## Antes

```csharp
public Task<string> BuscarNomeAsync()
{
    return Task.Delay(100).ContinueWith(_ => "Ana");
}
```

O que acontece depois da espera fica dentro do `ContinueWith`.

## Depois

```csharp
public async Task<string> BuscarNomeAsync()
{
    await Task.Delay(100);
    return "Ana";
}
```

## O que observar

`async` não cria uma thread sozinho. No `await`, o método devolve o controle e continua depois que a `Task` termina. Quem chama também dá `await` em `BuscarNomeAsync()`. Prefira devolver `Task` ou `Task<string>`. `async void` fica para evento, porque ninguém consegue esperar o fim nem ver a exceção com `await`.
