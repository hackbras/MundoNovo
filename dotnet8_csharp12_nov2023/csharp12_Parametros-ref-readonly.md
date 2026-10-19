# Parâmetros ref readonly

`ref readonly` recebe um struct grande pela referência e impede o método de alterar esse valor.

## Antes

```csharp
public readonly struct Medida
{
    public decimal Valor { get; init; }
}

void Mostrar(in Medida medida)
{
    Console.WriteLine(medida.Valor);
}
```

`in` já evitava a cópia, mas o compilador às vezes ainda copiava o valor para proteger o original.

## Depois

```csharp
void Mostrar(ref readonly Medida medida)
{
    Console.WriteLine(medida.Valor);
}

Medida medida = new() { Valor = 10m };
Mostrar(ref medida);
Mostrar(medida);
```

## O que observar

O método lê `medida` e não pode atribuir outro valor a ela. `ref medida` deixa claro que não há cópia. Chamar só com `medida`, sem `ref`, também compila; nesse caso o compilador pode copiar. `ref readonly` é a escolha quando a cópia de um struct grande pesa e o método só consulta.
