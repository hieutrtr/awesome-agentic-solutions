# Vibe Kanban - Overview

## Executive Summary

Vibe Kanban is an open-source AI coding agent orchestration platform that addresses the emerging "human orchestration bottleneck" in AI-assisted software development. As coding agents like Claude Code, Codex, and Gemini CLI become increasingly capable of writing code, the limiting factor shifts to task planning, parallelizing work across agents, reviewing outputs safely, and integrating changes back into real repositories. Vibe Kanban provides a Kanban-style interface to manage this workflow, enabling developers to run multiple coding agents in parallel or sequence, review diffs, and merge changes efficiently.

Built with a robust technology stack (Rust backend with Axum, React/TypeScript frontend), Vibe Kanban implements a local-first architecture that can be run instantly via NPX. Its core innovation is the use of git worktrees for task isolation, ensuring each agent attempt operates in its own branch without interfering with other work. The project supports 9 different coding agents and offers centralized MCP (Model Context Protocol) configuration management.

With 8.6k GitHub stars and active development, Vibe Kanban represents a maturing solution for developers and teams looking to scale their AI-assisted development workflows. While it excels at multi-agent orchestration and safe parallel execution, users should be aware of its polyglot toolchain requirements and the inherent complexity of managing multiple AI agents simultaneously.

## Technology Stack

- **Primary Language**: Rust (44.75%) + TypeScript/TSX (30.44%)
- **Backend**: Axum (Rust async web framework) + Tokio runtime + SQLx (SQLite/Postgres)
- **Frontend**: React 18 + Vite + Tailwind CSS + TanStack Query + Zustand
- **Build Tools**: Cargo (Rust workspace) + pnpm (Node workspace) + Vite bundler
- **Real-time Updates**: WebSocket JSON Patch (RFC6902) streaming
- **Deployment**: NPX CLI, Docker, or self-hosted server

## Primary Use Cases

1. **Multi-Agent Task Orchestration**: Run multiple coding agents (Claude Code, Codex, Gemini CLI, Amp, etc.) against well-scoped tasks in parallel or sequence, then review and compare outputs.

2. **Safe Isolated Development**: Each task attempt runs in an isolated git worktree with its own branch, preventing cross-task interference and enabling safe experimentation.

3. **Centralized Agent Configuration**: Manage MCP server configurations for all supported coding agents from a single interface, standardizing tooling across projects and teams.

4. **Rapid Review & Integration Loop**: View diffs, start dev servers, open worktrees in your editor (with remote SSH support), and merge/push/PR changes all from within the Vibe Kanban UI.

## Key Pros & Cons

**Pros:**
- **Strong isolation model** via git worktrees enables safer parallel agent runs without cross-task interference
- **Multi-agent flexibility** with support for 9 different coding agents and easy switching between them
- **Instant deployment** via `npx vibe-kanban` with no complex setup required for local use
- **Performant architecture** with Rust backend, proactive DB optimizations, and efficient WebSocket streaming

**Cons:**
- **Polyglot complexity** requires familiarity with Rust, Node/pnpm, and Docker for full development setup
- **Linux filesystem watching limitations** can cause performance issues with large monorepos (inotify constraints)
- **Limited frontend test coverage** with no visible Jest/Vitest/Playwright setup in the codebase
- **SQLite concurrency constraints** may limit throughput in high-write scenarios for the local deployment

## Main Alternatives

- **Aider**: Terminal-based AI pair programmer for git repos. Choose when you want a single fast CLI assistant per session without multi-agent orchestration overhead.

- **Cursor**: AI-native code editor built on VS Code. Choose when you want an integrated all-in-one AI editing experience rather than coordinating multiple external agent CLIs.

- **Continue.dev**: Open-source IDE extension for multi-model chat/autocomplete. Choose when you want a customizable in-editor assistant with strong context control.

- **GitHub Copilot Workspace**: Task-centric GitHub environment. Choose when you're standardized on GitHub and want issue-driven planning tightly integrated with PRs.

- **OpenHands (formerly OpenDevin)**: Open-source autonomous dev agent platform. Choose when you want a single powerful self-hosted agent for experimentation rather than multi-vendor coordination.

---

*Analysis generated: 2025-12-30*
*Source: https://github.com/BloopAI/vibe-kanban*
