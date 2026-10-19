# Operadores de atribuição composta definidos pelo usuário

Você pode escrever `+=` (e os outros `op=`) como uma operação própria, que altera o objeto no lugar.

## Antes

```csharp
public class Conta
{
    public int Saldo { get; private set; }

    public static Conta operator +(Conta conta, int valor) =>
        new Conta { Saldo = conta.Saldo + valor };
}

conta = conta + 10;
```

`conta += 10` faria `conta = conta + 10` e trocaria o objeto por outro.

## Depois

```csharp
public class Conta
{
    public int Saldo { get; private set; }

    public void operator +=(int valor) => Saldo += valor;
}

conta += 10;
```

## O que observar

`conta += 10` chama o operador e soma no `Saldo` da mesma instância. Não nasce outra `Conta`. O operador de atribuição composta é um método de instância e devolve `void`. Os demais seguem o mesmo desenho: `-=`, `*=` e os outros `op=`.
