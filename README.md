# WhipScribe Buildathon

WhipScribe turns recordings into transcripts and summaries: paste a link
or upload a file at [whipscribe.com](https://whipscribe.com), or call the
[API](https://whipscribe.com/docs), or use it inside Claude through the
[WhipScribe MCP server](https://whipscribe.com/claude).

This repository is an open challenge in three tracks. We are looking for people,
not just pull requests: someone with a real eye for UI and UX first, then
someone who builds well with AI tools, then someone who will take a feature all
the way to a customer and learn whatever the road needs. Do one track or several.

## Track 1 · Find what is wrong with the product

Use WhipScribe the way a real person would — on your phone and on your laptop —
and write down every place it is confusing, broken, slow or ugly. Then propose
the fix.

**Where to look:** everything at [whipscribe.com](https://whipscribe.com) —
the landing page and free tools, and once signed in: upload, the transcript
view, the library, credits, and the pricing page. This is the live product,
so what you find is what customers see. Mobile Safari, mobile Chrome, and a
desktop browser each count separately.

**How to file:** open an issue here with the *UI bug* template. One issue per
problem. A good report has the device and browser, the exact steps, what you
expected, what happened, and a screenshot or screen recording. Label it
`mobile` or `desktop`.

**How to propose a fix:** add a comment or a second issue with the *Proposal*
template: what you would change, why, and a mockup, sketch, or before/after.
A pull request with the change is welcome where the code is public, but the
proposal is what we read first — we are looking for judgement, not volume.

What stands out to us: noticing the problem a user would feel but not report,
explaining it in two sentences, and a fix that is smaller than the problem.

## Track 2 · Build the desktop app

For a feel of the shape we mean, look at [Buzz](https://github.com/chidiwilliams/buzz):
an open-source desktop app that records, transcribes and shows the result in
one window. Ours goes further — the calendar decides what to record, WhipScribe
does the transcription, and the library is shared with an AI assistant through
MCP — but that level of finish is the bar.

Build a desktop app that:

1. Connects to the user's calendar — Google Calendar first; Outlook, Apple
   Calendar or others are a bonus — and shows what is coming up.
2. Records the meeting — system audio, microphone, or both — with a clear way
   to start, pause and stop, and a recording that survives the app closing
   mid-call. Meeting recordings are the heart of this track: the transcript
   your app shows should read like the meeting, with speakers told apart.
3. Sends the recording to WhipScribe through the public API and shows the
   transcript, summary and speakers when they are ready.
4. Manages the user's recordings and transcripts — folders, search, rename,
   delete — through the WhipScribe MCP server, so the same library is
   reachable from the app and from an AI assistant.

Any stack you can ship with: Electron, Tauri, Swift, .NET, Flutter, Rust. Pick
what you can make excellent. Ship for one platform well before two platforms
badly.

Suggested order: connect a calendar and list events → record a meeting and
save the file → transcribe it and show the result → library management through
MCP → polish. Each step on its own is a fair submission; tell us where you
stopped and why.

**What you need**

- A WhipScribe account. Your own — every test runs on your own account and
  your own recordings. Generate an API key under *Account → API key*.
- The API reference: [whipscribe.com/docs](https://whipscribe.com/docs).
  Submit a file, poll the job, fetch the result as JSON, text, SRT or VTT.
- The MCP server: [whipscribe.com/claude](https://whipscribe.com/claude)
  explains how to connect it to an assistant; the same server is what your
  app talks to for library operations.
- A calendar developer account from the provider you integrate (for Google,
  a Cloud project with the Calendar API enabled and an OAuth client for a
  desktop app). Keep your client secret out of the repository.

**Credits for testing.** Introduce yourself (see *How to take part*) and we
send you a 7-day coupon code for API credits, so you can transcribe real
meetings while you build instead of rationing the free daily allowance.
Redeem it under *Credits* in the app; it applies to the account whose API key
you use.

## Track 3 · Google Drive, bulk upload and search

Most people's recordings already sit in a folder somewhere. Build the piece
that meets them there:

1. **Connect Google Drive** and let the user pick folders. Other storage
   (Dropbox, OneDrive, a local folder) is a bonus.
2. **Bulk upload.** Send everything in the chosen folders to WhipScribe through
   the API, show progress per file, keep going when the user closes the tab,
   and pick up new files that appear later.
3. **Browse and search.** A page that lists what was transcribed, by folder,
   and searches across all of it — the words inside the transcripts, not just
   the file names — with results that jump to the moment in the recording.
   Asking a question across a folder ("what did we decide about pricing?") is
   the stretch goal.

Build it as a web app in your fork under `apps/<your-name>/`, on the public API
for transcription and the MCP server for the library. A thorough design — the
flows, the states, the search results page, the empty folder, the 400-file
folder — is a valid entry on its own for this track; the UI is most of the
problem.

Suggested order: connect Drive and list a folder → upload one file and show
its transcript → bulk with progress → search → ask.

## How to take part

1. Fork this repository.
2. Track 1: file issues here. Tracks 2 and 3: build in your fork under
   `apps/<your-name>/` with a README that says how to run it and what works.
3. Open a pull request when you want us to look. Small, early PRs are better
   than one large one at the end; we will comment as you go.
4. Open an issue titled *Introduction: <name>* with a line about you and what
   you plan to do — that is also how you get the 7-day credit coupon — or put
   the same in your first PR description.

## Prizes

- **Winner:** the Neugence Challenge certificate, and cash of **6,000**.
- **Second:** **4,000**. **Third:** **2,000**.
- Everyone whose work stands out is invited to keep going with us on the real
  product, with access, ownership and pay that grow with what they take on.

Entries across all three tracks are judged together, against the criteria
below. There is no deadline yet; when one is set it will be announced here
and in every open issue.

## How we judge

In this order:

1. **UI and UX craft.** Does it feel right in the hand? Are the states —
   empty, loading, error, done — designed, or left to chance? Would a
   non-technical person understand it without being told?
2. **Building with AI, well.** We expect you to use AI tools. What we look at
   is whether you understood what they produced, kept what was good, and
   threw out what was not. Commit history tells this story; so does a README
   that explains the decisions.
3. **Finishing.** A feature that reaches a real user, with the rough edges
   handled, beats three features that nearly work.
4. **Learning in the open.** New platform, new language, new API — say what
   you had to learn and how it went.

## Ground rules

- Your own account, your own recordings. Never someone else's audio, and never
  a recording of a person who did not agree to it.
- No secrets in the repository: API keys, OAuth client secrets and tokens live
  in local configuration, not in commits.
- Be specific and kind in issues and reviews. We read everything.
- Code you contribute here is under this repository's license; your app in
  your fork stays yours unless you choose to bring it in.

## Questions

Open an issue with the *Question* template. If it is about the API or MCP
behaviour, include the request you made and the response you got, with your
key removed.
