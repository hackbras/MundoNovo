# Namespace com escopo de arquivo

O namespace pode valer para o arquivo inteiro, sem um bloco em volta de todas as classes.

## Antes

```csharp
namespace Loja
{
    public class Produto
    {
        public string Nome { get; set; } = "";
    }
}
```

## Depois

```csharp
namespace Loja;

public class Produto
{
    public string Nome { get; set; } = "";
}
```

## O que observar

O ponto e vírgula no fim de `namespace Loja;` substitui as chaves. Tudo que vem abaixo, neste arquivo, pertence a `Loja`. Um arquivo continua com um namespace só: se precisar de outro, use o formato antigo com chaves.
