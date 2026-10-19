# Literais binários e separadores

`0b` escreve um número em binário. O `_` separa os dígitos para a leitura e não muda o valor.

## Antes

```csharp
int mascara = 42;
int milhao = 1000000;
```

## Depois

```csharp
int mascara = 0b0010_1010;
int milhao = 1_000_000;
```

## O que observar

`0b0010_1010` é o mesmo `42`. `1_000_000` é o mesmo `1000000`. O `_` também cabe no hexadecimal: `0x00_FF`. Ele não pode ser o primeiro nem o último caractere do número, nem ficar grudado no ponto decimal. No C# 7.2, logo depois de `0b` ou `0x`, o `_` passou a valer: `0b_0010`.
