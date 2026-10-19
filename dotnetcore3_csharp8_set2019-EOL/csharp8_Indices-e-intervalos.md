# Índices e intervalos

`^` conta a partir do fim. `..` recorta um trecho. O fim do intervalo fica de fora.

## Antes

```csharp
string[] nomes = { "Ana", "Bia", "Caio", "Duda" };
string ultimo = nomes[nomes.Length - 1];
string[] meio = new string[2];
Array.Copy(nomes, 1, meio, 0, 2);
```

## Depois

```csharp
string[] nomes = { "Ana", "Bia", "Caio", "Duda" };
string ultimo = nomes[^1];
string[] meio = nomes[1..3];
```

## O que observar

`^1` é o último, `"Duda"`. `^2` é o penúltimo. `1..3` pega os índices 1 e 2: `"Bia"` e `"Caio"`. O 3 não entra. `..2` vai do começo até antes do 2, e `2..` vai do 2 até o fim. Array e `string` aceitam essa escrita. Um tipo seu aceita se tiver um indexador que receba `Index` ou `Range`.
