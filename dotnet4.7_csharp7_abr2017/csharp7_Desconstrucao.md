# Desconstrução

A desconstrução reparte um objeto em variáveis. A classe explica a ordem num método `Deconstruct`.

## Antes

```csharp
string nome = pessoa.Nome;
int idade = pessoa.Idade;
```

## Depois

```csharp
public class Pessoa
{
    public string Nome { get; set; }
    public int Idade { get; set; }

    public void Deconstruct(out string nome, out int idade)
    {
        nome = Nome;
        idade = Idade;
    }
}

(string nome, int idade) = pessoa;
```

## O que observar

A ordem dos `out` é a ordem das variáveis. Uma tupla também desconstrói, sem método extra: `(string nome, int idade) = Montar(pessoa)`. Se um dos valores não interessa, o descarte `_` ocupa o lugar.
