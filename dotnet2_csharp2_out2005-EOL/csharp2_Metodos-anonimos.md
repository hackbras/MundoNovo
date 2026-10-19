# Métodos anônimos

Um método anônimo é um bloco de código passado na hora, sem declarar um método com nome.

## Antes

```csharp
delegate int Operacao(int valor);

int Dobrar(int valor)
{
    return valor * 2;
}

Operacao calcular = Dobrar;
```

## Depois

```csharp
delegate int Operacao(int valor);

Operacao calcular = delegate(int valor)
{
    return valor * 2;
};
```

## O que observar

`delegate (int valor) { ... }` cria o método no lugar da atribuição. Ele enxerga variáveis do método em volta. No C# 3 a lambda `valor => valor * 2` faz o mesmo papel e virou o jeito comum de escrever isso.
