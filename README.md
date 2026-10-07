# Squadcard for AI agents

Squadcard is an app for football groups that play every week: who's in, fair teams, and ratings from your mates.
This folder holds what agents need to use it. Full guide: https://squadcard.app/agents

One MCP server, nothing to install: `https://squadcard.app/api/mcp`. You sign in to Squadcard once in your
browser; after that your agent can:

- make two fair teams from a list of names
- make a round-robin fixture list
- suggest team names
- start a squad and hand you the invite link
- join a squad from an invite link you give it
- say you're in, maybe or out for the next game
- set up the week's game and tell you who's in
- pick the teams, enter the score and hand you the vote link

It can never see how anyone voted, mark payments, buy anything, remove players or delete anything.

## Claude Code

```
claude mcp add --transport http squadcard https://squadcard.app/api/mcp
```

Then `/mcp` → `squadcard` → sign in. Or install the plugin in `claude-code-plugin/`, which adds the server and a
skill that tells Claude how to use it.

## Codex

```
codex mcp add squadcard --url https://squadcard.app/api/mcp
codex mcp login squadcard
```

## No browser where your agent runs?

Make a key at https://squadcard.app/account under "AI agents" and send it as `Authorization: Bearer <key>`
(`codex/config.toml` shows how for Codex). A key has the same limits as signing in, and you disconnect either
on the same page.
