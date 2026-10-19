# Declaração using

`using` sem chaves declara a variável e a descarta no fim do bloco em que ela nasceu.

## Antes

```csharp
string linha;
using (var leitor = new StreamReader(caminho))
{
    linha = leitor.ReadLine();
}
```

O `Dispose` do leitor acontece na chave que fecha o `using`.

## Depois

```csharp
using var leitor = new StreamReader(caminho);
string linha = leitor.ReadLine();
```

## O que observar

`leitor.Dispose()` roda no fim do método, ou no fim do bloco `{ }` onde a variável foi declarada. A variável fica visível nesse bloco inteiro, então duas com o mesmo nome não compilam. Se o arquivo precisar fechar antes do fim do método, o `using` com chaves continua sendo o caminho.
