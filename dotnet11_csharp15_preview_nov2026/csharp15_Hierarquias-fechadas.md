# Hierarquias fechadas

No C# 15, ainda em preview, `closed` fecha a lista de filhos diretos de uma classe: só o mesmo assembly pode herdar dela, e o `switch` sabe todos os casos.

## Antes

```csharp
public abstract record Portao;

public record Fechado : Portao;
public record Aberto(float Percentual) : Portao;

string Descrever(Portao portao) => portao switch
{
    Fechado => "fechado",
    Aberto(var percentual) => $"{percentual}% aberto",
    _ => "desconhecido"
};
```

Outro projeto podia criar um terceiro filho, então o `_` existia para o caso que o compilador não previa.

## Depois

```csharp
public closed record Portao;

public record Fechado : Portao;
public record Aberto(float Percentual) : Portao;

string Descrever(Portao portao) => portao switch
{
    Fechado => "fechado",
    Aberto(var percentual) => $"{percentual}% aberto"
};
```

## O que observar

`closed` já deixa o tipo abstrato: não dá para fazer `new Portao()`. Os filhos diretos nascem no mesmo assembly. O `switch` sem `_` compila porque `Fechado` e `Aberto` esgotam a hierarquia. Um filho novo que você esquecer de tratar vira erro de compilação. A sintaxe pode mudar até o C# 15 sair do preview.
