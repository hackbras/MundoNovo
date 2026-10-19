# Parâmetros padrão em lambdas

Um parâmetro de lambda pode ter valor padrão, como um parâmetro de método.

## Antes

```csharp
Func<string, string> saudar = nome => $"Oi, {nome}";

string mensagem = saudar("Ana");
```

Quem chamava a lambda era obrigado a passar o nome.

## Depois

```csharp
var saudar = (string nome = "visitante") => $"Oi, {nome}";

string comNome = saudar("Ana");
string semNome = saudar();
```

## O que observar

`saudar()` usa `"visitante"`. `saudar("Ana")` usa o texto passado. O valor padrão faz parte do tipo da lambda, então ela combina com um delegate que também tenha esse parâmetro opcional.
