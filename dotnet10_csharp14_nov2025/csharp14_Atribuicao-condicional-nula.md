# Atribuição condicional nula

O `?.` pode ficar do lado esquerdo de uma atribuição. A propriedade só é gravada quando o objeto existe.

## Antes

```csharp
if (cliente is not null)
{
    cliente.Cidade = "Recife";
}
```

## Depois

```csharp
cliente?.Cidade = "Recife";
```

## O que observar

Se `cliente` for nulo, a linha não faz nada e `"Recife"` nem é calculado quando o lado direito é uma chamada. Se `cliente` existir, `Cidade` recebe o valor. O `?.` na atribuição lê o objeto uma vez só, o que importa quando a expressão da esquerda tem um efeito, como um método que devolve o cliente.
