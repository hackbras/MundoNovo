# Segurança de memória

No C# 15, ainda em preview, criar um ponteiro e fixar um array podem ficar fora de `unsafe`. Ler o valor apontado continua dentro de `unsafe`.

## Antes

```csharp
unsafe
{
    int numero = 42;
    int* ponteiro = &numero;
    int valor = *ponteiro;
}
```

O bloco inteiro era `unsafe`, inclusive a parte que só guardava o endereço.

## Depois

```csharp
int numero = 42;
int* ponteiro = &numero;

int valor = unsafe(*ponteiro);
```

## O que observar

`&numero` obtém o endereço e, no preview, não pede `unsafe`. `*ponteiro` lê a memória e continua perigoso: a expressão `unsafe(...)` marca só essa leitura. O mesmo vale para `ponteiro->Campo` e `ponteiro[i]`. O projeto precisa de `<AllowUnsafeBlocks>true</AllowUnsafeBlocks>` e de `LangVersion` em `preview`. A regra pode mudar até o C# 15 sair do preview.
