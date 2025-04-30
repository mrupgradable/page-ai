# Table AI Agent
Used to make tables for Svelte components

> Note: Claude (although supposed to be in devbox isolation) creates `~/.claude.json` and `~/.claude dir` (it's a naughty little AI) 
> 
> MCP server will be created in ~/.claude.json (should be local) 

## Initialization
Shell into devbox → will install npm dependencies → run claude → will prompt you to login.
Thereafter configure and MCP (Context7) → verify MCP connected.
1. `devbox shell`
2. `ai.claude.run` (login + connect account)
3. `exit` (exit to add mcp)
4. `npx claude mcp add context7 -- npx -y @upstash/context7-mcp@latest`
5. `ai.claude.run`
6. `/mcp` (in claude)

## Table Prompt
Since we have a Context7 MCP, we should be able to create a Svelte table, with Tailwind CSS.
1. `npx claude`
2. 
```
Create a Svelte Table with Tailwind CSS. 
Table header should have the following columns:
Instrument
Market
Quantity
Instant
```