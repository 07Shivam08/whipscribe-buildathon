# WhipScribe Buildathon

WhipScribe turns recordings into transcripts and summaries. Try it at
[whipscribe.com](https://whipscribe.com). There is a public
[API](https://whipscribe.com/docs) and an [MCP server](https://whipscribe.com/claude)
for AI assistants.

This is a challenge and a way of hiring. We want to find three kinds of people,
in this order: someone with a real eye for UI and UX, someone who builds well
with AI tools, and someone who will take a feature all the way to a customer.

Pick one track or more.

## Track 1 — Find what is wrong

Use [whipscribe.com](https://whipscribe.com) on your phone and on your laptop.
Sign in, upload a file, read the transcript, use the library, look at credits
and pricing. It is the live product.

- File each problem as an issue here, using the **UI bug** template.
- Label it `mobile` or `desktop`.
- For the ones that matter, add a **Proposal**: what you would change, why, and
  a mockup or before/after.

We read proposals before code. A small fix for a real problem beats a long
list.

## Track 2 — Build the desktop app

A desktop app that:

1. Connects to your calendar (Google first; others are a bonus) and shows
   what is coming up.
2. Records the meeting — system audio, microphone, or both — and keeps the
   recording if the app closes mid-call.
3. Sends it to WhipScribe through the API and shows the transcript with
   speakers.
4. Manages your recordings through the MCP server: folders, search, rename,
   delete.

For the level of finish we mean, see [Buzz](https://github.com/chidiwilliams/buzz).
Any stack. One platform done well beats two done badly.

Build in order: calendar → recording → transcript → library → polish. Stop
where you like and say why.

## Track 3 — Google Drive, bulk upload, search

A web app that:

1. Connects to Google Drive and lets you pick folders.
2. Transcribes everything in them, with progress per file, and picks up new
   files later.
3. Lists what was transcribed by folder, and searches the words inside the
   transcripts. Results jump to the moment in the recording.
4. Stretch: ask a question across a folder.

A thorough design on its own is a valid entry for this track. The UI is most
of the problem.

## What you need

- Your own WhipScribe account. Get an API key under *Account → API key*.
- The API docs: [whipscribe.com/docs](https://whipscribe.com/docs).
- The MCP server: [whipscribe.com/claude](https://whipscribe.com/claude).
- For tracks 2 and 3: a Google Cloud project with the Calendar or Drive API
  and an OAuth client. Keep the client secret out of the repo.
- Credits for testing: introduce yourself (below) and we send you a 7-day
  coupon for API credits.

AI tools are expected. `AGENTS.md` is the brief for them, and `ai/prompts/`
has a starter prompt for each track.

## How to take part

1. Fork this repo.
2. Open an issue titled **Introduction: your name** with a line about you and
   what you plan to do. That is how you get the credit coupon.
3. Track 1: file issues here. Tracks 2 and 3: build in `apps/your-name/` in
   your fork, with a README that says how to run it and what works.
4. Open a pull request when you want us to look. Small and early is better
   than big and late.

## Prizes

- **Winner:** the Neugence Challenge certificate and **₹6,000**.
- **Second:** **₹4,000**.
- **The real prize:** people whose work stands out work with us for a few
  weeks on the real product — paid, with real customers — to see if it is the
  right fit. That is the path to a full-time offer.

No deadline yet. When there is one, it will be posted here.

## How we judge

1. **UI and UX.** Does it feel right? Are empty, loading, error and done
   states designed? Would a non-technical person get it?
2. **Building with AI, well.** Did you understand what the tool produced,
   keep the good and drop the rest? Your commits and README show this.
3. **Finishing.** One thing that works for a real user beats three that
   nearly do.
4. **Learning.** Say what was new to you and how it went.

## Rules

- Your own account and your own recordings. Never record someone who did not
  agree.
- No keys, secrets or tokens in commits.
- Be specific and kind. We read everything.
- Your app in your fork stays yours.

Questions: open an issue with the **Question** template.
