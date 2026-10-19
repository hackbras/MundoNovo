# Membros padrão de interface

Uma interface pode trazer o corpo de um método. A classe que não implementar esse método usa o corpo da interface.

## Antes

```csharp
public interface ILog
{
    void Log(string texto);
    void LogAviso(string texto);
}
```

Toda classe era obrigada a escrever `Log` e `LogAviso`.

## Depois

```csharp
public interface ILog
{
    void Log(string texto);
    void LogAviso(string texto) => Log("Aviso: " + texto);
}
```

## O que observar

Uma classe pode implementar só `Log`. `LogAviso` já tem corpo. A chamada do método padrão é feita pela interface:

```csharp
ILog log = new ConsoleLog();
log.LogAviso("disco cheio");
```

`ConsoleLog` nesse exemplo é uma classe que só escreve `Log`. Na variável declarada como `ConsoleLog`, `LogAviso` só aparece se a classe também declarar esse método.
