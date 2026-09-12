# Tools that make you faster

Everything here is public and free to set up. `.mcp.json` at the repo root
configures all four MCP servers for Claude Code; `.cursor/mcp.json` is the same
for Cursor. Codex and others: copy the entries into your tool's MCP config.

| Tool | What it does for you | Track |
|---|---|---|
| **WhipScribe MCP** — `https://whipscribe.com/mcp` | Your assistant can transcribe, list your library, search and manage folders on your own account. Sign in when the tool asks; setup notes at [whipscribe.com/claude](https://whipscribe.com/claude). | 2, 3, 4 |
| **Playwright MCP** — `@playwright/mcp` | Your assistant drives a real browser: open whipscribe.com, emulate an iPhone or Pixel, click through a flow, take screenshots, read console errors. Reproduce a bug once, then let the tool re-run it. | 1 |
| **Context7** — `@upstash/context7-mcp` | Current docs for the library you are using (Tauri, Electron, Google APIs, your web framework) instead of the model's memory. | 2, 3, 4 |
| **GitHub MCP** — `@modelcontextprotocol/server-github` | File issues and open PRs from inside your tool. Needs `GITHUB_TOKEN` in your environment with `repo` scope on your fork. | all |

Not MCP, still worth it:

- **Playwright test runner** (`npm init playwright@latest`) with device profiles
  (`devices['iPhone 14']`, `devices['Pixel 7']`) to turn a Track 1 bug into a
  script that proves the fix.
- **Lighthouse** (in Chrome DevTools) for mobile performance and accessibility
  scores on any page you report on.
- **axe DevTools** browser extension for accessibility findings with the exact
  element.
- **`gh` CLI** for issues and PRs from the terminal.

## Setting up

Claude Code: open the repo and run `claude`; it picks up `.mcp.json` and asks
you to approve each server. Cursor: Settings → MCP shows the four servers from
`.cursor/mcp.json`. Codex: add the same commands under `[mcp_servers]` in
`~/.codex/config.toml`.

Playwright needs Node 18+ and downloads browsers on first use. The WhipScribe
server signs you in through the browser the first time.

Keep `GITHUB_TOKEN` and any OAuth secrets in your shell environment or a
gitignored file, never in a commit.
