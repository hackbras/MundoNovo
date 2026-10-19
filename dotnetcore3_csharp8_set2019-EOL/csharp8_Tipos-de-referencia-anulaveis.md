# Tipos de referência anuláveis

`string` e as outras classes passam a ter `?` para dizer se `null` é esperado. O compilador avisa quando o uso não combina com essa marca.

## Antes

```csharp
string nome = null;
int letras = nome.Length; // estoura na execução
```

O compilador aceitava `null` em qualquer `string`.

## Depois

```csharp
#nullable enable

string nome = null; // aviso: não pode ser nulo
string? apelido = null;
int letras = nome.Length;
```

## O que observar

Isso é aviso do compilador. O programa ainda roda, e `string` e `string?` são o mesmo tipo na execução. `int?` já existia desde o C# 2 e continua sendo outro tipo, `Nullable<int>`. Ligue a verificação no projeto com `<Nullable>enable</Nullable>`. `nome!` diz ao compilador para confiar que não é nulo. Não é uma checagem na execução.
