# Retornos covariantes

O `override` pode devolver um tipo mais específico que o da classe base. Quem já sabe que tem um `Cachorro` recebe um `Cachorro`, sem converter.

## Antes

```csharp
public class Animal
{
    public virtual Animal Reproduzir() => new Animal();
}

public class Cachorro : Animal
{
    public override Animal Reproduzir() => new Cachorro();
}

Animal filhote = new Cachorro().Reproduzir();
```

O retorno era `Animal` mesmo quando o objeto era um `Cachorro`.

## Depois

```csharp
public class Animal
{
    public virtual Animal Reproduzir() => new Animal();
}

public class Cachorro : Animal
{
    public override Cachorro Reproduzir() => new Cachorro();
}

Cachorro filhote = new Cachorro().Reproduzir();
```

## O que observar

`Reproduzir` no `Cachorro` devolve `Cachorro`. Os parâmetros continuam iguais aos do método base. O tipo novo precisa ser a própria classe ou uma filha dela. Pela variável `Animal`, o resultado ainda é visto como `Animal`.
