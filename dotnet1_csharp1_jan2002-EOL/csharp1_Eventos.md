# Eventos

`event` avisa outras partes do programa que algo aconteceu. Quem está de fora só pode se inscrever. Só a própria classe dispara o aviso.

## Antes

```csharp
public class Pedido
{
    public delegate void Avisar(string mensagem);
    public Avisar Pago;
}
```

Como `Pago` é público, outro código pode chamar `pedido.Pago("...")` ou apagar a lista com `pedido.Pago = null`.

## Depois

```csharp
public class Pedido
{
    public delegate void Avisar(string mensagem);
    public event Avisar Pago;

    public void Confirmar()
    {
        if (Pago != null)
            Pago("pedido pago");
    }
}

pedido.Pago += Mostrar;
```

## O que observar

`+=` inscreve um método e `-=` tira. A chamada `Pago("pedido pago")` só compila dentro de `Pedido`. Antes de chamar, a classe testa `null`, porque pode não haver ninguém inscrito. O `?.` para essa chamada chegou no C# 6.
