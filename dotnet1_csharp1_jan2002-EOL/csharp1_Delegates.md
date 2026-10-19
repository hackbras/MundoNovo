# Delegates

Um `delegate` é uma variável que guarda um método. Quem recebe essa variável chama o método sem saber o nome dele.

## Antes

```csharp
int Dobrar(int valor)
{
    return valor * 2;
}

int resultado = Dobrar(4);
```

A chamada está presa no método `Dobrar`.

## Depois

```csharp
delegate int Operacao(int valor);

int Dobrar(int valor)
{
    return valor * 2;
}

Operacao calcular = Dobrar;
int resultado = calcular(4);
```

## O que observar

O método guardado precisa ter o mesmo formato do `delegate`: aqui, recebe um `int` e devolve um `int`. Dá para apontar `calcular` para outro método compatível e a chamada `calcular(4)` continua igual. Evento, no arquivo ao lado, é um `delegate` com regra de quem pode chamar.
