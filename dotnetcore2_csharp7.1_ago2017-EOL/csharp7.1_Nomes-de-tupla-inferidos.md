# Nomes de tupla inferidos

Os nomes de uma tupla podem sair do nome da variável ou da propriedade. Não é preciso escrever `Nome:` na frente.

## Antes

```csharp
var resumo = (Nome: pessoa.Nome, Idade: pessoa.Idade);
Console.WriteLine(resumo.Nome);
```

## Depois

```csharp
var resumo = (pessoa.Nome, pessoa.Idade);
Console.WriteLine(resumo.Nome);
```

## O que observar

`resumo.Nome` e `resumo.Idade` aparecem porque cada item é uma propriedade com esse nome. Uma conta não traz nome: `(pessoa.Idade + 1)` vira `Item1`, a menos que você escreva `(Idade: pessoa.Idade + 1)`. O nome simples da variável também serve: `(nome, idade)`.
