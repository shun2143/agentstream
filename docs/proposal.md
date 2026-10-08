# AgentStream

_AI agents pay each other per-second in USDC for data, compute, and content on Solana_

## Summary

AgentStream lets autonomous AI agents open real-time payment streams to other agents or APIs, paying only for the exact seconds of compute, data, or content they consume. It uses Solana's speed and low fees to settle thousands of micro-payments per minute between agents, with a simple SDK so any developer can monetize an AI agent or API instantly.

## Target users

AI agent developers, API providers, and builders of autonomous agent economies

## Problem

As AI agents increasingly call other agents and APIs autonomously, there's no fast, trust-minimized way for them to pay per use without human intervention or subscriptions.

## Solution

A Solana-based streaming payment protocol (using token streaming + agent identity) that lets agents open, meter, and close USDC payment streams programmatically via a simple SDK and on-chain escrow.

## MVP features

- SDK to open/close per-second USDC payment streams between two wallets/agents
- On-chain escrow program that releases funds proportionally to elapsed usage time
- Agent identity + reputation registry using Solana accounts
- Dashboard to monitor live streams, spend rate, and balances
- Example integration: pay-per-token LLM proxy that bills via AgentStream

## Chains

Solana

## Tech

Anchor, Rust, Solana Pay, USDC (SPL Token), Next.js, TypeScript SDK

## Category

AI

## Why now

Agentic AI and machine-to-machine commerce are exploding, and existing payment rails (cards, subscriptions) are too slow and human-centric for autonomous agents transacting at machine speed.

## Roadmap

- Add support for streaming other SPL tokens and stablecoins
- Build marketplace/discovery layer for paid agent services
- Partner with AI agent frameworks (e.g. LangChain, ElizaOS) for native integration
