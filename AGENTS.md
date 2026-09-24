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

### Pull request status
- Before each push, check the current state of the pull request for the
  working branch: open, merged, or closed.
- In the preview step, state which pull request the commit will go into
  (e.g., "adds to #2 (open)" or "opens a new PR").
- If the branch's pull request is already merged or closed:
  - Do not push onto it; new commits there will not show up in any PR.
  - Start the branch again from the latest default branch, keeping only
    the commits that have not been merged yet.
  - Open a new pull request for them, after the usual preview and approval.
  - Report this in the preview, including any force push it requires.

### Agent instruction files
- The same workflow applies to creating or modifying AGENTS.md or CLAUDE.md.
  Show the proposed changes first, and write or commit the file only after approval.
- AGENTS.md is the single source of truth for shared rules. CLAUDE.md imports it
  (`@AGENTS.md`) and adds only Claude-specific rules.
