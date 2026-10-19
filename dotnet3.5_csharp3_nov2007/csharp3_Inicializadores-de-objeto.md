# Inicializadores de objeto

O inicializador preenche propriedades na mesma expressão do `new`, entre chaves.

## Antes

```csharp
Pessoa pessoa = new Pessoa();
pessoa.Nome = "Ana";
pessoa.Idade = 20;
```

## Depois

```csharp
Pessoa pessoa = new Pessoa
{
    Nome = "Ana",
    Idade = 20
};
```

## O que observar

O compilador chama o construtor primeiro e depois atribui `Nome` e `Idade`. As propriedades precisam de `set` visível nesse ponto do código. Dá para escolher outro construtor: `new Pessoa("Ana") { Idade = 20 }`.
