# Starter prompt — Track 2, build the desktop app

Paste this as the first message to Claude, Codex, Gemini, Cursor or any other tool.

---

Read AGENTS.md in this repository first and follow it.

I am doing Track 2 of the WhipScribe Buildathon: a desktop app that connects
to my calendar, records meetings, transcribes them through the WhipScribe API
(https://whipscribe.com/docs) and manages the library through the WhipScribe
MCP server (https://whipscribe.com/claude). The bar is the best
meeting-recording desktop app on the market: help me survey what exists,
name what each gets right and wrong, and design something better.

My stack: <fill in — e.g. Tauri + TypeScript, Electron, Swift, .NET>
My platform first: <macOS | Windows | Linux>
My calendar first: <Google | Outlook | Apple>

Work with me in this order, one step at a time, and stop for my confirmation
between steps:

1. Survey: list the desktop meeting recorders people actually use, and for
   each what it gets right and where it falls short. Then write down the
   three things ours will do better. Only then scaffold `apps/<my-name>/` with a README that will say how to run it and
   what works. Set up local config for secrets that is gitignored from the
   start.
2. Calendar: OAuth for a desktop app, list the next events, show them.
3. Recording: system audio and microphone, start/pause/stop, a file that
   survives the app being closed mid-call.
4. Transcription: read https://whipscribe.com/docs, submit the file with my API
   key from local config, poll the job, show the transcript with speakers.
   Design the loading, error and done states.
5. Library through MCP: list, folders, rename, delete, search.
6. Polish and the README's "what works / what does not yet" section.

Rules: my own account and recordings only; never put a key or client secret
in a tracked file; do not invent API behaviour — read the docs or make a
request and show me the response; small commits with messages that name the
change.

Start with step 1 and ask me anything you need before scaffolding.
