# dynamic

`dynamic` desliga a verificação do compilador naquela variável. O membro é resolvido quando o programa roda.

## Antes

```csharp
object item = ObterItem();
Type tipo = item.GetType();
tipo.GetProperty("Nome").SetValue(item, "Ana");
```

A reflexão acha a propriedade `Nome` pelo texto e atribui.

## Depois

```csharp
dynamic item = ObterItem();
item.Nome = "Ana";
```

## O que observar

O compilador aceita `item.Nome` sem conhecer o tipo. Se `Nome` não existir, o erro aparece na execução, não na compilação. Serve para COM, JSON solto e objetos que o compilador não enxerga. Quando o tipo é conhecido, uma variável comum é mais segura.
