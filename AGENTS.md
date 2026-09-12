# Working on the WhipScribe Buildathon with an AI coding tool

This file is read by Codex, Claude Code, Gemini CLI, Cursor, Copilot and most
other agents (the tool-specific files in this repo point here). Give it to
your tool at the start of a session; it is the context a teammate would give
you on day one.

## What this repository is

An open challenge in three tracks — see `README.md`:

1. **Find what is wrong with the product.** Use whipscribe.com on a phone and
   a laptop, file UI bugs as issues here, propose fixes.
2. **Build the desktop app.** Calendar-aware meeting recorder that transcribes
   through the WhipScribe API and manages the library through the WhipScribe
   MCP server. Reference for the level of finish: Buzz.
3. **Google Drive, bulk upload and search.** Connect Drive, pick folders,
   transcribe everything in them with progress, then browse and search
   across the transcripts; asking a question across a folder is the stretch.

Work for tracks 2 and 3 lives in `apps/<your-name>/` in your fork, with its own README.

## What WhipScribe is

Recordings in, transcripts and summaries out. Three public doors:

- The product: https://whipscribe.com (sign in to upload, view transcripts,
  manage the library, buy credits).
- The API: https://whipscribe.com/docs — submit a file or a link, poll the
  job, fetch the result as JSON, text, SRT or VTT. Authentication uses an API
  key generated under *Account → API key*; the docs show the header.
- The MCP server: https://whipscribe.com/claude — connect it to an assistant
  (Claude, Cursor, Perplexity and others); the same server is what a desktop
  app uses for library operations.

## Rules the agent must follow

- **Own account only.** Every test runs on the contributor's own WhipScribe
  account and their own recordings. Never fetch, guess or reuse anyone else's
  audio, transcript or key.
- **No secrets in the repo.** API keys, OAuth client secrets and tokens go in
  local configuration (`.env`, keychain, OS credential store) that is
  `.gitignore`d. If you see a secret in a file, stop and say so; do not commit.
- **Do not invent API behaviour.** Read https://whipscribe.com/docs, or make a
  real request and read the response. If the docs and the response disagree,
  write down both in a *Question* issue.
- **Small, early pull requests.** One change per PR, with how to run it and
  what works. Commit messages name the change.
- **Say what you did not do.** A README that lists what is unfinished is worth
  more than one that implies completeness.
- **Keep the human in the loop on judgement calls**: UI decisions, scope cuts,
  anything that touches a customer's data.

## Conventions

- Any stack. Prefer what the contributor can make excellent over what is
  fashionable; ship one platform well before two badly. Platform notes:
  Windows system audio is WASAPI loopback (easy); macOS needs
  ScreenCaptureKit permissions (hard); iOS cannot capture other apps' audio
  at all — microphone only. Never promise system-audio capture on iOS.
- Design the states: empty, loading, error, done, offline. A screen that only
  works on the happy path is not done.
- Accessibility is part of UI quality: keyboard reachable, readable contrast,
  labels on controls.
- Write the README for someone who has never seen the app: install, run,
  connect a calendar, record, see a transcript.

## Suggested order for track 2

1. Connect a calendar and list the next events.
2. Record a meeting to a local file; survive the app closing mid-call.
3. Send the file to the API, poll, show the transcript with speakers.
4. Library operations through the MCP server: list, folders, rename, delete,
   search.
5. Polish: states, shortcuts, notifications, first-run experience.

Stop anywhere and submit; say where and why.

## Suggested order for track 3

1. Google Drive OAuth for a web app; list a folder the user picks.
2. Upload one file through the API; show its transcript.
3. Bulk: a queue with per-file progress that survives the tab closing;
   re-scan for new files.
4. Search across transcripts with results that jump to the moment.
5. Ask a question across a folder.

## Tools

`.mcp.json` configures four MCP servers: WhipScribe (the user's own account),
Playwright (drive a real browser, emulate phones, screenshot), Context7
(current library docs), GitHub (issues and PRs). `TOOLS.md` explains each.
Use Playwright for anything about how a page behaves; do not guess from HTML.

## Starter prompts

`ai/prompts/` has a prompt per track to paste into any tool as the first
message. They ask the tool to read this file first.
