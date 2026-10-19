# Tuplas

Uma tupla junta dois ou mais valores num retorno só, com nome em cada um. Serve quando criar uma classe só para isso seria demais.

## Antes

```csharp
class Resumo
{
    public string Nome { get; set; }
    public int Idade { get; set; }
}

Resumo Montar(Pessoa pessoa)
{
    return new Resumo { Nome = pessoa.Nome, Idade = pessoa.Idade };
}
```

## Depois

```csharp
(string Nome, int Idade) Montar(Pessoa pessoa)
{
    return (pessoa.Nome, pessoa.Idade);
}

var resumo = Montar(pessoa);
Console.WriteLine(resumo.Nome);
```

## O que observar

`resumo.Nome` e `resumo.Idade` são os nomes escritos no retorno. Sem nome, o compilador oferece `Item1` e `Item2`. No .NET Framework 4.7 a tupla já vem na biblioteca. Num projeto mais antigo, o pacote `System.ValueTuple` faz o mesmo papel.
