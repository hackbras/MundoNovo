# Propriedades com suporte de field

`field` é o campo escondido da propriedade. Dá para validar no `set` sem declarar um campo à parte.

## Antes

```csharp
private string _nome = "";

public string Nome
{
    get => _nome;
    set => _nome = value.Trim();
}
```

## Depois

```csharp
public string Nome
{
    get => field;
    set => field = value.Trim();
}
```

## O que observar

`field` só existe dentro dos acessores dessa propriedade. O compilador cria o campo. `value` continua sendo o valor que chegou no `set`. Se a classe já tem um membro chamado `field`, escreva `@field` para falar do campo da propriedade, ou escolha outro nome para o membro.
