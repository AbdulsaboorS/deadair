# Why this exists: the pains, with sources

Collected 2026-11-12. Quotes are short and verbatim. Vendor posts are labeled, since a
vendor describing a problem is weaker evidence than a user describing their own.

### Shipped voice agents fly blind
- Who: people building voice agents for booking, support, healthcare intake
- Source: https://news.ycombinator.com/item?id=45837650 (Hacker News, 2025-11-06, vendor)
- Quote: "once you ship a voice agent, you basically fly blind. You can't easily tell why calls fail."
- Also: https://news.ycombinator.com/item?id=45644302 (vendor), https://news.ycombinator.com/item?id=46042845
- Today they: read call logs and listen to recordings

### Framework users want traces to evaluate voice apps
- Who: LiveKit Agents and Pipecat builders
- Source: https://github.com/livekit/agents/issues/2260 (GitHub, 2025-03-26)
- Quote: "multiple requests by community members who'd like to get traces of their livekit applications in order to evaluate them."
- Signals: 57 reactions when collected, the top issue in the repo at the time

### Short replies are not heard, and tuning breaks interruptions
- Who: Pipecat voice agent builders
- Source: https://github.com/pipecat-ai/pipecat/issues/984 (GitHub, 2025-01-14)
- Quote: "short utterances like, "OK", "Yes, "No" aren't "heard" by the bot."
- Today they: lower the voice-detection start time and accept false interruptions
- Related: turn-taking dominates this thread on fast voice agents: https://news.ycombinator.com/item?id=47224295

### Transcript-based evals miss failures callers feel
- Who: teams shipping phone agents
- Source: https://dev.to/forgeflows/voice-agent-evals-are-blind-to-40-of-failures-33f7 (DEV, 2026-06-24, vendor)
- Quote: "The transcript passes. The customer hangs up frustrated. Your metrics never know."
- Today they: listen to sample calls weekly

### Telephony edge cases silently break speech-to-text
- Who: voice developers on SIP/RTP
- Source: https://news.ycombinator.com/item?id=49869684 (Hacker News comment, 2026-09-27)
- Quote: "Not "got it wrong," got literally nothing."
- Signals: one detailed report. Keypad tones (DTMF) went missing, and a tone decoder invented keypresses from speech

### Speech recognition breaks on domain words and accents
- Who: voice AI call-center builders, pharmacy and healthcare operators
- Source: https://news.ycombinator.com/item?id=49246249 (Hacker News, 2026-08-10); story: https://news.ycombinator.com/item?id=49244569
- Quote: "the biggest problem is ASR. WER is still atrocious even with SOTA models. When you add drug names and regional accents"

## What already exists

Funded testing and observability tools: [Coval](https://www.coval.dev),
[Hamming](https://hamming.ai), [Cekura](https://www.cekura.ai),
[Vapi tests](https://docs.vapi.ai/test/voice-testing.mdx), and Langfuse for traces.
The gap this repo aims at: most of them judge the transcript, and audio-level failures
stay invisible. That claim comes partly from vendors and has not been tested here yet.
Checking it is part of the work.
