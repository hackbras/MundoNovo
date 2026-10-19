# Membros de extensão

Além de métodos, uma extensão pode acrescentar propriedades e operadores a um tipo que você não escreveu.

## Antes

```csharp
public static class TextoExtensoes
{
    public static int ContarPalavras(this string texto) =>
        texto.Split(' ', StringSplitOptions.RemoveEmptyEntries).Length;
}

int n = "um dois".ContarPalavras();
```

## Depois

```csharp
public static class TextoExtensoes
{
    extension(string texto)
    {
        public int ContarPalavras =>
            texto.Split(' ', StringSplitOptions.RemoveEmptyEntries).Length;
    }
}

int n = "um dois".ContarPalavras;
```

## O que observar

`extension(string texto)` diz qual valor recebe o membro novo. Dentro do bloco, `ContarPalavras` é uma propriedade, por isso a chamada não tem parênteses. O método de extensão antigo continua válido. O bloco `extension` é o lugar dos membros novos que não são só método.
