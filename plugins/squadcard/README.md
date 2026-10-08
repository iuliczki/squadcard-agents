# Squadcard

Organise your weekly football game from Claude. Squadcard is an app for football groups that play every week:
who's in, fair teams, and ratings from your mates. This plugin connects Claude to it, with a skill that tells
Claude how to use the tools well.

## What you can ask for

- Two fair teams from a list of names, with the keepers split
- A round-robin fixture list for 3 to 16 teams
- Team name ideas
- A new squad, and the invite link to post in your group chat
- Joining a squad from an invite link you give it
- Saying you're in, maybe or out for the next game
- When and where the squad plays, and who's in
- The teams for this week, a reshuffle, the score, and the vote link for after the game

The first three need no squad. The rest act on the squads of the person who signed in.

## Example prompts

Things you can type as they are:

1. "Split these ten into two fair teams, Sam and Kofi are keepers: Sam, Kofi, Priya, Tom, Dan, Aisha, Lewis, Ollie, Jay, Rob."
2. "Make a round-robin for four teams: Reds, Blues, Greens and Yellows. Home and away."
3. "Start a 5-a-side squad called Tuesday Fives and give me the invite link."
4. "Who's in for our next game? If we have ten, pick the teams."
5. "We finished 7-5 to the bibs. Enter the result and give me the vote link."

The first two need no squad. The rest act on your own squads, and Claude asks before it starts a squad or
saves a score, because other people see those.

## Signing in

The first time Claude uses a squad tool, your browser opens. You sign in to Squadcard and press Allow. Claude
never sees your password, and you never paste a key into the chat. You can disconnect at any time from your
account at https://squadcard.app/account, under AI agents.

## What it does and what it sends

The plugin adds one remote MCP server, `https://squadcard.app/api/mcp`, and one skill. It runs nothing on your
computer and installs no packages. What you ask for (names, a score, a squad's name) goes to squadcard.app, the
same service as the website and the iPhone app, and nowhere else.

## What it can't do

There are no tools for votes, payments, removing players or deleting anything. Nobody, including an agent, can
see how an individual voted: only totals are ever shown. Starting a squad follows the website's own rule; see
https://squadcard.app/pricing.

## Links

- Guide: https://squadcard.app/agents
- Help: https://squadcard.app/help
- Support: https://squadcard.app/support
- Privacy: https://squadcard.app/privacy
- Terms: https://squadcard.app/terms
