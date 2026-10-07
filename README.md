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

## MCP config

For any client that takes a JSON config (Claude Desktop, Cursor, VS Code and others):

```json
{
  "mcpServers": {
    "squadcard": {
      "type": "http",
      "url": "https://squadcard.app/api/mcp"
    }
  }
}
```

The first time a tool is used, your browser opens for you to sign in to Squadcard.

## Tools

- `make_fair_teams`: two balanced teams from a list of names, with the keepers split
- `make_fixtures`: a round-robin fixture list for 3 to 16 teams
- `suggest_team_names`: team names from a theme or a word
- `list_squads`: the squads of the person signed in
- `get_squad`: a squad, its invite link, the next game and who is in
- `create_squad`: start a squad, with you as organiser
- `join_squad`: join a squad from an invite link you give it
- `set_game`: when and where the squad plays
- `answer_game`: say you are in, maybe or out for the next game
- `pick_teams`: balanced teams from whoever is in
- `reshuffle_teams`: another fair split of the same players
- `enter_result`: save the score, which opens voting, and get the vote link
- `get_match`: a match, its teams, score and turnout

## Claude Code

```
claude mcp add --transport http squadcard https://squadcard.app/api/mcp
```

Then `/mcp` → `squadcard` → sign in.

Or install the plugin, which adds the server and a skill that tells Claude how to use it. In Claude Code:

```
/plugin marketplace add iuliczki/squadcard-agents
/plugin install squadcard@squadcard
```

## Codex

```
codex mcp add squadcard --url https://squadcard.app/api/mcp
codex mcp login squadcard
```

## No browser where your agent runs?

Make a key at https://squadcard.app/account under "AI agents" and send it as `Authorization: Bearer <key>`
(`codex/config.toml` shows how for Codex). A key has the same limits as signing in, and you disconnect either
on the same page.

## What is in this repository

- `plugins/squadcard/`: the Claude Code plugin (the server, a skill, its own README and licence)
- `.claude-plugin/marketplace.json`: lets Claude Code install the plugin from this repository
- `codex/config.toml`: the same server for Codex
- `server.json`: the entry for the MCP registry

MIT licence.
