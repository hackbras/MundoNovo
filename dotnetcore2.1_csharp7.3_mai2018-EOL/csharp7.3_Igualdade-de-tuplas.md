# Igualdade de tuplas

`==` e `!=` comparam tuplas item por item. Os nomes dos itens não entram na conta.

## Antes

```csharp
var a = (Nome: "Ana", Idade: 20);
var b = (Nome: "Ana", Idade: 20);

bool iguais = a.Nome == b.Nome && a.Idade == b.Idade;
```

## Depois

```csharp
var a = (Nome: "Ana", Idade: 20);
var b = (Nome: "Ana", Idade: 20);

bool iguais = a == b;
```

## O que observar

`iguais` fica `true` porque os valores, na ordem, são os mesmos. `(Nome: "Ana", Idade: 20) == (Pessoa: "Ana", Anos: 20)` também é `true`: o compilador olha os tipos e a ordem, não os nomes. `!=` faz o contrário. Tuplas de tamanhos diferentes não se comparam.
