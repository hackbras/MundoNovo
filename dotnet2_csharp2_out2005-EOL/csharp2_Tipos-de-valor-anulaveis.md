# Tipos de valor anuláveis

`int`, `bool` e outros `struct` passaram a poder ficar sem valor. O `?` depois do tipo guarda um valor ou `null`.

## Antes

```csharp
int idade = -1; // -1 queria dizer "não informado"
```

O `-1` é um número de verdade. Qualquer conta usa ele como idade.

## Depois

```csharp
int? idade = null;

if (idade.HasValue)
{
    Console.WriteLine(idade.Value);
}
```

## O que observar

`int?` é o mesmo que `Nullable<int>`. `HasValue` diz se há número. `Value` entrega o número, e estoura se estiver vazio. `idade.Value` só depois do `if`. O operador `??`, do arquivo ao lado, escolhe outro valor quando o `?` está vazio.
