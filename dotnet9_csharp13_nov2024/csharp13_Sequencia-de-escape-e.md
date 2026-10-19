# Sequência de escape \e

`\e` é o caractere ESC, o mesmo que antes se escrevia com o código `\u001b`.

## Antes

```csharp
string vermelho = "\u001b[31mErro\u001b[0m";
```

## Depois

```csharp
string vermelho = "\e[31mErro\e[0m";
```

## O que observar

`\e` e `\u001b` são o mesmo caractere. No terminal, `\e[31m` pede a cor vermelha e `\e[0m` volta à cor normal. O atalho existe para esse uso, comum em texto colorido de console.
