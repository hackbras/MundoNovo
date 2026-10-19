# Classes estáticas

`static` numa classe impede `new` e herança. A classe vira um agrupador de métodos e dados estáticos.

## Antes

```csharp
public class Calculos
{
    private Calculos() { }

    public static int Dobrar(int valor)
    {
        return valor * 2;
    }
}
```

O construtor privado era o jeito manual de bloquear o `new`.

## Depois

```csharp
public static class Calculos
{
    public static int Dobrar(int valor)
    {
        return valor * 2;
    }
}

int total = Calculos.Dobrar(4);
```

## O que observar

Tudo dentro de uma classe estática também é `static`. `new Calculos()` não compila, e outra classe não pode herdar dela. Serve para funções soltas que não precisam de um objeto, como uma classe de cálculo.
