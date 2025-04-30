# Table AI Agent
Used to make tables for Svelte components

> Note: Claude (although supposed to be in devbox isolation) creates `~/.claude.json` and `~/.claude dir` (it's a naughty little AI) 
> 
> MCP server config (with `project` scope) is created in `project/.mcp.json`

## Initialization
Shell into devbox → will install npm dependencies → run claude → will prompt you to login.
Thereafter configure and MCP (Context7) → verify MCP connected.
1. `devbox shell`
2. `ai.claude.run` (login + connect account → via devbox alias)
3. `exit` (adding mcp via claude, whist in claude is flaky)
4. `npx claude mcp add context7 -s project -- npx -y @upstash/context7-mcp@latest` (whilst in claude)
5. `ai.claude.run` (back in claude) 
6. `/mcp` (verify MCP connected)

### Project Generation
As this is a "workbench", AI generated code should be isolated (with all relevant dependencies) in its own dir.
Attempting, symbolic linking to temp location (could be to any project dir).
1. `mkdir /tmp/web-app`
2. `ln -s /tmp/web-app web-app`

## Table Prompt
Since we have a Context7 MCP, we should be able to create a Svelte table, with Tailwind CSS.
1. `npx claude`
2. `/mcp` (verify context7 is connected → should also detect & ask)
3. 
```
All of the work you do should be in "web-app" dir.

Create a Svelte Table with Tailwind CSS. 

Table header should have the following columns:
Instrument
Market
Quantity
Instant
```
4. Code will get generated in "web-app" dir (along with package, etc)

### Run AI generated code
Could do this as part of the `Table Prompt`, just convenience for separate terminal.
1. `devbox shell`
2. `cd web-app`
3. `npm install`
4. `npm run dev`

### Unlink for next generation
As this is a "workbench" code will not be committed from here → rather where ever the sym link is.
However, simply unlink the dir and follow the steps to generate again.
1. `rm web-app`

## Resources
* [Claude Code MCP](https://docs.anthropic.com/en/docs/agents-and-tools/claude-code/tutorials#set-up-model-context-protocol-mcp)
* [Context7 MCP Config](https://github.com/upstash/context7?tab=readme-ov-file#install-in-claude-code)