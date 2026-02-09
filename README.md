# Execution Feasibility Ranker

A vector function that evaluates startup ideas simultaneously to assess their relative feasibility and executability, producing a probability distribution where higher scores indicate more executable ideas.

## Overview

The Execution Feasibility Ranker compares multiple startup ideas and ranks them by how realistically they can be transformed from concept to functioning business. Unlike absolute scoring functions, this operates in the comparative domain—producing scores that reflect how feasible each idea is *relative to the alternatives presented*.

## Input

An object with an `items` field containing an array of startup ideas to compare (minimum 2 items):

```json
{
  "items": [
    "An AI-powered personal stylist using computer vision.",
    "A biotech platform using CRISPR for cancer treatment.",
    "A simple mobile app for daily habit tracking."
  ]
}
```

Each item can be:
- **String**: A text pitch describing the startup idea
- **Image**: A visual pitch (slide, mockup, diagram)
- **Video**: A video pitch
- **Audio**: An audio pitch
- **Array**: A composite pitch combining multiple modalities

## Output

A vector of scores (one per item) summing to approximately 1, representing relative execution feasibility:

```json
[0.15, 0.05, 0.80]
```

Higher scores indicate more executable ideas. In the example above, the habit tracking app (0.80) is ranked as most feasible, followed by the AI stylist (0.15), with the CRISPR platform (0.05) ranked as least feasible to execute.

## Evaluation Criteria

The function evaluates ideas across four dimensions:

### 1. Technical Feasibility
- Technology maturity: established vs. unproven breakthroughs
- Integration complexity: how many systems must work together
- Technical talent availability: generalists vs. rare specialists
- MVP buildability: speed and ease of prototyping

### 2. Resource Requirements
- Capital intensity: bootstrappable vs. capital-intensive
- Time to market: months vs. years of development
- External dependencies: partnerships, regulatory relationships
- Talent requirements: small generalist team vs. large specialized team

### 3. Regulatory and Legal Complexity
- Regulatory burden: unregulated vs. heavily regulated
- Jurisdictional complexity: single vs. multi-jurisdiction
- Legal defensibility: patent risks, liability exposure
- Approval timelines: immediate launch vs. lengthy approvals

### 4. Execution Risk Profile
- Path clarity: established playbooks vs. uncharted territory
- Risk interdependence: independent vs. cascading risks
- Known vs. unknown risks: well-understood vs. unknown unknowns
- Failure modes: pivotable vs. catastrophic

## Use Cases

- **Investment Screening**: Triage opportunities by execution difficulty
- **Founder Self-Assessment**: Reality-check multiple directions
- **Accelerator Selection**: Input for cohort selection with execution focus
- **Portfolio Construction**: Balance feasibility profiles across investments
- **Competitive Analysis**: Assess which competitors pursue more feasible strategies

## Limitations

- Maximum 10 items can be compared at once
- Minimum 2 items required for comparison
- Evaluates ideas in the abstract, not specific team/founder fit
- Focuses on execution difficulty, not market potential or investment attractiveness
