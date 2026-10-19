# Atributos

Um atributo é uma marca entre colchetes em cima de uma classe, um método ou um campo. O compilador e outras ferramentas leem essa marca.

## Antes

```csharp
// não use mais este método; chame SalvarPedido
public void Salvar()
{
}
```

O comentário não avisa quem ainda chama `Salvar`.

## Depois

```csharp
[Obsolete("Use SalvarPedido")]
public void Salvar()
{
}
```

## O que observar

`[Obsolete]` faz o compilador avisar em cada chamada de `Salvar`. Um atributo é uma classe que herda de `Attribute`. O nome da classe pode terminar com `Attribute`, e na marca dá para omitir esse sufixo: a classe `ObsoleteAttribute` se escreve `[Obsolete]`.
