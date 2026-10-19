# Expressões switch

O `switch` pode ser uma expressão que produz um valor. Cada braço usa `=>` e termina sem `break`.

## Antes

```csharp
string texto;
switch (status)
{
    case 1:
        texto = "Novo";
        break;
    case 2:
        texto = "Pago";
        break;
    default:
        texto = "Outro";
        break;
}
```

## Depois

```csharp
string texto = status switch
{
    1 => "Novo",
    2 => "Pago",
    _ => "Outro"
};
```

## O que observar

`texto` recebe o resultado do braço que combinar. `_` é o caso que sobrou. Cada braço é uma expressão, não um bloco de comandos. Se faltar um caso e não houver `_`, o compilador reclama quando não consegue provar que todos os valores foram cobertos.
