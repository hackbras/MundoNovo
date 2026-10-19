# Linguagem padrão do .NET Framework

O .NET Framework 4.8 é a última versão do .NET Framework. A linguagem padrão dele é o C# 7.3. Ele não trouxe sintaxe nova.

## Antes

```xml
<!-- um projeto antigo podia ficar preso numa linguagem anterior -->
<LangVersion>6</LangVersion>
```

## Depois

```xml
<!-- no 4.8 o padrão já é 7.3; esta linha só deixa a escolha explícita -->
<LangVersion>7.3</LangVersion>
```

## O que observar

Com a linguagem 7.3 dá para usar tuplas, `out` na declaração, funções locais, padrões e o restante do C# 7.0 até o 7.3. Os arquivos desses recursos estão nas pastas `dotnet4.7_csharp7_abr2017`, `dotnetcore2_csharp7.1_ago2017-EOL` e `dotnetcore2.1_csharp7.3_mai2018-EOL`. O C# 8 não é a linguagem do 4.8. Ele chegou no .NET Core 3. O 4.8.1, de agosto de 2022, continua no C# 7.3 como padrão.
