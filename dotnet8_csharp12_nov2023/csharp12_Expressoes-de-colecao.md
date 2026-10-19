# Expressões de coleção

Colchetes criam a coleção. O mesmo escrito serve para array, `List` e outros tipos que aceitam essa forma.

## Antes

```csharp
int[] numeros = new int[] { 1, 2, 3 };
List<string> nomes = new List<string> { "Ana", "Bia" };
```

## Depois

```csharp
int[] numeros = [1, 2, 3];
List<string> nomes = ["Ana", "Bia"];
int[] todos = [.. numeros, 4];
```

## O que observar

O tipo da variável decide qual coleção nasce: `int[]` vira array, `List<string>` vira lista. `.. numeros` copia os elementos de outra coleção para dentro da nova. A lista vazia é `[]`.
