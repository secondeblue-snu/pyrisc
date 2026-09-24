@AGENTS.md

## Claude-specific rules

### Claude-Session link
- Applies only when the environment (e.g., Claude Code on the web) explicitly
  provides a `Claude-Session` link for commits or PRs. Never construct or guess
  a session link yourself.
- If one is provided: leave it out by default, and list it as an optional
  item during the preview step. Include it only when the user explicitly asks.
- If none is provided (e.g., a local CLI session): skip this item entirely.
