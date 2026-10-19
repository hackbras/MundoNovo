# Métodos parciais com retorno

O método `partial` pode ser público e devolver valor. Quando ele tem retorno, uma parte declara e a outra é obrigada a ter o corpo.

## Antes

```csharp
public partial class Pessoa
{
    partial void AoSalvar();
}
```

No C# 3 o método parcial era privado, `void`, e a parte com o corpo era opcional.

## Depois

```csharp
public partial class Pessoa
{
    public partial string Formatar(string nome);
}

public partial class Pessoa
{
    public partial string Formatar(string nome) => nome.Trim();
}
```

## O que observar

As duas partes precisam existir, porque alguém pode chamar `Formatar` e usar o texto devolvido. A assinatura é igual nos dois arquivos: mesmo nome, mesmos parâmetros e mesmo tipo de retorno. Geradores de código usam isso para entregar um método que o outro arquivo completa. O gancho antigo, privado e `void`, continua opcional.
