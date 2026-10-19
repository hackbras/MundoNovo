# Modificadores em parâmetros lambda simples

Um parâmetro de lambda pode ter `out`, `ref` ou `in` sem repetir o tipo, quando esse tipo já é conhecido.

## Antes

```csharp
delegate bool Conversor(string texto, out int numero);

Conversor converter = (string texto, out int numero) => int.TryParse(texto, out numero);
```

Os modificadores `out` e `ref` exigiam o tipo escrito ao lado do nome.

## Depois

```csharp
delegate bool Conversor(string texto, out int numero);

Conversor converter = (texto, out numero) => int.TryParse(texto, out numero);

bool ok = converter("42", out int valor);
```

## O que observar

`texto` e `numero` recebem os tipos do delegate `Conversor`. `out numero` continua obrigando a lambda a atribuir `numero` antes de terminar. O mesmo vale para `ref` e `in` quando o delegate declara esses modificadores.
