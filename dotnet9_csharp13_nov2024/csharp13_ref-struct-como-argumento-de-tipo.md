# ref struct como argumento de tipo

Um `ref struct`, como `Span<T>`, pode ser o tipo passado para um método genérico quando o parâmetro autoriza isso.

## Antes

```csharp
void Imprimir<T>(T valor)
{
    Console.WriteLine(valor);
}

ReadOnlySpan<char> nome = "Ana";
// Imprimir(nome); não compilava: Span não podia ser T
```

## Depois

```csharp
void Imprimir<T>(T valor) where T : allows ref struct
{
    Console.WriteLine(valor.ToString());
}

ReadOnlySpan<char> nome = "Ana";
Imprimir(nome);
```

## O que observar

`allows ref struct` avisa que `T` pode ser um `Span` ou outro `ref struct`. Sem essa cláusula, o compilador recusa. Um `ref struct` não pode ir para o heap: o método não pode guardá-lo num campo de classe nem numa lista.
