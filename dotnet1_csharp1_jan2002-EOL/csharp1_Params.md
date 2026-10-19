# params

`params` deixa quem chama passar vários valores soltos. Dentro do método eles chegam como array.

## Antes

```csharp
void Registrar(string[] nomes)
{
    Console.WriteLine(nomes.Length);
}

Registrar(new string[] { "Ana", "Bia" });
```

## Depois

```csharp
void Registrar(params string[] nomes)
{
    Console.WriteLine(nomes.Length);
}

Registrar("Ana", "Bia");
```

## O que observar

`params` é o último parâmetro do método. A chamada pode ter zero textos, um, ou vários. Com zero, o array chega vazio. Dentro do método, `nomes` é um `string[]` comum, com `Length` e índice.
