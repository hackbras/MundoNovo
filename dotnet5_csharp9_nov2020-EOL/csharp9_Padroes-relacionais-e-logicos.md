# Padrões relacionais e lógicos

O `switch` e o `is` comparam com `<`, `>`, `<=` e `>=`. `and`, `or` e `not` juntam essas condições.

## Antes

```csharp
string faixa;
if (idade < 12)
    faixa = "criança";
else if (idade < 18)
    faixa = "adolescente";
else
    faixa = "adulto";
```

## Depois

```csharp
string faixa = idade switch
{
    < 12 => "criança",
    >= 12 and < 18 => "adolescente",
    _ => "adulto"
};
```

## O que observar

Cada braço entrega o texto da faixa. `and` exige as duas partes. `or` exige uma. `is not null` testa presença sem escrever `!= null`. Dentro de um padrão de propriedade, fica `pedido is { Total: > 0 and < 100 }`.
