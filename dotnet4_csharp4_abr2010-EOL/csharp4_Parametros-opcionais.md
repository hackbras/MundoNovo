# Parâmetros opcionais

Um parâmetro opcional já nasce com um valor. Quem chama pode omitir esse argumento.

## Antes

```csharp
void Enviar(string texto)
{
    Enviar(texto, false);
}

void Enviar(string texto, bool urgente)
{
}
```

Cada combinação pedia um método a mais.

## Depois

```csharp
void Enviar(string texto, bool urgente = false)
{
}

Enviar("Olá");
Enviar("Olá", true);
```

## O que observar

Os parâmetros opcionais ficam no fim da lista. O valor padrão precisa ser constante: número, texto, `true`, `false` ou `null`. Quem já compilou contra esse método guarda o valor padrão na chamada. Se você mudar o `false` para `true` depois, os programas antigos continuam com `false` até serem compilados de novo.
