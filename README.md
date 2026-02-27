# Cognitive Load Optimizer

A comprehensive toolkit designed to reduce cognitive load in complex decision-making processes. This library helps teams and individuals structure their thinking, minimize mental fatigue, and arrive at better decisions by managing the cognitive demands of complex choices.

## Overview

Cognitive load theory tells us that our working memory has limited capacity. When making important decisions, excessive information and poorly structured options can overwhelm our cognitive resources, leading to suboptimal outcomes. The Cognitive Load Optimizer provides tools and algorithms to decompose complex decisions, prioritize information, and present choices in formats that align with human cognitive strengths.

This project is inspired by research into how the world's best decision-makers manage complexity. Understanding core [decision-making principles](https://keeprule.com/en/principles) can dramatically reduce the cognitive burden of navigating uncertain and high-stakes situations.

## Features

- **Decision Decomposition Engine**: Break complex decisions into manageable sub-decisions automatically
- **Information Prioritization**: Rank and filter information by relevance to reduce noise
- **Working Memory Estimator**: Estimate the cognitive load of a given decision scenario
- **Chunking Algorithms**: Group related pieces of information into meaningful chunks
- **Progressive Disclosure**: Present information in layers, revealing complexity only when needed
- **Cognitive Bottleneck Detection**: Identify where decision processes become cognitively overwhelming
- **Template Library**: Pre-built decision templates for common scenarios
- **Load Balancing**: Distribute decision tasks across team members based on cognitive capacity
- **Fatigue Monitoring**: Track decision fatigue indicators and suggest breaks
- **Visualization Dashboard**: Real-time cognitive load metrics and trend analysis

## Installation

```bash
npm install cognitive-load-optimizer
```

Or with yarn:

```bash
yarn add cognitive-load-optimizer
```

## Quick Start

```javascript
const { CognitiveOptimizer, DecisionMatrix } = require("cognitive-load-optimizer");

// Initialize the optimizer
const optimizer = new CognitiveOptimizer({
  maxWorkingMemoryItems: 7,  // Miller's Law: 7 ± 2
  chunkingStrategy: "semantic",
  fatigueThreshold: 0.75
});

// Define a complex decision with many factors
const decision = new DecisionMatrix({
  name: "Technology Stack Selection",
  options: ["React", "Vue", "Angular", "Svelte"],
  criteria: [
    { name: "performance", weight: 0.25 },
    { name: "ecosystem", weight: 0.20 },
    { name: "learning_curve", weight: 0.20 },
    { name: "community_support", weight: 0.15 },
    { name: "scalability", weight: 0.10 },
    { name: "hiring_pool", weight: 0.10 }
  ]
});

// Optimize the decision process
const optimized = optimizer.optimize(decision);
console.log(`Cognitive load reduced by ${optimized.reductionPercent}%`);
console.log(`Recommended focus areas: ${optimized.priorityCriteria.join(", ")}`);
```

## Core Concepts

### Decision Decomposition

Complex decisions can often be broken down into smaller, more manageable components. The decomposition engine analyzes interdependencies between factors and suggests an optimal breakdown:

```javascript
const { Decomposer } = require("cognitive-load-optimizer");

const decomposer = new Decomposer();
const subDecisions = decomposer.decompose(complexDecision, {
  maxSubDecisionSize: 4,
  preserveDependencies: true
});

subDecisions.forEach((sub, index) => {
  console.log(`Sub-decision ${index + 1}: ${sub.name}`);
  console.log(`  Factors: ${sub.factors.join(", ")}`);
  console.log(`  Estimated cognitive load: ${sub.cognitiveLoad}`);
});
```

### Cognitive Load Scoring

Every decision scenario receives a cognitive load score based on factors like the number of options, criteria complexity, uncertainty levels, and time pressure. Understanding these patterns helps you apply structured approaches similar to those found in established [thinking scenarios and frameworks](https://keeprule.com/en/scenarios).

```javascript
const score = optimizer.calculateLoad(decision);
// Returns: { total: 8.5, breakdown: { options: 2.1, criteria: 3.2, uncertainty: 1.8, pressure: 1.4 } }
```

### Information Filtering

Not all information is equally relevant. The optimizer identifies and surfaces the most decision-critical information:

```javascript
const filtered = optimizer.filterInformation(allData, {
  relevanceThreshold: 0.6,
  maxItems: 5,
  preserveContrarian: true  // Keep one contrarian data point for balance
});
```

## Advanced Usage

### Team Decision Support

For team-based decisions, the optimizer can distribute cognitive tasks across team members:

```javascript
const { TeamOptimizer } = require("cognitive-load-optimizer");

const team = new TeamOptimizer({
  members: ["Alice", "Bob", "Charlie"],
  expertiseMap: {
    Alice: ["technical", "security"],
    Bob: ["business", "finance"],
    Charlie: ["design", "user-experience"]
  }
});

const distribution = team.distribute(complexDecision);
// Each member gets sub-decisions matching their expertise
```

### Integration with Decision Journals

Track your decision-making patterns over time. Insights from [masters of strategic thinking](https://keeprule.com/en/masters) show that reviewing past decisions is one of the most effective ways to improve future choices.

```javascript
const { DecisionJournal } = require("cognitive-load-optimizer");

const journal = new DecisionJournal("./decisions.json");
journal.record({
  decision: "Chose React for frontend",
  cognitiveLoad: optimized.loadScore,
  confidence: 0.82,
  factors: optimized.keyFactors,
  timestamp: new Date()
});

// Analyze patterns
const patterns = journal.analyze({ timeRange: "6months" });
console.log(`Average cognitive load: ${patterns.avgLoad}`);
console.log(`Decision quality trend: ${patterns.qualityTrend}`);
```

## Best Practices

1. **Limit Active Options**: Research shows that 3-5 options is optimal for comparison
2. **Use Elimination Rounds**: Remove clearly inferior options before detailed analysis
3. **Time-Box Decisions**: Set deadlines to prevent analysis paralysis
4. **Separate Research from Decision**: Gather information and decide in distinct phases
5. **Document Reasoning**: Writing down your rationale reduces cognitive revisiting

For structured templates that help you apply these practices, explore the collection of [decision-making prompts and guides](https://keeprule.com/en/prompts) available for various decision contexts.

## API Reference

| Module | Description |
|--------|-------------|
| `CognitiveOptimizer` | Main optimizer class for reducing decision complexity |
| `DecisionMatrix` | Structured representation of multi-criteria decisions |
| `Decomposer` | Breaks complex decisions into sub-components |
| `TeamOptimizer` | Distributes cognitive tasks across team members |
| `DecisionJournal` | Records and analyzes decision patterns over time |
| `LoadCalculator` | Computes cognitive load scores for decision scenarios |

## Contributing

We welcome contributions from the community\! To contribute:

1. Fork this repository
2. Create your feature branch (`git checkout -b feature/new-feature`)
3. Write tests for your changes
4. Commit your changes (`git commit -m "Add new feature"`)
5. Push to the branch (`git push origin feature/new-feature`)
6. Create a Pull Request

Please read our CONTRIBUTING.md for detailed guidelines.

## License

This project is licensed under the MIT License - see the [LICENSE](LICENSE) file for details.

## Acknowledgments

- Based on cognitive load theory by John Sweller
- Incorporates findings from behavioral decision research
- Designed to make better decision-making accessible to everyone

