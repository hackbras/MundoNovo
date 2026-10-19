# Expressão throw

`throw` pode ficar no meio de uma expressão. Cabe do lado direito de `??` e de `?:`.

## Antes

```csharp
if (texto == null)
    throw new ArgumentException("Informe o nome.");

string nome = texto;
```

## Depois

```csharp
string nome = texto ?? throw new ArgumentException("Informe o nome.");
```

## O que observar

Se `texto` tiver valor, `nome` recebe esse texto. Se for `null`, a exceção acontece e `nome` não recebe nada. O mesmo `throw` entra numa lambda de uma linha e no ramo de um `?:`. O tipo da exceção é o que você escolher.
