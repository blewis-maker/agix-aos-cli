# Agix AOS

A local agentic operating system. It installs your environment and a team of AI agents on your machine, then helps you build toward your north star.

Agix AOS runs entirely on your computer. The `agix` CLI sets up a local knowledge fabric, a `wiki/`, and an instance identity, then stands up a fleet of agents you can put to work. There's no account to create and no data leaves your machine — if you have Claude Code or OpenAI Codex installed and signed in, Agix uses that, so no API key is required.

## Install

```sh
brew tap blewis-maker/agix
brew trust blewis-maker/agix
brew install agix-aos
agix            # first run: onboards you + sets up your environment
```

Homebrew installs Node for you. Rust is used at install time to build the local agent bus, and Homebrew handles that too.

## First run

The first time you run `agix`, an onboarding session walks you through setup:

- It captures your **north star** — what you're trying to build or solve.
- It provisions your local environment: a knowledge fabric, a `wiki/`, and your instance identity.
- It stands up your agent fleet.

No API key needed if you have Claude Code or OpenAI Codex installed and signed in — Agix uses your existing CLI for model access. Otherwise, you can set an API key.

Once onboarded, the two entry points are:

```sh
agix agent run sensei    # a guided session toward your north star
agix agent list          # see your agent fleet
```

## The agent fleet

- **sensei** — your strategic mentor and session conductor.
- **architect** — system and solution design.
- **research** — gathers and synthesizes sources.
- **onboarding** — first-run setup.
- **git-orchestrator** — git workflow.
- **tester** — writes and runs tests.
- **investigator** — root-cause debugging.
- **context-warden** — keeps your working context coherent.

## Your data and privacy

Agix AOS is local-first. State lives under your home directory (`~/.config/agix` and related paths), and there is no telemetry — nothing is sent anywhere.

These agents are autonomous and act on your machine: they can read and write files and run commands. Review an agent before you run it, and treat its capability the way you'd treat any tool with shell access. If you're using Claude Code or Codex for model access, running agents makes real model calls that count against that account's usage.

## Requirements

- macOS. Linux is in beta and unverified end-to-end.
- Homebrew (installs Node automatically). Rust is needed only at install time and is handled by Homebrew.
- Optional: Claude Code or OpenAI Codex, installed and signed in, for zero-API-key use.

## License

Apache-2.0.
