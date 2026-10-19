# Eventos e construtores partial

Construtor e evento podem ser `partial`: uma parte da classe declara, a outra implementa.

## Antes

```csharp
public class Pedido
{
    public Pedido()
    {
        Itens = new List<string>();
    }

    public List<string> Itens { get; }

    public event EventHandler? Pronto;
}
```

Construtor e evento ficavam inteiros numa parte só da classe.

## Depois

```csharp
public partial class Pedido
{
    public partial Pedido();

    public partial event EventHandler? Pronto;
}

public partial class Pedido
{
    public partial Pedido()
    {
        Itens = new List<string>();
    }

    public List<string> Itens { get; private set; } = new();

    public partial event EventHandler? Pronto
    {
        add { }
        remove { }
    }
}
```

## O que observar

A primeira parte anuncia o construtor e o evento. A segunda parte escreve o corpo e os acessores `add`/`remove`. As duas partes precisam ser a mesma classe `partial`. Um gerador pode implementar o evento sem ocupar o arquivo em que você declara o tipo.
