# Tipos anônimos

Um tipo anônimo carrega alguns campos sem você declarar uma classe. O compilador inventa o tipo.

## Antes

```csharp
class Resumo
{
    public string Nome;
    public int Idade;
}

Resumo resumo = new Resumo();
resumo.Nome = pessoa.Nome;
resumo.Idade = pessoa.Idade;
```

## Depois

```csharp
var resumo = new { pessoa.Nome, pessoa.Idade };
Console.WriteLine(resumo.Nome);
```

## O que observar

`resumo.Nome` e `resumo.Idade` existem, e são somente leitura. Não há um nome de classe para escrever no lugar de `var`. Serve para um trecho curto, principalmente no meio de uma consulta LINQ. Dois `new { ... }` com as mesmas propriedades, na mesma ordem e nos mesmos tipos, são o mesmo tipo anônimo.
