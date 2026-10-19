# Padrões de propriedade estendidos

Um padrão pode descer por várias propriedades com ponto, sem abrir um padrão novo a cada nível.

## Antes

```csharp
if (pedido is Pedido { Cliente: Cliente { Cidade: "Recife" } })
{
    Console.WriteLine("Entrega local");
}
```

## Depois

```csharp
if (pedido is Pedido { Cliente.Cidade: "Recife" })
{
    Console.WriteLine("Entrega local");
}
```

## O que observar

`Cliente.Cidade` lê a cidade do cliente dentro do mesmo padrão. Se `Cliente` for nulo, o padrão falha e o `if` não entra. O tipo `Pedido` na frente continua opcional quando a variável já é desse tipo.
