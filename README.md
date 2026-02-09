# Claude Agent SDK Skill

A [Claude Code skill](https://docs.anthropic.com/en/docs/agent-sdk/skills) that teaches Claude how to build applications with the Claude Agent SDK (`@anthropic-ai/claude-agent-sdk` or `lite-claude-agent-sdk`).

Covers the full API surface: query options, hooks, MCP servers, multi-turn conversations, streaming, permissions, structured output, and session management.

## Install

Clone or symlink into your project's `.claude/skills/` directory:

```bash
# Option 1: Clone directly
git clone https://github.com/foksa/claude-agent-sdk-skill.git .claude/skills/claude-agent-sdk

# Option 2: Add as git submodule
git submodule add https://github.com/foksa/claude-agent-sdk-skill.git .claude/skills/claude-agent-sdk
```

Claude Code will automatically discover the skill from `.claude/skills/claude-agent-sdk/SKILL.md`.

## Structure

```
SKILL.md                        # Core workflow + quick reference (~100 lines)
references/
├── query-options.md            # All 35+ options with types/defaults
├── hooks.md                    # 15 hook events, matchers, callbacks
├── mcp-servers.md              # stdio/HTTP/SDK servers, tool() helper
└── patterns.md                 # Multi-turn, streaming, sessions, gotchas
```

The skill uses progressive disclosure: `SKILL.md` provides the essentials, and Claude loads reference files on-demand when deeper detail is needed.

## What's Covered

- **Query options** — All configuration fields with types, defaults, and examples
- **Hooks** — PreToolUse, PostToolUse, Stop, Notification, and 11 more events
- **MCP servers** — stdio, HTTP/SSE, and in-process SDK servers with `tool()` + `createSdkMcpServer()`
- **Patterns** — Multi-turn with `streamInput()` and AsyncIterable, `canUseTool` approval flows, structured output with Zod, session resume/fork, AbortController, token streaming
- **Gotchas** — Empty systemPrompt token savings, hook return value semantics, declarative-only hooks, and more

## License

MIT
