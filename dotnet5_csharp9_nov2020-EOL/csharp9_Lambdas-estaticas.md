# Lambdas estáticas

`static` numa lambda proíbe usar variáveis de fora. A lambda fica só com os parâmetros e com o que é estático.

## Antes

```csharp
int fator = 2;
Func<int, int> dobrar = x => x * fator;
```

A lambda guarda `fator`. Isso cria um objeto para carregar essa variável.

## Depois

```csharp
Func<int, int> dobrar = static x => x * 2;
```

## O que observar

`static x => x * fator` não compila, porque `fator` é variável do método. Constante, método estático e operador podem entrar. O efeito prático é a lambda não segurar as variáveis de quem chamou. Função local também aceita `static`, desde o C# 8, com a mesma regra.
