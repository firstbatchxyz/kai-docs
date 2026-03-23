# Kai Evolve

**Evolutionary search that discovers faster implementations. Profiles hotspots, benchmarks alternatives, delivers the winner.**

Kai Evolve pairs the creative problem-solving capabilities of frontier LLMs with automated evaluators, using an evolutionary framework to iteratively improve upon the most promising solutions. Fitness-function optimization with real benchmark validation across hundreds of autonomous iterations. Evidence in every PR.

## The Core Idea

Traditional optimization requires a human to analyze code, hypothesize an improvement, implement it, and test it. This is slow and limited by individual expertise. Kai Evolve replaces this manual cycle with an automated evolutionary loop:

1. **Analyze**: AI agents scan your repository to understand code structure and identify optimization candidates
2. **Evaluate**: Automated evaluators are generated to objectively measure each solution's performance
3. **Evolve**: LLMs propose improved implementations. The best solutions survive and inform the next generation of proposals. This cycle repeats across hundreds of iterations
4. **Verify**: Every improvement is validated against the evaluators to ensure correctness

Because LLMs can draw on broad programming knowledge and the evolutionary framework provides objective feedback, Evolve often discovers optimizations that no single engineer would consider: novel memory access patterns, unconventional algorithmic decompositions, or subtle restructurings that unlock significant speedups.

The approach is general-purpose. Any problem whose solution can be expressed as code and automatically evaluated is a candidate for evolution.

## Where to Use Kai Evolve

Kai Evolve is available across all Kai surfaces:

- **[Web Dashboard](../platform/web-dashboard)**: Walk through the guided setup, monitor evolution progress, review results, and compare runs
- **[MCP Server](../platform/mcp-server)**: Start evolutions, check progress, and retrieve programs programmatically from any MCP-compatible client

## Next Steps

- [Getting Started](getting-started) - Walk through starting your first evolution
- [Understanding Results](understanding-results) - Read fitness charts, compare programs, and apply improvements
- [Evaluators](evaluators) - How Kai scores and verifies evolved code
