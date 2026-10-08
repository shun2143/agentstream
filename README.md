# AgentStream
![AgentStream logo](assets/logo.png)

**AI agents pay each other per-second in USDC for data, compute, and content on Solana**

## Overview
AgentStream lets autonomous AI agents open real-time payment streams to other agents or APIs, paying only for the exact seconds of compute, data, or content they consume. It uses Solana's speed and low fees to settle thousands of micro-payments per minute between agents, with a simple SDK so any developer can monetize an AI agent or API instantly.

## Problem
As AI agents increasingly call other agents and APIs autonomously, there is no fast, trust-minimized way for them to pay per use without human intervention or subscriptions. Cards and subscriptions are built for humans, not for machine-speed, second-by-second billing.

## Solution
A Solana-based streaming payment protocol, combining token streaming with agent identity, that lets agents open, meter, and close USDC payment streams programmatically via a simple SDK and on-chain escrow.

## Features (MVP)
- SDK to open/close per-second USDC payment streams between two wallets/agents
- On-chain escrow program that releases funds proportionally to elapsed usage time
- Agent identity + reputation registry using Solana accounts
- Dashboard to monitor live streams, spend rate, and balances
- Example integration: a pay-per-token LLM proxy that bills via AgentStream

## Tech Stack
- Anchor, Rust (on-chain escrow program)
- Solana Pay, USDC (SPL Token)
- Next.js, TypeScript SDK (dashboard + client SDK)

## How It Works
```
Agent A (payer)                Solana Escrow Program            Agent B / API (payee)
     |                                 |                                |
     | 1. open_stream(amount, rate) -->|                                |
     |                                 |-- locks USDC in escrow ------>|
     |                                 |                                |
     | 2. usage happens (tokens, calls, data) over time               |
     |                                 |<-- meter elapsed seconds ------|
     |                                 |-- releases USDC proportionally->
     |                                 |                                |
     | 3. close_stream() ------------>|                                |
     |<-- unused USDC refunded --------|                                |
```
Agents call the SDK to open a stream, which creates an on-chain escrow account holding USDC. As time elapses, the escrow program releases funds proportionally to the payee. Either party can close the stream at any time; any unused balance is refunded to the payer. Agent identity and reputation are tracked via Solana accounts, and the dashboard surfaces live stream status, spend rate, and balances.

## Roadmap
- Add support for streaming other SPL tokens and stablecoins
- Build a marketplace/discovery layer for paid agent services
- Partner with AI agent frameworks (e.g. LangChain, ElizaOS) for native integration

## Pitch
See our one-pager and spoken pitch:
- [Pitch deck (PDF)](docs/pitch.pdf)
- [Pitch script](docs/pitch-script.md)

## Team
- [Name] — Role (placeholder)
- [Name] — Role (placeholder)
- [Name] — Role (placeholder)

Built for the Colosseum hackathon.

---

🎬 Pitch video: [docs/pitch-video.mp4](docs/pitch-video.mp4)


## Prototype

Live prototype: https://shun2143.github.io/agentstream/

The source is [docs/index.html](docs/index.html) (served with GitHub Pages from the /docs folder). All data is simulated.
