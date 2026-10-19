# Argumentos nomeados

O argumento nomeado diz qual parâmetro está recebendo o valor. A ordem da chamada pode seguir o sentido da leitura, não só a ordem da declaração.

## Antes

```csharp
void Enviar(string texto, bool urgente, bool copiarGerente)
{
}

Enviar("Olá", true, false);
```

Os dois `bool` ficam sem pista de qual é qual.

## Depois

```csharp
void Enviar(string texto, bool urgente, bool copiarGerente)
{
}

Enviar("Olá", urgente: true, copiarGerente: false);
```

## O que observar

O nome é o do parâmetro, com dois-pontos. Dá para mudar a ordem: `Enviar(copiarGerente: false, urgente: true, texto: "Olá")`. Até o C# 7.1, depois de um argumento nomeado os seguintes também precisavam de nome. No C# 7.2 um nome pode ficar no meio, se a posição estiver certa.
