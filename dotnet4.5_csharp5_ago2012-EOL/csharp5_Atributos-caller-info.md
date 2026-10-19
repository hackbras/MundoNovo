# Atributos Caller Info

O compilador preenche o nome de quem chamou, o arquivo e a linha. O parâmetro precisa ter um valor padrão.

## Antes

```csharp
void Log(string mensagem, string metodo)
{
    Console.WriteLine(metodo + ": " + mensagem);
}

void Salvar()
{
    Log("gravou", "Salvar");
}
```

O texto `"Salvar"` era escrito à mão e ficava velho quando o método mudava de nome.

## Depois

```csharp
using System.Runtime.CompilerServices;

void Log(string mensagem, [CallerMemberName] string metodo = "")
{
    Console.WriteLine(metodo + ": " + mensagem);
}

void Salvar()
{
    Log("gravou"); // metodo vale "Salvar"
}
```

## O que observar

A chamada não passa o nome. O compilador escreve `"Salvar"` por você. Também existem `[CallerFilePath]` e `[CallerLineNumber]`. O parâmetro com esses atributos fica no fim e tem valor padrão, senão deixa de ser opcional.
