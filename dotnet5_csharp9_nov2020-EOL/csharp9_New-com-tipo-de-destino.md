# new com tipo de destino

Quando a variável já mostra o tipo, o `new` pode omitir o nome. Os parênteses continuam, com ou sem argumentos.

## Antes

```csharp
Pessoa pessoa = new Pessoa("Ana", 20);
List<string> nomes = new List<string> { "Ana", "Bia" };
```

## Depois

```csharp
Pessoa pessoa = new("Ana", 20);
List<string> nomes = new() { "Ana", "Bia" };
```

## O que observar

O tipo sai do lado esquerdo. `new()` sem argumentos chama o construtor vazio. `var pessoa = new("Ana")` não compila: o `var` e o `new` ficariam os dois sem tipo. O mesmo encurtamento vale no `? :` quando o destino já tem tipo: `int? qtd = tem ? 1 : null`.
