# Acesso diferente em get e set

O `get` e o `set` de uma propriedade podem ter acessos diferentes. O caso comum é todo mundo ler e só a própria classe gravar.

## Antes

```csharp
public class Produto
{
    public int Id;

    public void DefinirId(int id)
    {
        Id = id;
    }
}
```

`Id` público deixa qualquer código gravar por cima.

## Depois

```csharp
public class Produto
{
    private int _id;

    public int Id
    {
        get { return _id; }
        private set { _id = value; }
    }
}
```

## O que observar

Quem está fora lê `produto.Id` e não consegue atribuir. O `set` privado só a própria classe usa. O acesso do `get` ou do `set` precisa ser mais fechado que o da propriedade, nunca mais aberto. No C# 3 a forma curta desse exemplo é `public int Id { get; private set; }`.
