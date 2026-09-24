# AGENTS.md

## Working rules

### Language
- Write the first response in the language of the user's first prompt.
- End that first response with a short question, written in English,
  asking whether the user would like to continue the conversation in English.

### Commits
- Commit only after the user explicitly requests it and approves it.
- Workflow: [request] -> preview -> [permit] -> pr
  1. [request]: The user asks for a commit.
  2. preview: Show the changes to be committed (files and key diffs)
     and the commit message in a code block.
  3. [permit]: The user approves.
  4. pr: Only then commit and push.
- Never commit or push without approval.

### Agent instruction files
- The same workflow applies to creating or modifying AGENTS.md or CLAUDE.md.
  Show the proposed changes first, and write or commit the file only after approval.
- AGENTS.md is the single source of truth for shared rules. CLAUDE.md imports it
  (`@AGENTS.md`) and adds only Claude-specific rules.
