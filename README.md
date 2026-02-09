# Execution Feasibility Ranker

A vector function that evaluates and ranks startup ideas by their execution feasibility, producing a probability distribution across all input items.

## Overview

The Execution Feasibility Ranker compares multiple startup ideas simultaneously and determines their relative feasibility of being successfully built and brought to market. Unlike absolute scoring systems, this ranker provides comparative rankings—distributing a fixed probability mass across all ideas to answer: "If I had to bet on which of these could actually be executed, how would I allocate my confidence?"

## Input

The function accepts an object with an `items` array containing 2 or more startup ideas. Each item can be:

- **Text pitch**: A string describing the startup idea
- **Image pitch**: A visual representation (slide, mockup, diagram)
- **Audio pitch**: A spoken presentation or voice memo
- **Video pitch**: A recorded demo or presentation
- **Composite pitch**: An array combining multiple modalities

### Example Input

```json
{
  "items": [
    "An AI-powered personal stylist app that uses computer vision",
    "A biotech platform using CRISPR for personalized cancer treatment",
    "A simple mobile app for daily habit tracking with reminders"
  ]
}
```

## Output

A vector of scores (one per input item) that sum to approximately 1. Higher scores indicate greater execution feasibility relative to the other items in the set.

### Example Output

```json
[0.22, 0.18, 0.60]
```

In this example, the habit tracking app receives the highest feasibility score, while the CRISPR biotech platform receives the lowest.

## Evaluation Criteria

The ranker evaluates each idea across four dimensions:

### 1. Technical Feasibility
- **Technology maturity**: Does it use established technology or require unproven breakthroughs?
- **Integration complexity**: How many systems must work together?
- **Talent availability**: Can generalist engineers build this, or are rare specialists required?
- **MVP buildability**: Can a working prototype be built quickly with current tools?

### 2. Resource Requirements
- **Capital intensity**: Can it be bootstrapped, or does it require massive funding?
- **Time to market**: Can it launch in months, or does it require years of development?
- **External dependencies**: Does it require partnerships, regulatory relationships, or platform access?
- **Talent requirements**: Does it need a large specialized team or can a small team execute?

### 3. Regulatory Complexity
- **Regulatory burden**: Is it unregulated (standard software) or heavily regulated (healthcare, finance)?
- **Jurisdictional complexity**: Can it operate in one jurisdiction or must it comply across many?
- **Legal defensibility**: Are there patent risks, liability exposure, or platform constraints?
- **Approval timelines**: Does it require lengthy approval processes (FDA, FAA)?

### 4. Execution Risk Profile
- **Path clarity**: Are there established playbooks, or is success criteria unclear?
- **Risk interdependence**: Can challenges be tackled independently, or do risks cascade?
- **Known vs unknown risks**: Is this a well-understood domain or uncharted territory?
- **Failure modes**: Can the company pivot if things go wrong?

## Use Cases

- **Startup portfolio evaluation**: Compare investment opportunities by execution risk
- **Idea prioritization**: Determine which product concept to pursue first
- **Competitive analysis**: Assess relative feasibility of different market approaches
- **Resource allocation**: Distribute team attention across multiple initiatives
- **Pitch deck review**: Provide structured feedback on startup proposals

## Notes

- **Feasibility ≠ Desirability**: A terrible idea can be highly feasible. This ranker assesses whether something CAN be built, not whether it SHOULD be.
- **Feasibility ≠ Profitability**: Many feasible businesses fail to make money. The ranker assesses execution possibility, not market success.
- **Relative ranking**: Scores are comparative within each input set. The same idea may score differently when compared against different alternatives.
- **Presentation-agnostic**: The ranker evaluates the underlying idea, not the quality of its presentation.
