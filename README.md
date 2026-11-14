# deadair

A flight recorder for voice agents. It finds the failures a transcript can't show:
dead air, talk-over, and short replies the bot never heard.

**Status: day 0.** Nothing is built yet. This README says what it will be and why.

## The problem

Teams that ship phone and voice agents mostly test them by reading transcripts. But the
failures callers feel are in the audio:

- The caller says "yes" and the bot doesn't hear it.
- The bot talks over the caller, or stops every time someone coughs.
- Nobody speaks for four seconds and the caller hangs up.

The transcript of that call can look fine. See [docs/pains.md](docs/pains.md) for the
people saying this, with links.

## What it will do (first version)

Take a call, find the audio-level failures, and show them on a timeline you can read in a
minute. The exact shape of the first version is still an open decision. See
[DECISIONS.md](DECISIONS.md).

## What it is not

- Not a hosted product. It runs on your machine and your audio stays there.
- Not a replacement for transcript evals. It covers the part they miss.

## License

MIT
