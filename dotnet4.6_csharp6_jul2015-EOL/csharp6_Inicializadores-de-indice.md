# Inicializadores de índice

Um dicionário pode nascer com a mesma cara de uma atribuição por chave: `["Ana"] = 10`.

## Antes

```csharp
var placar = new Dictionary<string, int>
{
    { "Ana", 10 },
    { "Bia", 8 }
};
```

Cada par chama `Add`.

## Depois

```csharp
var placar = new Dictionary<string, int>
{
    ["Ana"] = 10,
    ["Bia"] = 8
};
```

## O que observar

As duas formas preenchem o dicionário. A de colchetes usa o indexador, então uma chave repetida substitui o valor. A forma com `{ "Ana", 10 }` chama `Add` e, no dicionário, uma chave repetida estoura. Qualquer tipo com indexador de escrita aceita a forma dos colchetes.
