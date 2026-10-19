# Alias para qualquer tipo

`using` pode apelidar um tipo complicado, inclusive tupla, array e tipo anulável.

## Antes

```csharp
(int X, int Y) origem = (0, 0);
(int X, int Y) destino = (3, 4);
```

O formato da tupla era repetido em cada variável. O `using` antigo só apelidava namespace e classe com nome.

## Depois

```csharp
using Ponto = (int X, int Y);

Ponto origem = (0, 0);
Ponto destino = (3, 4);
```

## O que observar

`Ponto` é só um apelido de `(int X, int Y)`. Os dois são o mesmo tipo. O apelido vale no arquivo em que foi escrito. Também funciona para array (`using Notas = int[];`) e para anulável (`using Nome = string?;`).
