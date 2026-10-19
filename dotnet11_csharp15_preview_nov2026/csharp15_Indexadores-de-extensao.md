# Indexadores de extensão

No C# 15, ainda em preview, um bloco `extension` pode criar um indexador para um tipo que não tinha colchetes.

## Antes

```csharp
IEnumerable<int> numeros = Enumerable.Range(1, 10);
int terceiro = numeros.ElementAt(2);
```

`IEnumerable<int>` não tem indexador. A posição pedia o método `ElementAt`.

## Depois

```csharp
public static class IndexadorDeSequencia
{
    extension(IEnumerable<int> sequencia)
    {
        public int this[int indice] => sequencia.ElementAt(indice);
    }
}

IEnumerable<int> numeros = Enumerable.Range(1, 10);
int terceiro = numeros[2];
```

## O que observar

`this[int indice]` é o indexador, escrito dentro de `extension`. `numeros[2]` chama esse indexador e devolve `3`, porque a sequência começa em 1. O parâmetro entre parênteses de `extension` é obrigatório: indexador é membro de instância. A sintaxe pode mudar até o C# 15 sair do preview.
