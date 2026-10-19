# Lambdas com tipo natural

Uma lambda pode ter um tipo próprio. Dá para guardá-la em `var` quando os parâmetros declaram o tipo.

## Antes

```csharp
Func<string, int> tamanho = texto => texto.Length;
```

O compilador precisava do `Func<...>` escrito à esquerda para saber o tipo da variável.

## Depois

```csharp
var tamanho = (string texto) => texto.Length;
int n = tamanho("Ana"); // 3
```

## O que observar

Os tipos dos parâmetros precisam aparecer na lambda para o `var` funcionar. `texto => texto.Length` sozinho ainda não tem tipo, porque `texto` poderia ser várias coisas. O mesmo recurso permite escrever o tipo de retorno na frente: `var ler = int (string texto) => int.Parse(texto);`.
