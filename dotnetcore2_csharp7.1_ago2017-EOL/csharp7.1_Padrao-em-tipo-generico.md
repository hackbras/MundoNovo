# Padrão em tipo genérico

`is` com o tipo e a variável passa a funcionar quando o valor é um parâmetro genérico.

## Antes

```csharp
void Imprimir<T>(T valor)
{
    if (valor is int)
        Console.WriteLine((int)(object)valor);
}
```

No C# 7.0, `valor is int numero` não compilava se `valor` fosse `T`.

## Depois

```csharp
void Imprimir<T>(T valor)
{
    if (valor is int numero)
        Console.WriteLine(numero);
}
```

## O que observar

`numero` só existe dentro do `if`, e já é `int`. O teste falha quando `T` não for um `int` naquela chamada. O mesmo vale para outros tipos: `valor is string texto`.
