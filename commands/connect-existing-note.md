Your task is to connect an existing note to other notes in my Obsidian vault by editing the target note directly.

When I provide a note name or reference:

1. Locate and read the original file. If the target is missing or ambiguous, ask me to identify it before editing anything.
2. Search other vault notes and read candidate notes to verify useful relationships with the target's content. Exclude Copilot conversations, saved prompts, agent instructions, and other configuration files from connection candidates.
3. Verify the exact titles and paths of related files.
4. Use the available editing tool to append a connections section to the original file.

LANGUAGE AND SECTION FORMAT
- Write relationship explanations in the same language as the target note.
- Preserve note titles and paths exactly as they exist in the vault.
- If a connections section already exists, reuse its heading.
- Otherwise, use "## Conexões com outras notas" for Portuguese notes, "## Connections to other notes" for English notes, or an equivalent heading in the target's language.
- Format entries as: - [[Exact note title]] — A brief, specific explanation of the relationship.

LINK FORMAT IN THE FILE
- Save literal Obsidian wikilinks: [[Exact note title]].
- When necessary to disambiguate duplicate titles, use [[folder/Title]].
- Do not use Markdown links such as [text](address).
- Do not use app://, obsidian://, or web URLs for these connections.
- Do not escape brackets or put the connections in a code block.

EDITING
- Editing the target note is this command's default behavior.
- Do not merely return a section in chat for me to copy.
- Preserve all content outside the connections section, including properties, examples, code, and existing formatting.
- If the section already exists, update it without duplicating links and preserve valid existing connections. Recognize links to the same destination even when they use different aliases or paths.
- Do not create, rename, or delete files.
- Do not edit related notes or add reciprocal links.

CRITERIA
- Include only relevant relationships with notes that exist and that you have read to verify the connection.
- Do not link the target note to itself.
- Do not invent titles or force relationships based only on shared words.
- Prefer specific, useful connections over a large number of weak links.
- If you find no relevant connections, leave the file unchanged and report that result.

VERIFICATION
- After editing, reread the original file to confirm that the section was saved with literal [[wikilinks]] and that unrelated content was preserved.
- Only claim that you edited the note after verifying the change.
- If tools or permissions do not allow reading, searching, or editing, state the limitation clearly. Do not simulate a completed edit.

FINAL RESPONSE
Briefly confirm which note was edited and how many new connections were added. If none were added, say so. Do not reproduce the entire note.