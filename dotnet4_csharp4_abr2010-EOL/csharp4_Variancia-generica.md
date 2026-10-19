# Variância genérica

`out` e `in` num tipo genérico permitem tratar um tipo mais específico como um tipo mais geral, ou o contrário, quando isso é seguro.

## Antes

```csharp
IEnumerable<string> nomes = new List<string> { "Ana", "Bia" };
List<object> objetos = new List<object>();
foreach (string nome in nomes)
    objetos.Add(nome);
```

`string` é um `object`, mas no C# 3 a atribuição direta `IEnumerable<object> objetos = nomes` não compilava.

## Depois

```csharp
IEnumerable<string> nomes = new List<string> { "Ana", "Bia" };
IEnumerable<object> objetos = nomes;
```

## O que observar

`IEnumerable<out T>` só entrega `T`, nunca recebe um `T` para guardar. Por isso uma sequência de `string` serve onde pedem uma sequência de `object`. O contrário usa `in`: um `Action<object>`, que aceita qualquer objeto, serve onde pedem um `Action<string>`. `List<string>` continua sem poder ir para `List<object>`, porque a lista também recebe itens.
