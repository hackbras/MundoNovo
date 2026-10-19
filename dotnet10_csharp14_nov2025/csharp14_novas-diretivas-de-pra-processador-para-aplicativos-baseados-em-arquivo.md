# Diretivas de pré-processador para aplicativos baseados em arquivo

Um único arquivo `.cs` pode dizer qual SDK e quais pacotes usar, sem um `.csproj` ao lado.

## Antes

```xml
<Project Sdk="Microsoft.NET.Sdk">
  <ItemGroup>
    <PackageReference Include="Humanizer" Version="2.14.1" />
  </ItemGroup>
</Project>
```

O programa menor ainda precisava de uma pasta de projeto para referenciar um pacote.

## Depois

```csharp
#:sdk Microsoft.NET.Sdk
#:package Humanizer@2.14.1

Console.WriteLine("pronto");
```

## O que observar

As linhas `#:` ficam no topo do arquivo. `#:sdk` escolhe o SDK. `#:package` traz um pacote NuGet, com o nome e a versão separados por `@`. Você executa com `dotnet run arquivo.cs`. Um projeto com `.csproj` continua sendo o lugar de uma aplicação com vários arquivos.
