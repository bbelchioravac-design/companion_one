# ALIOS ONE Chat — Community Edition

A private AI assistant that lives on your machine, remembers what you decide it remembers, and never lets your API key touch a browser.

Built by someone who spent over a year building AI memory architectures the hard way — this is the clean, simple starting point she wishes she'd had.

## What you get

- **Chat with any model on OpenRouter** (GPT, Claude, Gemini, Llama, Deepseek…) — streaming, images, dictation, one interface
- **Memory cards** — the heart of it. Write down what your assistant should always remember (project context, working preferences, technical terminology, key decisions). Every active card travels with every message. Toggle cards on/off. You are in full control of the memory — nothing is stored or inferred behind your back
- **Automatic session summaries** so long conversations never lose the thread
- **Real privacy:** everything (chats, cards, settings) lives in local files next to the app. Your API key is stored on disk and used server-side only — the browser never sees it. No accounts, no cloud, no telemetry
- **Temperature, repetition penalty, context window, custom system prompt** — the knobs that matter, nothing that doesn't

## Install (3 steps, ~2 minutes)

You need: [Python 3.10+](https://python.org/) (tick "Add to PATH" on Windows) and a free [OpenRouter](https://openrouter.ai/keys) API key (pay-per-use — casual usage costs cents per day; add $5 credit and forget).

1. Download this folder
2. Windows: double-click `install.bat` · Mac/Linux: `./install.sh` (it installs 3 small Python packages and asks for your API key once)
3. Windows: double-click `run.bat` · Mac/Linux: `./run.sh`

Your browser opens at `http://localhost:8801`. Open ⚙, define your assistant's system prompt (its role, communication style, domain expertise), create your first memory card, and start working.

## How memory works here (honest version)

This app does **manual memory**: you write the cards, you decide what's active. The AI receives your cards with every message and treats them as its own context. That's it — simple, transparent, fully yours.

It does **not** do automatic memory (vector databases, embeddings, nightly consolidation). That architecture exists — the author runs a much larger system in production — but it's a different beast: servers, pipelines, calibration. This edition is the honest starting point. If you outgrow it, you'll know exactly what to build next, and you'll understand why.

**Pro tip:** end productive sessions by asking your assistant *"summarize the key decisions and context from today that you'd want to carry forward"* — then paste the answer into a new memory card. Congratulations, you're doing memory consolidation by hand. It works better than you'd think.

## FAQ

**Where is my data?** In `state.json` next to `server.py` (with automatic backups in `backups/`). Copy that file = full backup. Delete it = clean slate.

**Which model should I use?** GPT-4o and Claude Sonnet are the strongest general-purpose models. Llama 3.3 70B is the budget option. Any OpenRouter model id works.

**Can other devices use it?** By default it's localhost-only (safe). To use it from another device on the same network, edit `HOST` in `server.py` to `"0.0.0.0"` — and understand that anyone on your network could then use your API credit.

**Does the microphone work?** Dictation uses your browser's speech engine (Chrome works best). On `localhost` it works out of the box.

**Is my key safe?** It never leaves your machine and never enters the browser. Don't share your `openrouter.key` or `state.json` publicly.

## License

MIT — do whatever you want, no warranty. If you build something useful on top of it, the author would genuinely love to hear about it.

---

*Built by [Beatriz Belchior](https://www.linkedin.com/in/beatrizbelchior) · [ALIOS ONE](https://aliosone.one)*
