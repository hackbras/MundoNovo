# Expressões with

`with` copia um `record` e troca só os valores que você listar. O original permanece como estava.

## Antes

```csharp
public class Pessoa
{
    public string Nome { get; set; }
    public string Cidade { get; set; }
}

Pessoa bia = new Pessoa { Nome = "Bia", Cidade = ana.Cidade };
```

Cada campo da cópia era copiado à mão.

## Depois

```csharp
public record Pessoa(string Nome, string Cidade);

var ana = new Pessoa("Ana", "Recife");
Pessoa bia = ana with { Nome = "Bia" };
```

## O que observar

`bia.Nome` é `"Bia"` e `bia.Cidade` é `"Recife"`. `ana` continua com nome `"Ana"`. `with` cria outro objeto. Dá para trocar vários campos: `{ Nome = "Bia", Cidade = "Olinda" }`. No C# 9 o `with` é de `record`. No C# 10 um `struct` também aceita.
