# Testes unitários

Um teste unitário verifica uma unidade de comportamento de forma isolada e com resultado previsível.

Em uma classe de serviço, podemos substituir o repositório por um mock para testar a regra de negócio sem depender de um banco de dados real.

Esse isolamento ajuda a identificar se uma falha está no comportamento testado. O teste ainda precisa verificar resultados importantes, e não apenas reproduzir a implementação.