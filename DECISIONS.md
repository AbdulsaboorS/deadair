# Decisions

One entry per real decision: the options, his choice, and why. Newest at the bottom.

## Open (not decided yet)

1. **Shape of the first version.** An offline analyzer that reads a call recording, or a
   tracer that plugs into a running agent?
2. **Which failures come first.** Dead air, talk-over, missed short replies, slow turns,
   lost keypad tones. Pick one to three.
3. **Where the first test calls come from.** A voice agent he runs himself, public sample
   calls, or synthetic calls made for the purpose.
4. **Language and stack.**
5. **Which framework gets the first integration,** if the tracer shape wins: Pipecat,
   LiveKit Agents, or the Cloudflare voice stack.

## Decided

- 2026-11-14: Name is `deadair`. Public repo, MIT license. Lives in its own repo because it
  is a tool people install, not a page they visit.
