# Classes parciais

`partial` divide uma classe em dois ou mais arquivos. O compilador junta as partes e vira uma classe só.

## Antes

```csharp
// Pessoa.cs, o arquivo crescia com tudo misturado
public class Pessoa
{
    public string Nome;
    public string Cidade;
}
```

## Depois

```csharp
// Pessoa.cs
public partial class Pessoa
{
    public string Nome;
}

// Pessoa.Endereco.cs
public partial class Pessoa
{
    public string Cidade;
}
```

## O que observar

As partes precisam do mesmo nome, do mesmo namespace e do mesmo projeto. Para o restante do programa existe uma `Pessoa` só, com `Nome` e `Cidade`. `partial` também serve em `struct` e em `interface`. Código gerado por ferramenta costuma ocupar uma parte, e o seu código fica na outra.
