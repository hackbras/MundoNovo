# var

`var` pede ao compilador para descobrir o tipo da variável pelo valor da direita. O tipo fica fixo.

## Antes

```csharp
List<string> nomes = new List<string>();
```

O tipo `List<string>` está escrito duas vezes.

## Depois

```csharp
var nomes = new List<string>();
```

## O que observar

`nomes` é `List<string>` do mesmo jeito. `var` não é um tipo que muda depois, e não é o `dynamic` do C# 4. `var x = null` não compila, porque a direita não mostra um tipo. Passe o mouse na variável no editor para ver o tipo que o compilador escolheu.
