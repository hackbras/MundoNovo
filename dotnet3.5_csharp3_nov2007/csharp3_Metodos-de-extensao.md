# Métodos de extensão

Um método de extensão é um método estático que aparece como se fosse método do tipo. O primeiro parâmetro leva `this`.

## Antes

```csharp
public static class TextoUtil
{
    public static string Resumir(string texto, int tamanho)
    {
        if (texto.Length <= tamanho)
            return texto;
        return texto.Substring(0, tamanho);
    }
}

string curto = TextoUtil.Resumir(nome, 10);
```

## Depois

```csharp
public static class TextoUtil
{
    public static string Resumir(this string texto, int tamanho)
    {
        if (texto.Length <= tamanho)
            return texto;
        return texto.Substring(0, tamanho);
    }
}

string curto = nome.Resumir(10);
```

## O que observar

A classe do método precisa ser `static`, e o arquivo que chama `nome.Resumir` precisa do `using` do namespace dela. Não é herança: o compilador transforma a chamada em `TextoUtil.Resumir(nome, 10)`. O LINQ é feito de métodos de extensão em `IEnumerable<T>`.
