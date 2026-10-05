# Agent Survival Arena V3

Long-running 100-agent evolutionary economy.

## Core rules
- 100 organisms
- A$0 real starting cash per organism
- Hourly action cycles
- 70% cull at the daily selection
- 50 mutated descendants + 10 crossover descendants + 10 novelty organisms
- Alliances of 2-4 agents
- Verified external revenue dominates fitness
- 25% of verified earned revenue may become agent reinvestment; 75% goes to the central treasury
- Live spending is disabled by default
- The owner's A$100 reserve is not distributed to agents

## Budget policy
The configured A$100 reserve is modeled as:
- A$50 emergency reserve
- A$20 infrastructure/API ceiling
- A$30 traction fund reserved for validated experiments

None of those pools are autonomously spendable in V3. Organisms start from zero and only earned, verified revenue can unlock reinvestment.

## Free-model routing
The scheduler can use these GitHub Actions secrets when present:
- ARENA_GROQ_API_KEY
- ARENA_GEMINI_API_KEY
- ARENA_OPENROUTER_API_KEY
- ARENA_POLLINATIONS_API_KEY

Optional paid OpenAI escalation exists but is OFF unless both ARENA_OPENAI_API_KEY is configured and ARENA_ALLOW_PAID_OPENAI=true.

If no provider key is available or a free quota is exhausted, the organism falls back to the offline evolutionary brain rather than charging anything.

## Persistent state
Runtime state and reports are written to the `arena-state` branch under:
`arena-v3/state/`

Latest machine-readable report:
`arena-v3/state/report.json`

## Real-world safety boundary
No autonomous spam, impersonation, credential abuse, fake reviews, privacy invasion, account farming, malware/exploitation, regulated-goods sales, gambling/speculation, or attempts to bypass safeguards.

Payment/contact rails are not enabled unless explicitly configured. Revenue is only counted as real when ingested as a verified revenue event.
