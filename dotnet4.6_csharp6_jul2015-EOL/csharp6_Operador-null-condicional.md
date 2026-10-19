# Operador null-condicional

`?.` lê um membro só se o objeto existir. Se for `null`, o resultado é `null` e o restante da linha não roda.

## Antes

```csharp
string cidade = null;
if (cliente != null && cliente.Endereco != null)
    cidade = cliente.Endereco.Cidade;
```

## Depois

```csharp
string cidade = cliente?.Endereco?.Cidade;
```

## O que observar

Se `cliente` ou `Endereco` for `null`, `cidade` fica `null`. Se os dois existirem, `cidade` recebe o texto. `?[]` faz o mesmo para índice: `pedido?.Itens?[0]`. Junto com `??`, vira `cliente?.Endereco?.Cidade ?? "sem cidade"`.
