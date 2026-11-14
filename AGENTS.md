# deadair (public)

An open source flight recorder for voice agents. It finds audio-level failures that
transcript evals miss: dead air, talk-over, short replies the bot never heard.

Abdulsaboor builds this in public to learn the audio side of voice agents and to make
something voice builders actually install. He directs and makes the architecture calls.
Agents are his technical team and teachers. He must be able to explain every part of it
out loud.

## Layout

```
AGENTS.md            rules (this file, 90 lines max)
CLAUDE.md            points Claude Code here
SESSION_CONTEXT.md   handoff between sessions, gitignored, 60 lines max
README.md            what it is, who it's for, how to try it
DECISIONS.md         decision log: the options, his choice, and why
WALKTHROUGH.md       how it works, top 3 tradeoffs, what breaks at scale (written at ship)
docs/pains.md        the sourced complaints this exists to fix
docs/concepts.md     plain-word notes on each concept, written as he learns it
```

## What good looks like

- A voice builder can try it in under a minute with one command on one call.
- The output shows a failure they did not know about, on a timeline they can read fast.
- There is one moment worth a muted 30-second clip.
- The first version ships in 1 to 3 days. Cut scope before adding time.

## Teaching rules (part of done)

- Before building a piece, explain the concept behind it in plain words, with one small
  example. Then add it to docs/concepts.md in a few lines.
- Every real architecture decision: 2 to 3 options with tradeoffs, a recommendation, and
  he decides. Log it in DECISIONS.md.
- Build in small steps he can run and hear. After each step, tell him what to run and
  what he should see.
- He should type or change some of the code himself when a concept is new. Offer that,
  don't force it.
- Before shipping, ask one light quiz question. Write WALKTHROUGH.md.
- Concepts to cover as they come up: voice activity detection, turn-taking and
  endpointing, barge-in, the latency budget across speech-to-text, the model, and
  text-to-speech, cascaded versus full-duplex models, phone audio (8 kHz, codecs),
  keypad tones, traces and spans.

## Build rules

- Every number is measured, counted, or labeled illustrative. No invented accuracy claims.
- Check each detector against calls where the failure is known, and report misses too.
- Describe his experience only from facts he gave.
- Compare against the existing tools honestly. If one already does a thing, say so.

## Technical rules

- Pick the boring stack that ships. Propose it; he decides.
- Audio stays local by default. Nothing is uploaded unless the user asks.
- Real call recordings never go in git. Only synthetic or clearly licensed samples.
- Secrets only in `.env` or `.dev.vars`, both gitignored.

## Copy rules

- Casual, plain, direct, in his voice. No em dashes anywhere.
- Posts are his. Agents may outline posts and pick clip moments. He writes the final words.

## Git rules

- Small commits, plain messages. Work on branches once there is a working version on main.
- Publishing a package or a release needs his say-so in the current session.

## Session rules

- Start: read SESSION_CONTEXT.md. End: rewrite it (60 lines max, current state only).
- Push back once if you see a better approach, then defer.
- Report what was actually run and heard. Anything checked only by reading code is
  reported as code-verified.
