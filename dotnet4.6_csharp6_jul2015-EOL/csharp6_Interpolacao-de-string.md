# Interpolação de string

Uma string com `$` embute valores no texto. A expressão fica entre chaves, no lugar em que o valor aparece.

## Antes

```csharp
string texto = string.Format("Produto {0} custa {1}", nome, preco);
```

## Depois

```csharp
string texto = $"Produto {nome} custa {preco}";
```

## O que observar

`nome` e `preco` são lidos na hora de montar o texto. Uma chave de verdade no texto se escreve dobrada: `$"{{ok}}"`. O formato de número cabe dentro da chave, como `{preco:0.00}`. Por baixo, o compilador monta a string com os valores, no mesmo espírito do `string.Format`.
