# Tipos genéricos

Um tipo genérico guarda o tipo entre `< >`. A lista de texto só aceita texto, e a leitura sai sem conversão.

## Antes

```csharp
ArrayList nomes = new ArrayList();
nomes.Add("Ana");
nomes.Add(10);
string primeiro = (string)nomes[0];
```

A lista aceita qualquer coisa. O erro do `10` aparece quando alguém faz o `(string)`.

## Depois

```csharp
List<string> nomes = new List<string>();
nomes.Add("Ana");
string primeiro = nomes[0];
```

## O que observar

`nomes.Add(10)` deixa de compilar. O `<string>` vale para a lista inteira. `List<T>` é uma classe pronta da biblioteca; o recurso da linguagem é criar e usar tipos com `<T>`, inclusive os seus: `class Caixa<T>`. Dá para limitar com `where T : struct` ou `where T : class`.
