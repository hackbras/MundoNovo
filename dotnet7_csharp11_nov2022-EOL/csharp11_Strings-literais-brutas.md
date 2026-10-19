# Strings literais brutas

Uma string entre três aspas guarda o texto como foi escrito, inclusive quebras de linha e aspas.

## Antes

```csharp
string json = "{\n  \"nome\": \"Ana\"\n}";
```

Cada aspa e cada quebra de linha precisava de uma barra invertida.

## Depois

```csharp
string json = """
    {
      "nome": "Ana"
    }
    """;
```

## O que observar

O fechamento `"""` marca até onde o recuo é ignorado. O texto fica alinhado com essa coluna, então os espaços à esquerda da chave somem do valor. Aspas simples dentro do bloco não precisam de `\`. Para incluir `{` numa interpolação, escreva `{{`.
