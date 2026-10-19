# Descartes

`_` ocupa um lugar cujo valor não vai ser usado. O compilador não cria variável com esse nome.

## Antes

```csharp
int ignorado;
if (int.TryParse(texto, out ignorado))
{
    Console.WriteLine("é número");
}
```

`ignorado` existe só para o `out` ter onde gravar.

## Depois

```csharp
if (int.TryParse(texto, out _))
{
    Console.WriteLine("é número");
}
```

## O que observar

O `TryParse` ainda grava o número, e o programa ignora. Na desconstrução, `(string nome, _) = pessoa` fica com o nome e descarta a idade. Dá para repetir `_` várias vezes na mesma linha. Uma variável chamada `_` de verdade, com tipo na frente, é outra coisa: aí ela existe.
