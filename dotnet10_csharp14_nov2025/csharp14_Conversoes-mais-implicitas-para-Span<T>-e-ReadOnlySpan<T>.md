# Conversões mais implícitas para Span e ReadOnlySpan

Um array pode ir direto para um `Span<T>`, sem chamar `AsSpan()`.

## Antes

```csharp
int[] numeros = { 1, 2, 3 };
Span<int> trecho = numeros.AsSpan();
```

## Depois

```csharp
int[] numeros = [1, 2, 3];
Span<int> trecho = numeros;
ReadOnlySpan<int> leitura = numeros;
```

## O que observar

O compilador converte o array no `Span` que aponta para os mesmos elementos. Alterar `trecho[0]` altera `numeros[0]`. `ReadOnlySpan<int>` permite ler e impede gravar. O `Span` não pode ser guardado num campo de classe: ele só vive enquanto o método está executando.
