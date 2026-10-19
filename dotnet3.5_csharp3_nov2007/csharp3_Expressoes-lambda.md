# Expressões lambda

A lambda é um método curto escrito com `=>`. O lado esquerdo são os parâmetros. O lado direito é o resultado.

## Antes

```csharp
delegate int Operacao(int valor);

Operacao dobrar = delegate(int valor)
{
    return valor * 2;
};
```

## Depois

```csharp
Func<int, int> dobrar = valor => valor * 2;
int total = dobrar(4);
```

## O que observar

`valor => valor * 2` lê como "recebe valor e devolve valor vezes 2". Se o corpo tiver mais de uma linha, use chaves e `return`. Sem parâmetro, escreva `() => 10`. Com vários, `(a, b) => a + b`. `Func<int, int>` significa: entra um `int`, sai um `int`.
