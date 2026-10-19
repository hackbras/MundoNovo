# Propriedades init

`init` deixa a propriedade ser preenchida na criação. Depois disso, a atribuição não compila.

## Antes

```csharp
public class Pessoa
{
    public string Nome { get; set; }
}

var pessoa = new Pessoa { Nome = "Ana" };
pessoa.Nome = "Bia";
```

Com `set`, qualquer código muda `Nome` mais tarde.

## Depois

```csharp
public class Pessoa
{
    public string Nome { get; init; }
}

var pessoa = new Pessoa { Nome = "Ana" };
```

## O que observar

O inicializador `{ Nome = "Ana" }` e o construtor da classe podem gravar `Nome`. Na linha seguinte, `pessoa.Nome = "Bia"` é erro de compilação. `init` não impede a classe de mudar o campo por dentro, num método dela. Quem está fora é que não atribui de novo.
