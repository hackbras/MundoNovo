# Propriedades parciais

Uma propriedade pode ser `partial`: a declaração fica numa parte da classe e o `get`/`set` fica na outra.

## Antes

```csharp
public partial class Pessoa
{
    public string Nome { get; set; } = "";
}
```

A propriedade inteira tinha de estar numa parte só. O gerador de código não conseguia completar só o acesso.

## Depois

```csharp
public partial class Pessoa
{
    public partial string Nome { get; set; }
}

public partial class Pessoa
{
    private string _nome = "";

    public partial string Nome
    {
        get => _nome;
        set => _nome = value.Trim();
    }
}
```

## O que observar

A primeira parte anuncia a propriedade. A segunda parte implementa. As duas precisam concordar no tipo e nos acessores. Geradores de código usam isso para criar o miolo da propriedade sem apagar o que você declarou.
