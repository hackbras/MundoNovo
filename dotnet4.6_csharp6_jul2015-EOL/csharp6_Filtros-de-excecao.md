# Filtros de exceção

`when` escolhe se aquele `catch` serve. A condição é um `bool`. Se for falsa, outro `catch` pode tratar a exceção.

## Antes

```csharp
try
{
    LerArquivo();
}
catch (IOException ex)
{
    if (!ex.Message.Contains("disco"))
        throw;
    Console.WriteLine(ex.Message);
}
```

## Depois

```csharp
try
{
    LerArquivo();
}
catch (IOException ex) when (ex.Message.Contains("disco"))
{
    Console.WriteLine(ex.Message);
}
```

## O que observar

O `when` roda antes de entrar no `catch`. Se a mensagem não tiver `"disco"`, esse `catch` é pulado e a exceção segue para outro `catch` ou para quem chamou. Dá para filtrar por qualquer condição, não só pelo tipo da exceção.
