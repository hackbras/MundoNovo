# Propriedades automáticas

A propriedade automática declara `get` e `set` sem o campo e sem o corpo. O compilador cria o campo escondido.

## Antes

```csharp
public class Pessoa
{
    private string _nome;

    public string Nome
    {
        get { return _nome; }
        set { _nome = value; }
    }
}
```

## Depois

```csharp
public class Pessoa
{
    public string Nome { get; set; }
}
```

## O que observar

`pessoa.Nome = "Ana"` funciona como antes. Use a forma longa quando o `set` precisar validar ou quando o `get` calcular um valor. O campo escondido não tem nome no seu código; no C# 7.3 dá para colocar um atributo nele com `field:`.
