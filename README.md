# Obsidian Note Connections

[Português](README.pt-BR.md)

A reusable command for Copilot for Obsidian that finds relevant connections between an existing note and other vault notes, then adds verified `[[wikilinks]]` to the original note.

Provide the target note, and the agent searches, checks candidate notes, updates the connections section, and rereads the file to verify the change.

This project distributes a custom command, not an Obsidian plugin or an Agent Skill. It uses Copilot's Agent Chat and the selected agent's vault tools.

## Requirements

- Obsidian on desktop.
- [Copilot for Obsidian](https://github.com/logancyang/obsidian-copilot), configured with an agent that can search, read, and edit vault files.
- Access to a model through the selected agent. Provider costs and usage limits depend on your setup.
- Permission for the agent to edit the target note.

This workflow is intended for **Agent Chat**. Do not assume Quick Chat or an editor command has the same file-editing capabilities.

## Setup

1. Install and enable Copilot through Obsidian's Community plugins.
2. Configure your agent in Copilot and verify that it can read and edit a test note.
3. Open **Settings → Copilot → Command → Add Cmd**.
4. Set the name to **Connect existing note**.
5. Copy the contents of [the command file](commands/connect-existing-note.md) into the Prompt field.
6. Enable **Show in slash menu** and save.

Labels may differ between versions. See the official [setup guide](https://docs.obsidiancopilot.com/getting-started/) and [command documentation](https://docs.obsidiancopilot.com/custom-commands/).

## Usage

In Agent Chat, type `/`, select **Connect existing note**, then provide a note title or reference:

```text
Mockito
```

The command edits the target note by default. No additional request to save is needed. Agent permission settings may still require approval.

Example content added to the note:

```markdown
## Conexões com outras notas

- [[JUnit]] — Executes the tests in which Mockito replaces dependencies.
```

Explanations and a newly created section heading follow the target note's language; note titles and paths remain unchanged. If a connections section already exists, the command updates it without duplicating links and preserves valid existing connections. All content outside that section remains unchanged.

The command does not create notes, modify related notes, or add reciprocal links. If it finds no relevant connections, it leaves the target unchanged.

## Example

See [the reproducible example](examples/README.md). Use only `examples/vault/` as the test vault; keep the expected output outside it.

## Validation status

The author reported testing the Portuguese predecessor on multiple personal notes, including updating an existing connections section without duplicates. The observed result included editing the original note and saving literal wikilinks.

**The English command distributed here has not yet been tested in Obsidian.** The included example is illustrative, not recorded agent output.

| Environment | Recorded information |
| --- | --- |
| Obsidian version | Not provided |
| Copilot version | Not provided |
| Agent and model | Not provided |
| Exact English command | Pending validation |

Before labeling the English command as validated, record the environment and check: new connections, repeated execution without duplicates, preservation of existing content, no relevant candidates, and ambiguous titles.

## Limitations

- Connection quality and search coverage depend on the model, tools, and note contents. The command does not guarantee every possible connection.
- Relevant notes may be missed; weak relationships may be suggested. Review the changes.
- An instruction cannot grant file access or bypass agent permissions.
- Copilot chats are not automatically imported from ChatGPT. This command analyzes existing vault notes.
- Depending on your model provider, note contents needed for the request may be sent to an external service.

## Hide Copilot files in the graph

In Graph view's **Filters → Search files**, exclude your actual Copilot folder. For a folder named `copilot`:

```text
-path:"copilot/"
```

For separate folders, adapt the filter:

```text
-path:"copilot-conversations/" -path:"copilot-custom-prompts/"
```

This changes graph visibility, not file storage or agent access.

## License

[MIT](LICENSE).