# Reproducible example / Exemplo reproduzível

This example uses fictional study notes. The expected output is illustrative; an agent may use different wording or choose a different set of relevant connections.

Este exemplo usa notas fictícias. O resultado esperado é ilustrativo; o agente pode escrever explicações diferentes ou escolher outro conjunto de conexões relevantes.

## Files / Arquivos

- `vault/Mockito.md`: target note before execution / nota original.
- `vault/JUnit.md`: related note about test execution / nota relacionada à execução de testes.
- `vault/Testes unitários.md`: related note about isolation / nota relacionada ao isolamento.
- `expected/Mockito.md`: illustrative result / resultado ilustrativo.

## Run / Executar

1. Make a copy of `vault/` and open that folder as a separate Obsidian vault. Configure Copilot in this test vault.
2. Register the command from `commands/connect-existing-note.md` using the main README instructions.
3. In Agent Chat, type `/`, choose the command, and send `Mockito`.
4. Inspect `Mockito.md` in Source mode.
5. Run the command again on the same note.

1. Faça uma cópia de `vault/` e abra essa pasta como um cofre separado no Obsidian. Configure o Copilot nesse cofre de teste.
2. Cadastre o comando de `commands/connect-existing-note.md` seguindo o README principal.
3. No Agent Chat, digite `/`, selecione o comando e envie `Mockito`.
4. Confira `Mockito.md` no modo fonte.
5. Execute novamente na mesma nota.

Do not open the entire repository as the test vault: the expected output and documentation would become search candidates.

Não abra o repositório inteiro como cofre de teste: o resultado esperado e a documentação poderiam influenciar a busca.

## Acceptance checks / Critérios de aceitação

- Only the original `Mockito.md` is edited by the command.
- Its existing explanation and code remain unchanged.
- Connections use literal `[[JUnit]]` and `[[Testes unitários]]`, if those destinations are selected.
- The explanations remain in Portuguese.
- A second run does not duplicate links or the section.
- Related note files remain unchanged.
- No additional note is created by the command. Copilot may independently save chat or configuration files according to its settings.

- O comando edita somente o arquivo original `Mockito.md`.
- A explicação e o código existentes permanecem intactos.
- As conexões usam `[[JUnit]]` e `[[Testes unitários]]` literais, se esses destinos forem selecionados.
- As explicações permanecem em português.
- A segunda execução não duplica links nem a seção.
- As notas relacionadas permanecem intactas.
- O comando não cria novas notas. O Copilot pode salvar conversas ou arquivos de configuração por suas próprias opções.