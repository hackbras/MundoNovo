# Atributo no campo da propriedade

`field:` manda o atributo para o campo escondido de uma propriedade automática. Sem isso, o atributo vai para a propriedade.

## Antes

```csharp
public class Login
{
    [NonSerialized]
    private string _senha;

    public string Senha
    {
        get { return _senha; }
        set { _senha = value; }
    }
}
```

O campo precisava estar escrito no código para receber `[NonSerialized]`.

## Depois

```csharp
public class Login
{
    [field: NonSerialized]
    public string Senha { get; set; }
}
```

## O que observar

`field:` é o alvo do atributo. A propriedade continua automática. `[NonSerialized]` só pode ficar em campo, então na propriedade automática ele precisa desse alvo. Outros alvos conhecidos são `method:` e `param:`, quando a propriedade tem mais de um lugar para marcar.
