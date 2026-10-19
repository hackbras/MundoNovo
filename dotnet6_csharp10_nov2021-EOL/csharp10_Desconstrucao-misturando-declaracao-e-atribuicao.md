# Desconstrução misturando declaração e atribuição

Na mesma desconstrução, uma variável pode já existir e a outra pode ser declarada ali.

## Antes

```csharp
(int X, int Y) ponto = (3, 4);

int x;
int y;
(x, y) = ponto;
```

Todas as variáveis da lista tinham de ser novas, ou todas já tinham de existir.

## Depois

```csharp
(int X, int Y) ponto = (3, 4);

int x = 0;
(x, int y) = ponto;
```

## O que observar

`x` já existia e recebe `3`. `int y` nasce nessa linha e recebe `4`. A mistura vale para tuplas e para tipos com `Deconstruct`. Cada posição segue a sua regra: ou declara, ou atribui.
