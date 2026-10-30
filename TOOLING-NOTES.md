# Tooling added alongside Harvey (session notes)

Skills are copied into `.claude/skills/` so they load when Claude Code runs in this folder.
The originals are untouched, so the same skills still work outside this folder.

## Skills in .claude/skills/
- Day trader pack (11): trader-scanner, -news, -entry, -exit, -timemachine, -risk, -budget, -broker, -alerts, -analyst, -pelosi
  (source: Jakeschincariol/day-trader-skill; Python, reads free public data, paper trading by default, no order without an explicit yes)
- Design: design-taste-frontend (Leonxlnx/taste-skill), impeccable (pbakaus/impeccable), pro-design (custom, includes the Lenis default rule)
- Anti-slop pack (6): antislop, antislop-code, antislop-copywriting, antislop-human, antislop-layoutmobile, antislop-ui (miqdadbadjuber/anti-slop)
- agent-reach (Panniantong/Agent-Reach): read-only search and reading across web, GitHub, YouTube, Bilibili, V2EX
- img2threejs (v2.0.0): turns a reference image into a procedural Three.js model

## Reference files
- `DESIGN.md`: Claude-style design reference from `npx getdesign@latest add claude`

## Tools installed on the machine (not part of this repo)
- `lenis` (npm): smooth scrolling for websites. pro-design uses it by default and turns it off for visitors who prefer reduced motion.
- `@playwright/cli` (npm, global) and the `playwright` MCP server (`claude mcp add playwright npx @playwright/mcp@latest`).
  The browser download was blocked in the cloud workspace, so these need to be set up on a normal computer: run `playwright install chromium`.
- `agent-reach` (uv tool). Extra channels (Reddit, X, Instagram, Facebook) failed to add in the cloud workspace; retry on a normal computer.

## Not working in the cloud workspace (network allowlist)
nasdaqtrader.com, Yahoo Finance, cdn.playwright.dev, impeccable.style and the helper download Agent Reach needs for social channels.

## Agent Floor (live 3D office for coding agents)
- Source: github.com/develop212/agent-floor (not on npm, built from source). Source lives in `agent-floor/` in this repo (node_modules and dist are git-ignored). After a fresh clone run `cd agent-floor && npm ci && npm run build` once.
- Project hooks are in `.claude/settings.json` (backup: `settings.json.bak`), so Agent Floor opens when Claude Code starts in this folder.
- It listens on 127.0.0.1:4317 only. Set `AGENT_FLOOR_AUTOLAUNCH=0` to stop hooks from opening the window.
- The desktop window needs Electron or a Chromium browser on a normal computer; it cannot open in the cloud workspace.

## Browser tools for this project
- `.claude/skills/playwright-cli`: Playwright CLI skill.
- `.mcp.json`: project MCP servers `playwright` (`npx @playwright/mcp@latest`) and `chrome-devtools` (`npx chrome-devtools-mcp@latest`).
  Both need a real Chrome or Chromium on the machine. They could not open pages in the cloud workspace.
