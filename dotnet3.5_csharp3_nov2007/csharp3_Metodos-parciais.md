# Métodos parciais

Um método `partial` é um gancho. Uma parte da classe declara. A outra parte pode escrever o corpo. Se ninguém escrever, a chamada some.

## Antes

```csharp
public class Pessoa
{
    public void Salvar()
    {
        AoSalvar(); // este método tinha que existir, senão não compilava
    }
}
```

## Depois

```csharp
public partial class Pessoa
{
    partial void AoSalvar();

    public void Salvar()
    {
        AoSalvar();
    }
}

public partial class Pessoa
{
    partial void AoSalvar()
    {
        Console.WriteLine("salvou");
    }
}
```

## O que observar

Sem a segunda parte, o programa compila e `Salvar` não chama nada. No C# 3 esse método é privado, `void`, e não leva `out`. Código gerado usa isso para um ponto opcional no seu arquivo. No C# 9 o método parcial também pode ser público e ter retorno; nesse caso as duas partes são obrigatórias.
