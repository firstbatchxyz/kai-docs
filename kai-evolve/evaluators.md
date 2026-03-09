# Evaluators

Evaluators are the scoring functions that determine whether an evolved solution is better than the original. They measure performance, verify correctness, and rank candidates. Without a good evaluator, Evolve can't distinguish a genuine improvement from a regression.

## How Evaluators Work

During each iteration of an evolution:

1. The LLM generates a new candidate program
2. The evaluator runs against the candidate
3. A fitness score is produced
4. The score determines whether the candidate survives to the next generation

This feedback loop is what drives the evolutionary process. The evaluator provides the objective, quantifiable assessment that lets Evolve improve systematically rather than randomly.

Evaluators run in Kai's cloud infrastructure alongside the evolution, so they don't require any local setup.

## Evaluator Strategies

Kai supports three approaches to evaluation.

### Auto-Generated

Kai analyzes your code scopes and automatically generates evaluators that:
- Measure execution time and throughput
- Verify correctness against expected outputs
- Compare results with the original implementation
- Score candidates across multiple dimensions

This is the default strategy and works well for most optimization tasks. Kai uses LLM-based analysis to understand what your code does and creates an evaluator that captures the right performance characteristics.

### Existing

If you already have benchmark scripts, test harnesses, or evaluation functions in your repository, you can point Evolve to them directly. This is useful when:
- You have established performance benchmarks
- Your evaluation criteria are complex or domain-specific
- You want full control over how solutions are scored

In the manual start flow, specify the file path to your evaluator. In the guided flow, Kai detects existing evaluators and suggests them where appropriate.

### LLM Only

For exploratory optimizations where formal benchmarking is difficult, Kai can use LLM-based scoring. The LLM evaluates the evolved code based on code quality, algorithmic complexity analysis, and pattern recognition against known optimizations.

This strategy is less precise than automated benchmarking but useful for early exploration or when the cost of writing a formal evaluator outweighs the optimization target.

## Evaluator Generation

When you select the auto-generated strategy, Kai:

1. Analyzes the code scopes you've selected
2. Identifies inputs, outputs, and expected behavior
3. Generates a scoring function that captures performance characteristics
4. Validates the evaluator against your existing code before starting the evolution

You can track evaluator generation progress during the [evaluator review step](getting-started#3-evaluators) of the setup flow.

## Custom Scopes

Evaluators are tied to specific code scopes: the file and line ranges that Evolve will optimize. When configuring scopes, you define exactly which parts of your code the evaluator should measure.

Narrower scopes produce more focused optimizations. Broader scopes give Evolve more room to discover structural improvements but require evaluators that can measure the impact across a larger surface area.

## Next Steps

- [Getting Started](getting-started) - Walk through the full evolution setup flow
- [Understanding Results](understanding-results) - Interpret fitness scores and evolution metrics
