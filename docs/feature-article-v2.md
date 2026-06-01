# Engagement Stack: A Human-First Career OS With an Agent in the Sidecar

*Why your professional life needs an agent surface — and what happens when your Career OS starts feeding your job search.*

The traditional resume is too small for modern professional life.

An engineer's real market signal is scattered across work history, GitHub repositories, live products, architecture notes, shipped artifacts, testimonials, references, stated preferences, hard constraints, and the actual shape of the opportunities they want next. A PDF carries a sliver of that. A LinkedIn profile carries a different sliver. Neither is a maintained source of truth — and, more to the point in 2026, neither can be read by an agent.

That last part is the problem worth solving.

## The agent surface

Dan Shipper, who runs Every, has spent the last two years arguing that AI doesn't shrink the amount of human work — it moves it. In *The Knowledge Economy Is Over. Welcome to the Allocation Economy*, he makes the case that once models commoditize yesterday's competence, the scarce skill becomes allocation: deciding what to point an agent at, and judging what it brings back. His colleague Kieran Klassen calls the shape of the new workflow the **human sandwich** — a person frames the task at the front, an agent compresses hours into minutes in the middle, and a person evaluates the result at the back. Shipper's blunter version: every agent needs a human, and the further an agent runs from human oversight, the worse it gets.

Buried in that work is a corollary that matters for everyone, not just software companies. If agents are going to do real work on your behalf, the things they act on have to be legible to them. Shipper's point about software in the agent era is that a product now has to be usable by humans and agents at the same time — same product, same data, two kinds of reader. Call that an **agent surface**: a structured face on something that a person can read and an agent can act on, with neither one a second-class citizen.

Most of the digital world doesn't have one yet. Your career certainly doesn't.

## Build it human-first, with the agent in the sidecar

Engagement Stack is an agent surface for your professional life. It's a human-first, agent-readable career dossier: Markdown for people, YAML for agents, evidence-backed project claims, explicit engagement preferences, structured offer requests, evaluation rubrics, resume shaders, and platform-specific submission adapters — all in one versioned repository.

*Human-first* is the load-bearing word. The Markdown is the source of truth a person writes and reads; the YAML rides alongside it as the machine-readable twin, generated from the same canonical facts. This is the opposite of an autopilot that files your applications while you sleep. It's a sidecar: you drive, your agent rides beside you reading the same dashboard, and you keep both hands on the wheel. The human sandwich isn't a limitation to design around here — it's the operating principle. The stack is built so a human frames and approves while the agent does the legwork in between.

Shipper himself has grown skeptical that every employee inside a company needs a personal agent; he now expects organizations to converge on one shared "super agent." Fair — for an employee. But your career isn't an employee inside one company. It's a single identity transacting across dozens of opportunities, employers, and clients over decades. That is exactly the case where a personal, portable, agent-readable surface earns its keep.

## Canonical facts in, scoped outputs out

The core mechanic is simple: keep canonical facts stable, then generate scoped outputs from them.

You maintain one canonical CV. Then you apply a resume shader for an AI-platform role, a federal technology role, a fractional-CTO engagement, or a developer-tools staff position. The shader changes emphasis, language, ordering, and output target. It does not rewrite history.

This is the allocation economy in miniature. You supply the situated taste — which role, which framing, which opportunity is worth your time — and the agent renders against it. You allocate; it produces. The repo is the website, too: GitHub renders the Markdown and cross-linked documents with no publishing step, and a CI run can emit PDF, DOCX, and TXT with Pandoc when you need a traditional artifact.

## What happens when it feeds your job search

A dossier that only sits there is just a nicer resume. The whole point of an agent surface is that *other* agents can drink from it.

The first one that does is **Job Search Superpower** — a companion prompt that reads your Engagement Stack and returns strategy: positioning, target roles, an honest hop-length on each pivot you're considering, and recommended shaders for the openings actually worth pursuing. Your durable Career OS feeds the strategy surface.

Then the loop closes. Job Search Superpower hands back an advisory export — a human-readable report plus a YAML packet — that your stack can ingest *after you've reviewed it*. Strategy on top, source of truth underneath, a human approving the handoff in between. The human sandwich again, this time spanning two tools instead of one.

That division of labor is deliberate. The job-search prompt stays the volatile, opinionated strategy layer. Engagement Stack stays the durable, slow-moving record. Neither tries to be the other, and the human signs off before anything the agent recommends becomes a fact.

## Have your agent call mine

The surface points outward as well as in. Engagement Stack defines an intake surface: a potential employer or client can submit an engagement request by email with a structured subject line and an optional YAML packet. A human can read it. An agent can parse it. Missing fields trigger clarification before evaluation — and the evaluation itself can be explicit. Prefer remote but accept hybrid for exceptional work; prefer full-time but consider contract at a premium. Those trade-offs live as both human-readable priorities and agent-readable scoring rules.

*Have your agent call mine.* That stops being a joke the moment both sides have a real surface to call.

None of this requires putting your whole life in public. The public repo can state that private thresholds exist while ignored local overlays hold the actual salary floors, negotiation strategy, work-authorization details, and sensitive constraints. The browseable face stays curated; the decision model stays complete for the one agent that works for you.

This is not just a job-search toolkit. It's a professional operating system for the agent era — the human-first kind, where the agent rides in the sidecar and you keep the wheel.

---

*The allocation economy, the agent surface, and the "human sandwich" are drawn from Dan Shipper and his colleagues at Every — see [The Knowledge Economy Is Over. Welcome to the Allocation Economy](https://every.to/chain-of-thought/the-knowledge-economy-is-over-welcome-to-the-allocation-economy) and [After Automation](https://every.to/p/after-automation). The "human sandwich" framing is Kieran Klassen's.*
