# Strings interpoladas constantes

Uma string interpolada pode ser `const` quando cada pedaço dentro das chaves também é constante.

## Antes

```csharp
const string nome = "Ana";
const string mensagem = "Olá, " + nome;
```

`$"..."` era calculado na execução, então não podia ser `const`.

## Depois

```csharp
const string nome = "Ana";
const string mensagem = $"Olá, {nome}";
```

## O que observar

`nome` precisa ser `const`. Uma variável comum, um método ou uma propriedade quebram a compilação, porque o valor teria de ser montado com o programa rodando. O resultado é o mesmo texto de sempre: `"Olá, Ana"`.
