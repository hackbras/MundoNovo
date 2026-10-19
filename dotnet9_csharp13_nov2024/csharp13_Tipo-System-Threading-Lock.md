# Tipo System.Threading.Lock

`lock` pode usar o tipo `Lock`, feito para esse papel, em vez de um `object` qualquer.

## Antes

```csharp
object cadeado = new();

lock (cadeado)
{
    saldo += 10;
}
```

Qualquer objeto servia de cadeado, inclusive um que já tinha outro uso.

## Depois

```csharp
using System.Threading;

Lock cadeado = new();

lock (cadeado)
{
    saldo += 10;
}
```

## O que observar

`Lock` existe para sincronizar código. O `lock` em cima dele usa a API dessa classe. O bloco continua igual: uma thread entra, as outras esperam. Declare o cadeado como campo `readonly` da classe que guarda o recurso compartilhado.
