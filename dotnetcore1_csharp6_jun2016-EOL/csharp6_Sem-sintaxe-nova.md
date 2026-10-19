# Sem sintaxe nova

O .NET Core 1.0 usa o C# 6, a mesma linguagem do .NET Framework 4.6. Esta versão não trouxe comando novo.

## Antes

```csharp
// .NET Framework 4.6
string cidade = cliente?.Endereco?.Cidade ?? "sem cidade";
```

## Depois

```csharp
// .NET Core 1.0, o mesmo C# 6
string cidade = cliente?.Endereco?.Cidade ?? "sem cidade";
```

## O que observar

O que mudou foi o lugar onde o programa roda: o Core 1 é multiplataforma e se publica com a ferramenta `dotnet`. Interpolação, `?.`, `nameof` e os outros recursos do C# 6 estão na pasta `dotnet4.6_csharp6_jul2015-EOL`. O .NET Core 1.1, de novembro de 2016, também ficou no C# 6.
