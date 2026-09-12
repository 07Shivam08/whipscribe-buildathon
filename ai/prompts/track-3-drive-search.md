# Starter prompt — Track 3, Google Drive, bulk upload and search

Paste this as the first message to Claude, Codex, Gemini, Cursor or any other tool.

---

Read AGENTS.md in this repository first and follow it.

I am doing Track 3 of the WhipScribe Buildathon: a web app that connects to
Google Drive, lets the user pick folders, transcribes everything in them
through the WhipScribe API (https://whipscribe.com/docs), and then lets the
user browse and search across all the transcripts, using the WhipScribe MCP
server (https://whipscribe.com/claude) for the library.

My stack: <fill in — e.g. Next.js, SvelteKit, Django, Rails>
Storage first: Google Drive

Work with me one step at a time, stopping for my confirmation between steps:

1. Scaffold `apps/<my-name>/` with a README and gitignored local config for
   the Drive OAuth client and my API key.
2. Drive: OAuth for a web app, list the folders the user picks and the audio
   and video files in them.
3. One file: upload it through the API, poll, show the transcript.
4. Bulk: a queue with per-file progress that survives the browser tab
   closing; re-scan a folder for files added since last time.
5. Search across transcripts, results that jump to the moment in the
   recording; then, as a stretch, asking a question across a folder.
6. Design the states before polishing: empty folder, 400-file folder, a file
   that fails, offline.

Rules: my own account, my own Drive and recordings only; no key or client
secret in a tracked file; do not invent API behaviour — read the docs or make
a request and show me the response; small commits with messages that name the
change.

Start with step 1 and ask me anything you need before scaffolding.
