# Abhishek Dubey

I build the supervision layer for autonomous coding agents — control planes that keep parallel
agents observable and interruptible, and deterministic gates that decide what a model is
allowed to do with its own output.

Nine years shipping Android. Currently mobile at
[Greenlight](https://play.google.com/store/apps/details?id=me.greenlight), Bengaluru.

## Building

**Crewdeck** — a local-first control plane for parallel coding agents. One detached supervisor
owns every project runtime and fences each by lease identity, restarting under a bounded
crash-loop policy. A headless xterm mirrors every PTY into SQLite, so a reconnecting browser
tab replays exact prior screen state. Agent subprocess environments are rebuilt from an
allowlist, so control-plane tokens never reach an agent. After a crash mid-rollover the daemon
refuses to guess which session won: state becomes `indeterminate` and launch is withheld until
a human resolves it.

**Agentic review gates** — running an LLM reviewer inside a real merge gate on three
production repositories since May 2026. The reviewer writes structured findings and posts
nothing. A **separate** model process then re-reads only those findings and the code they
cite and votes keep or drop — because a claim and its refutation produced in one context share
the same blind spot. A deterministic `bash`/`jq` step applies the confidence threshold, decides
whether anything blocks, and holds the posting credential the agent never sees.

## Selected work

**[QuizGen: AI Quiz & MCQ Test](https://play.google.com/store/apps/details?id=com.quizgenai.app)**
— A production AI quiz app on Google Play, with the backend and release pipeline behind it.
Tech: Kotlin · Jetpack Compose · TypeScript · Fly.io · GitHub Actions
Why it is interesting: 767 and 382 commits across client and backend, 29 tagged releases, and
nine CI workflows — including scheduled content generation and the agentic review gate above.
This is where the agent tooling gets tested against a codebase real users depend on.

**[google-play-screenshot-skill](https://github.com/abhishekdubey331/google-play-screenshot-skill)**
— Turn app UI into store-ready Google Play screenshots and feature graphics.
Tech: Python · agent skill · deterministic composition
Why it is interesting: layout is deterministic and reproducible; the model enhances at the
edges rather than placing pixels.

**[ReviewRadar](https://github.com/abhishekdubey331/ReviewRadar)** — An MCP server that turns
app-store reviews into prioritized product intelligence.
Tech: TypeScript · MCP · vector search · rules + LLM
Why it is interesting: deterministic rules handle what rules handle and the model takes only
the residue, which keeps P0/P1 triage stable across runs.
[Write-up](https://medium.com/towards-artificial-intelligence/build-a-review-analytics-mcp-server-with-typescript-rules-llms-and-vector-search-15a6297e5f2a)

**Liquidity Sprint** *(private)* — A shadow execution lab for a NIFTY options scalp.
Tech: FastAPI · React + Vite · Kite Connect / Dhan · Fly.io
Why it is interesting: there is no live order path in the codebase. Fills are modelled at the
ask and the bid, statutory charges are applied, quantity is hard-capped at one lot, and
completed trades land in append-only JSONL. The apparatus exists to decide whether the edge
survives the spread before any capital moves.

## Technical interests

- Supervising non-deterministic processes: leases, fencing, crash-loop policy, replayable state
- Deterministic gates around model output, and eval baselines before tightening them
- Local-first systems — loopback by default, anything wider is an explicit opt-in
- Safety rails in financial software: shadow modes, circuit-breakers, hard position caps
- Android and Compose at production scale

## Stack

Kotlin · Jetpack Compose · TypeScript · Next.js · Python · FastAPI · Node.js ·
SQLite / DuckDB · GitHub Actions · Fly.io · MCP

## Writing

- [Build a Review Analytics MCP Server with TypeScript, Rules, LLMs, and Vector Search](https://medium.com/towards-artificial-intelligence/build-a-review-analytics-mcp-server-with-typescript-rules-llms-and-vector-search-15a6297e5f2a)
- [Seamless Real-Time Location Tracking with gRPC, Kotlin & Jetpack Compose](https://medium.com/proandroiddev/building-a-real-time-location-streaming-service-with-grpc-and-kotlin-a-better-alternative-to-62563f518cc8)
- [Automate Android Login Workflows with ADB and Python](https://medium.com/proandroiddev/effortless-account-switching-automate-your-android-app-login-flow-with-python-and-adb-8a5aea83924d)
- [Event-Driven Solution in Android Without BroadcastReceiver](https://medium.com/@abhishekdubey331/building-an-event-driven-solution-in-android-without-broadcastreceiver-9ca59c4a0dbf)

## Elsewhere

[Medium](https://medium.com/@abhishekdubey331) ·
[LinkedIn](https://linkedin.com/in/abhishekdubey331) ·
[X](https://x.com/abhidubey331)
