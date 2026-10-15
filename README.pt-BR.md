# Obsidian Note Connections

[English](README.md)

Um comando reutilizável para o Copilot for Obsidian que encontra conexões relevantes entre uma nota existente e outras notas do cofre e acrescenta `[[wikilinks]]` verificados à própria nota.

Você indica a nota; o agente pesquisa, verifica as candidatas, atualiza a seção de conexões e relê o arquivo para conferir a alteração.

Este projeto distribui um comando personalizado, não um plugin do Obsidian nem uma Agent Skill. Ele utiliza o Agent Chat do Copilot e as ferramentas de acesso ao cofre do agente selecionado.

## Requisitos

- Obsidian no computador.
- [Copilot for Obsidian](https://github.com/logancyang/obsidian-copilot), configurado com um agente capaz de pesquisar, ler e editar arquivos do cofre.
- Acesso a um modelo pelo agente escolhido. Custos e limites dependem da configuração.
- Permissão para o agente editar a nota indicada.

O fluxo foi pensado para o **Agent Chat**. Não presuma que o Quick Chat ou um comando pelo editor possui as mesmas ferramentas de edição.

## Configuração

1. Instale e ative o Copilot pelos plugins da comunidade do Obsidian.
2. Configure seu agente e confira se ele consegue ler e editar uma nota de teste.
3. Abra **Settings → Copilot → Command → Add Cmd**.
4. Defina o nome como **Connect existing note**, ou **Conectar nota existente**.
5. Copie o conteúdo do [arquivo do comando](commands/connect-existing-note.md) para o campo Prompt.
6. Ative **Show in slash menu** e salve.

Os nomes das opções podem variar entre versões. Consulte o [guia de configuração](https://docs.obsidiancopilot.com/getting-started/) e a [documentação de comandos](https://docs.obsidiancopilot.com/custom-commands/).

## Uso

No Agent Chat, digite `/`, selecione o comando e informe o título ou a referência da nota:

```text
Mockito
```

O comando edita a nota por padrão. Não é necessário pedir para salvar novamente. As permissões do agente ainda podem exigir aprovação.

Exemplo de conteúdo acrescentado:

```markdown
## Conexões com outras notas

- [[JUnit]] — Executa os testes nos quais o Mockito substitui dependências.
```

As explicações e o título de uma nova seção seguem o idioma da nota; títulos e caminhos dos arquivos permanecem inalterados. Se a seção já existir, o comando a atualiza sem duplicar links e preserva as conexões válidas. O conteúdo fora dessa seção permanece intacto.

O comando não cria notas, não altera as notas relacionadas e não acrescenta links recíprocos. Se não encontrar conexões relevantes, preserva a nota original.

## Exemplo

Veja o [exemplo reproduzível](examples/README.md). Utilize somente `examples/vault/` como cofre de teste; mantenha o resultado esperado fora dele.

## Estado da validação

O autor relatou testes do comando anterior em português em várias notas pessoais, incluindo atualização de uma seção existente sem duplicar links. O resultado observado incluiu edição da nota original e gravação de wikilinks literais.

**O comando em inglês distribuído aqui ainda não foi testado no Obsidian.** O exemplo incluído é ilustrativo, não uma saída registrada do agente.

| Ambiente | Informação registrada |
| --- | --- |
| Versão do Obsidian | Não informada |
| Versão do Copilot | Não informada |
| Agente e modelo | Não informados |
| Comando exato em inglês | Validação pendente |

Antes de apresentar a tradução como validada, registre o ambiente e confira: novas conexões, execução repetida sem duplicações, preservação do conteúdo, ausência de candidatas relevantes e títulos ambíguos.

## Limitações

- A qualidade das conexões e a cobertura da busca dependem do modelo, das ferramentas e do conteúdo das notas. O comando não garante todas as conexões possíveis.
- Algumas notas relevantes podem não ser encontradas; relações fracas podem ser sugeridas. Revise as alterações.
- Uma instrução não concede acesso aos arquivos nem ignora permissões do agente.
- Conversas do ChatGPT não são importadas automaticamente. Este comando analisa notas existentes no cofre.
- Conforme o provedor escolhido, conteúdo necessário das notas pode ser enviado a um serviço externo.

## Ocultar arquivos do Copilot no gráfico

Em **Filtros → Buscar arquivos** do gráfico, exclua o caminho real da pasta do Copilot. Para uma pasta chamada `copilot`:

```text
-path:"copilot/"
```

Se as pastas estiverem separadas, adapte o filtro:

```text
-path:"copilot-conversations/" -path:"copilot-custom-prompts/"
```

Isso altera a visualização do gráfico, não o armazenamento nem o acesso do agente.

## Licença

[MIT](LICENSE).