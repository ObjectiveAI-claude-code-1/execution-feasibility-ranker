# Execution Feasibility Ranker

A vector function that ranks startup ideas by relative execution feasibility, producing a probability distribution where higher values indicate more feasible paths from idea to market.

## Overview

The Execution Feasibility Ranker evaluates multiple startup ideas simultaneously and produces a comparative ranking. Rather than scoring each idea in isolation, it assesses them relative to each other—recognizing that feasibility is contextual. An idea requiring $10M in capital might be "infeasible" compared to a bootstrappable SaaS, but "highly feasible" compared to a moon-landing venture.

## Input

The function accepts an array of 2 or more startup ideas. Each idea can be:

- **Text**: A string describing the startup pitch
- **Image**: A visual pitch (mockup, diagram, prototype photo)
- **Audio**: An audio pitch or demonstration
- **Video**: A video pitch or demo
- **Composite**: An array combining multiple formats for a single idea

```json
{
  "items": [
    "A mobile app for habit tracking with streaks and reminders",
    "A biotech platform using CRISPR for personalized cancer treatment",
    ["An AI writing assistant", {"type": "image_url", "image_url": {"url": "..."}}]
  ]
}
```

## Output

A vector of probabilities summing to approximately 1, with one score per input idea. Higher scores indicate higher relative execution feasibility.

```json
[0.55, 0.15, 0.30]
```

## Evaluation Criteria

The ranker evaluates ideas across four dimensions:

### 1. Technical Feasibility
- **Technology maturity**: Established technology vs. unproven breakthroughs
- **Integration complexity**: How many systems must work together
- **Talent availability**: Generalists vs. rare specialists required
- **MVP buildability**: Can a prototype be built quickly with current tools

### 2. Resource Requirements
- **Capital intensity**: Bootstrappable vs. massive funding required
- **Time to market**: Months vs. years of development
- **External dependencies**: Partnerships, regulatory relationships, platform access
- **Team requirements**: Small generalist team vs. large specialized organization

### 3. Regulatory Complexity
- **Regulatory burden**: Unregulated software vs. heavily regulated industries
- **Jurisdictional complexity**: Single vs. multi-jurisdiction compliance
- **Legal defensibility**: Patent risks, liability exposure, platform constraints
- **Approval timelines**: Immediate launch vs. lengthy approval processes

### 4. Execution Risk Profile
- **Path clarity**: Established playbooks vs. unclear success criteria
- **Risk interdependence**: Independent challenges vs. cascading risks
- **Domain knowledge**: Well-understood vs. uncharted territory
- **Failure modes**: Pivot-friendly vs. catastrophic failure potential

## Use Cases

- **Founders**: Compare multiple startup directions before committing
- **Accelerators**: Evaluate applicant ideas for realistic market paths
- **Investors**: Screen deals for execution risk during due diligence
- **Corporate Innovation**: Allocate innovation budgets to feasible projects
- **Educators**: Teach entrepreneurship with concrete comparisons

## Philosophy

This function embodies pragmatism over purity. It doesn't ask "is this a good idea?" or "will this succeed?" It asks only "which of these ideas presents the clearest path to execution?" The probability distribution output communicates both rankings and confidence—tight distributions suggest clear hierarchies, while spread distributions suggest near-equivalence.
