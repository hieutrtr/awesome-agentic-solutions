# Finance Guru™ - Overview

## Executive Summary

Finance Guru™ is an AI-powered personal family office system that transforms Claude into a team of 8 specialized financial agents working collaboratively to provide institutional-grade investment analysis. Built on the BMAD-CORE™ v6 architecture, it eliminates the complexity of juggling multiple browser tabs and tools by offering coordinated multi-agent analysis through a single command interface.

The project distinguishes itself through its CLI-first design philosophy, where 11 production-ready Python tools handle heavy quantitative calculations outside the LLM context, ensuring token efficiency while providing comprehensive risk metrics, technical analysis, and portfolio optimization capabilities. All data stays local on the user's machine, making it ideal for privacy-conscious individual investors.

With 111 GitHub stars and active development, Finance Guru represents an innovative approach to personal financial analysis—delivering the coordination and judgment typically reserved for wealthy family office clients through AI-powered agent collaboration. However, it requires Claude Code platform and multiple MCP server dependencies, making it best suited for technically proficient users comfortable with terminal-based workflows.

## Technology Stack

- **Primary Language**: Python 3.12+
- **Key Technologies**: Pydantic (type-safe validation), pandas/numpy/scipy (data analysis), yfinance (market data), Streamlit (visualization)
- **Framework/Platform**: Claude Code with BMAD-CORE™ v6 agent architecture
- **Build Tools**: uv (Python package manager), Bun (JS runtime for auxiliary tools)
- **Testing**: pytest with pytest-cov (coverage reporting)

## Primary Use Cases

1. **Portfolio Risk Analysis**: Calculate comprehensive risk metrics (VaR, CVaR, Sharpe, Sortino, Max Drawdown, Beta, Alpha) for investment holdings with educational context explaining each metric.

2. **Investment Decision Support**: Get coordinated multi-agent analysis for decisions like "Should I add more TSLA?" where Market Researcher, Quant Analyst, Strategy Advisor, and Compliance Officer collaborate to provide holistic recommendations.

3. **Portfolio Optimization**: Utilize Max Sharpe, Risk Parity, Min Variance, and Black-Litterman optimization methods with position limit controls to determine optimal asset allocations.

## Key Pros & Cons

**Pros:**
- **Comprehensive Tooling**: 11 production-ready CLI tools covering risk, technical, and portfolio analysis with educational documentation explaining the math behind each metric
- **Token Efficiency**: CLI-first architecture keeps heavy computation outside LLM context, leaving 51% free context for actual work
- **Privacy-First**: All data stays local on user's machine—no external data sharing required

**Cons:**
- **Platform Lock-in**: Requires Claude Code platform for full multi-agent functionality
- **Complex Setup**: Multiple dependencies including MCP servers (exa, bright-data, sequential-thinking), Docker, and Python packages
- **Small Community**: Only 2 contributors and limited ecosystem compared to established financial analysis platforms

## Main Alternatives

- **OpenBB Terminal**: Open-source investment research platform with broader data sources and larger community. Choose if you need extensive data access without AI agent coordination.
- **QuantConnect**: Cloud-based algorithmic trading platform with serious backtesting capabilities. Choose for algorithmic trading at scale with language-agnostic support.
- **TradingAgents**: Research-focused multi-agent trading framework. Choose for academic/research purposes or if not using Claude Code platform.

---

*Analysis generated: 2026-01-15*
*Source: https://github.com/AojdevStudio/Finance-Guru*
