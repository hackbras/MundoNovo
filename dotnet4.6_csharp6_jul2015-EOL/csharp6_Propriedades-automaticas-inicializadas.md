# Propriedades automáticas inicializadas

A propriedade automática pode receber o valor na declaração. Sem `set`, ela só é preenchida na declaração ou no construtor.

## Antes

```csharp
public class Produto
{
    public string Nome { get; set; }

    public Produto()
    {
        Nome = "sem nome";
    }
}
```

## Depois

```csharp
public class Produto
{
    public string Nome { get; set; } = "sem nome";
    public int Id { get; } = 1;
}
```

## O que observar

`Nome` continua podendo mudar depois. `Id` só tem `get`: o valor `1` entra na criação, e um construtor também pode atribuir `Id`. Fora da classe, `produto.Id = 2` não compila. O campo escondido continua existindo.
