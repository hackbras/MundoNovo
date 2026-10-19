# Inicializadores de coleção

A coleção pode nascer já com os itens, entre chaves. O compilador chama `Add` para cada um.

## Antes

```csharp
List<string> nomes = new List<string>();
nomes.Add("Ana");
nomes.Add("Bia");
```

## Depois

```csharp
List<string> nomes = new List<string> { "Ana", "Bia" };
```

## O que observar

Uma coleção sua entra nessa sintaxe se tiver um método `Add` compatível. Um dicionário usa chaves internas, uma por par: `{ "Ana", 10 }`, e isso chama `Add("Ana", 10)`. No C# 6 o dicionário também aceita `["Ana"] = 10`.
