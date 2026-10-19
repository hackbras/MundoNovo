# Records

`record` declara um tipo cujo `==` compara os valores. A forma curta já cria construtor e propriedades.

## Antes

```csharp
public class Pessoa
{
    public string Nome { get; set; }
    public int Idade { get; set; }
}

var a = new Pessoa { Nome = "Ana", Idade = 20 };
var b = new Pessoa { Nome = "Ana", Idade = 20 };
bool iguais = a == b; // false: são dois objetos
```

## Depois

```csharp
public record Pessoa(string Nome, int Idade);

var a = new Pessoa("Ana", 20);
var b = new Pessoa("Ana", 20);
bool iguais = a == b; // true: os valores são iguais
```

## O que observar

O `record` posicional cria o construtor e as propriedades `Nome` e `Idade` com `init`. O `ToString` escreve os valores, no formato `Pessoa { Nome = Ana, Idade = 20 }`. Para uma cópia com um campo diferente, use `with`. Um `record` deste arquivo é uma classe. O `record struct` chegou no C# 10.
