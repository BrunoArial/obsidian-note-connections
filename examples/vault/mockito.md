# Mockito

Mockito é uma biblioteca usada para criar objetos simulados em testes Java.

Um mock pode substituir uma dependência da classe testada. Isso permite controlar as respostas dessa dependência e verificar interações sem executar sua implementação real.

## Exemplo

```java
ProdutoRepository repository = mock(ProdutoRepository.class);
when(repository.existsById(1L)).thenReturn(true);
```

Esse trecho define que a chamada `existsById(1L)` no mock retorna `true`. Ele não consulta um banco de dados.