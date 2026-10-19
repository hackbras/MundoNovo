# Argumentos nomeados no meio

Um argumento nomeado pode ficar no meio da chamada. Os argumentos seguintes podem ir sem nome, se cada um estiver na posição certa do parâmetro.

## Antes

```csharp
void Enviar(string destino, bool urgente, string assunto)
{
}

Enviar("ana@email.com", urgente: true, assunto: "Pedido");
```

Depois de `urgente:`, o C# 4 exigia nome em todo o resto.

## Depois

```csharp
void Enviar(string destino, bool urgente, string assunto)
{
}

Enviar("ana@email.com", urgente: true, "Pedido");
```

## O que observar

`true` está na segunda posição, que é `urgente`, e `"Pedido"` está na terceira, que é `assunto`. Por isso a chamada compila. Nome fora de ordem seguido de valor sem nome continua erro: `Enviar(assunto: "Pedido", "ana@email.com", true)` não compila. O nome no meio serve para um `bool` ou um `null` não ficar sem significado.
