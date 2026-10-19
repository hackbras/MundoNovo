# Literais de string UTF-8

O sufixo `u8` grava o texto direto em bytes UTF-8, sem converter uma `string` na hora de executar.

## Antes

```csharp
byte[] bytes = System.Text.Encoding.UTF8.GetBytes("oi");
```

`GetBytes` cria um array novo cada vez que a linha roda.

## Depois

```csharp
ReadOnlySpan<byte> bytes = "oi"u8;
```

## O que observar

`"oi"u8` é um `ReadOnlySpan<byte>` com os bytes do texto. O compilador monta esses bytes no programa. Para guardar num `byte[]` que você possa alterar, chame `ToArray()`. O tipo serve bem para comparar cabeçalhos e protocolos que já falam em bytes.
