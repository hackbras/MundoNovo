# Atribuição com coalescência nula

`??=` só atribui quando a variável está `null`. Se ela já tem valor, o lado direito não roda.

## Antes

```csharp
if (nome == null)
    nome = "sem nome";
```

## Depois

```csharp
nome ??= "sem nome";
```

## O que observar

`null` dispara a atribuição. Texto vazio `""` não é `null`, então `??=` deixa `""` como está. Se o lado direito for uma chamada, ela só acontece quando `nome` é `null`. O `??` sem o `=` apenas escolhe o valor e não grava de volta.
