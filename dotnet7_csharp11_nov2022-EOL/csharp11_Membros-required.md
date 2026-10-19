# Membros required

`required` obriga quem cria o objeto a preencher aquela propriedade. Sem ela, o código não compila.

## Antes

```csharp
public class Pessoa
{
    public string Nome { get; set; }
}

Pessoa pessoa = new Pessoa(); // Nome ficou nulo e o compilador aceitou
```

## Depois

```csharp
public class Pessoa
{
    public required string Nome { get; set; }
}

Pessoa pessoa = new Pessoa { Nome = "Ana" };
```

## O que observar

O inicializador `{ Nome = "Ana" }` cumpre a obrigação. `new Pessoa()` sem `Nome` é erro de compilação. Um construtor que já recebe o nome pode avisar o compilador com `[SetsRequiredMembers]`, para não pedir a propriedade de novo.
