# nameof

`nameof` pega o nome de uma variável, um tipo ou um membro como texto. Se o nome mudar, o texto muda junto.

## Antes

```csharp
if (string.IsNullOrEmpty(nome))
    throw new ArgumentException("nome");
```

O `"nome"` é um texto solto. Renomear a variável não atualiza a mensagem.

## Depois

```csharp
if (string.IsNullOrEmpty(nome))
    throw new ArgumentException(nameof(nome));
```

## O que observar

`nameof(nome)` vale `"nome"`. `nameof` não executa a expressão, só lê o nome. `nameof(pessoa.Cidade)` vale `"Cidade"`, o último pedaço. Serve em log, exceção e `INotifyPropertyChanged`, onde o texto precisa ser o nome do membro.
