# Parâmetros in

`in` passa um `struct` por referência e impede o método de alterar esse valor. A chamada não precisa escrever `in`.

## Antes

```csharp
decimal Desconto(decimal preco)
{
    return preco * 0.9m;
}
```

`preco` é uma cópia. No `decimal` a cópia é pequena. Num `struct` com muitos campos, a cópia custa mais.

## Depois

```csharp
decimal Desconto(in decimal preco)
{
    return preco * 0.9m;
}

decimal valor = Desconto(100m);
```

## O que observar

`preco = 0` dentro de `Desconto` não compila. O método só lê. Quem chama escreve `Desconto(100m)`, sem `in`. O ganho aparece em `struct` grande e `readonly`. Para `int` e `decimal`, a cópia já era barata: o exemplo mostra a sintaxe.
