# await em catch e finally

`await` pode ficar dentro de `catch` e de `finally`. A espera de um log ou de uma limpeza cabe ali.

## Antes

```csharp
Exception erro = null;
try
{
    Salvar();
}
catch (Exception ex)
{
    erro = ex;
}

if (erro != null)
    await LogAsync(erro);
```

No C# 5 o `await` era proibido dentro do `catch`.

## Depois

```csharp
try
{
    Salvar();
}
catch (Exception ex)
{
    await LogAsync(ex);
}
```

## O que observar

O `catch` espera o `LogAsync` terminar antes de seguir. O mesmo vale para o `finally`, por exemplo um `await` que fecha uma conexão. O método em volta continua precisando ser `async`.
