# Operador de coalescência nula

`??` devolve o valor da esquerda quando ele existe. Quando a esquerda é `null`, devolve o que está à direita.

## Antes

```csharp
string cidade = null;
string texto = cidade != null ? cidade : "sem cidade";
```

## Depois

```csharp
string cidade = null;
string texto = cidade ?? "sem cidade";
```

## O que observar

`texto` fica `"sem cidade"` porque `cidade` é `null`. Se `cidade` fosse `"Recife"`, `texto` seria `"Recife"` e o lado direito nem seria usado. Dá para encadear: `apelido ?? nome ?? "sem nome"`. O primeiro que não for `null` ganha.
