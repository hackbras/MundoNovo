# Tipos locais de arquivo

O modificador `file` esconde a classe: só o arquivo em que ela foi escrita consegue usá-la.

## Antes

```csharp
internal class AjudaDoCalculo
{
    public static int Dobro(int n) => n * 2;
}
```

`internal` ainda deixa qualquer outro arquivo do mesmo projeto enxergar a classe.

## Depois

```csharp
file class AjudaDoCalculo
{
    public static int Dobro(int n) => n * 2;
}

int resultado = AjudaDoCalculo.Dobro(4);
```

## O que observar

Outro arquivo do mesmo projeto que citar `AjudaDoCalculo` não compila. Dois arquivos podem ter um tipo `file` com o mesmo nome, porque um não vê o outro. Serve para um detalhe de implementação que não deve vazar para o resto do projeto.
