# Parâmetros ref e out

`ref` e `out` deixam o método alterar a variável de quem chamou. Sem eles, o método recebe uma cópia do número.

## Antes

```csharp
int SomarUm(int valor)
{
    return valor + 1;
}

int qtd = 1;
qtd = SomarUm(qtd);
```

## Depois

```csharp
void SomarUm(ref int valor)
{
    valor = valor + 1;
}

int qtd = 1;
SomarUm(ref qtd); // qtd vale 2
```

## O que observar

`ref` exige que `qtd` já tenha um valor antes da chamada, e a chamada também escreve `ref`. `out` é o outro lado: o método é obrigado a atribuir, e quem chama não precisa inicializar. O uso típico é `TryParse`, em que o método devolve `true` ou `false` e preenche o número pelo `out`.
