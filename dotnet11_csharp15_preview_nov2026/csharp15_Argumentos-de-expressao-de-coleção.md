# Argumentos de expressão de coleção

No C# 15, ainda em preview, `with(...)` no início de uma expressão de coleção passa argumentos ao construtor, como a capacidade ou o comparador.

## Antes

```csharp
string[] valores = ["um", "dois", "tres"];

List<string> nomes = new List<string>(valores.Length * 2);
nomes.AddRange(valores);

HashSet<string> conjunto = new HashSet<string>(StringComparer.OrdinalIgnoreCase)
{
    "Hello",
    "HELLO"
};
```

A capacidade e o comparador iam no `new`, fora dos colchetes.

## Depois

```csharp
string[] valores = ["um", "dois", "tres"];

List<string> nomes = [with(capacity: valores.Length * 2), .. valores];

HashSet<string> conjunto = [with(StringComparer.OrdinalIgnoreCase), "Hello", "HELLO"];
```

## O que observar

`with(...)` é o primeiro elemento e não entra na coleção. `.. valores` copia os textos para a lista, que já nasce com capacidade para o dobro. No `HashSet`, as duas palavras caem no mesmo item porque o comparador ignora maiúsculas. A sintaxe pode mudar até o C# 15 sair do preview.
