# Tipos de união

No C# 15, ainda em preview, `union` declara um valor que é exatamente um dos tipos listados. O `switch` precisa tratar cada um.

## Antes

```csharp
object animal = new Cachorro("Rex");

string nome = animal switch
{
    Cachorro c => c.Nome,
    Gato g => g.Nome,
    _ => "outro"
};
```

`object` aceita qualquer coisa. O `_` cobria um tipo que não era cachorro nem gato.

## Depois

```csharp
public record Gato(string Nome);
public record Cachorro(string Nome);
public record Passaro(string Nome);

public union Animal(Gato, Cachorro, Passaro);

Animal animal = new Cachorro("Rex");

string nome = animal switch
{
    Cachorro c => c.Nome,
    Gato g => g.Nome,
    Passaro p => p.Nome
};
```

## O que observar

`Animal` só guarda um `Gato`, um `Cachorro` ou um `Passaro`. Atribuir `new Cachorro("Rex")` converte sozinho para `Animal`. Tirar um braço do `switch` é erro de compilação, porque faltou um caso. Os três records não precisam herdar um do outro. A sintaxe pode mudar até o C# 15 sair do preview.
