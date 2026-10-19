# Quebra de linha na interpolação

O código dentro de `{ }` numa string interpolada pode ocupar várias linhas.

## Antes

```csharp
decimal preco = 10m;
int quantidade = 3;
decimal total = preco * quantidade;
string texto = $"Total: {total}";
```

A conta precisava estar numa variável, porque a interpolação não aceitava quebra de linha dentro das chaves.

## Depois

```csharp
decimal preco = 10m;
int quantidade = 3;
string texto = $"Total: {
    preco * quantidade
}";
```

## O que observar

A expressão entre `{` e `}` é código normal. Quebrar a linha só organiza a leitura; o valor de `texto` continua `"Total: 30"`. Vale para `if`, chamada de método e qualquer expressão que caiba ali.
