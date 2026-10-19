# Atributos genéricos

A classe do atributo pode ter um parâmetro de tipo, no lugar de receber um `typeof(...)`.

## Antes

```csharp
[Validador(typeof(Cliente))]
public class Pedido
{
}

public class ValidadorAttribute : Attribute
{
    public ValidadorAttribute(Type tipo) { }
}
```

## Depois

```csharp
[Validador<Cliente>]
public class Pedido
{
}

public class ValidadorAttribute<T> : Attribute
{
}
```

## O que observar

`T` é `Cliente` porque o atributo foi escrito como `Validador<Cliente>`. O compilador conhece esse tipo. Um atributo genérico não pode ser herdado por outra classe de atributo. O uso no dia a dia é marcar código com um tipo, sem a caixa `typeof`.
