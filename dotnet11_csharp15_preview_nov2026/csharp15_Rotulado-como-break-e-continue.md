# break e continue rotulados

No C# 15, ainda em preview, `break` e `continue` podem citar o nome do laço de fora e pular direto para ele.

## Antes

```csharp
bool achou = false;

for (int linha = 0; linha < 3; linha++)
{
    for (int coluna = 0; coluna < 3; coluna++)
    {
        if (grade[linha, coluna] == 9)
        {
            achou = true;
            break;
        }
    }

    if (achou)
    {
        break;
    }
}
```

O `break` de dentro só saía do `for` da coluna. A bandeira `achou` repetia a saída no `for` da linha.

## Depois

```csharp
externo: for (int linha = 0; linha < 3; linha++)
{
    for (int coluna = 0; coluna < 3; coluna++)
    {
        if (grade[linha, coluna] == 9)
        {
            break externo;
        }
    }
}
```

## O que observar

O rótulo `externo:` fica colado no `for` que ele nomeia. `break externo` encerra esse `for`, os dois níveis de uma vez. `continue externo` iria para a próxima linha, sem terminar o laço de fora. Sem rótulo, `break` e `continue` seguem valendo só para o laço mais interno. A sintaxe pode mudar até o C# 15 sair do preview.
