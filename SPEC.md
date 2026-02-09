# Execution Feasibility Ranker

A vector function that evaluates all startup ideas simultaneously to assess their relative feasibility and executability.

## Input Schema

The input is an object with an `items` field containing an array of startup ideas to compare. Each item can be:
- A string (text pitch)
- An image, audio, or video (multimodal pitch)
- An array of the above (composite pitch)

```json
{
  "items": [
    "An AI-powered personal stylist.",
    "A biotech platform using CRISPR for cancer treatment.",
    "A simple mobile app for habit tracking."
  ]
}
```

## Output

A vector of scores (one per item) summing to ~1, representing relative execution feasibility. Higher scores indicate more executable ideas.

## Output Length

Dynamic - equals the number of items in the input array.

## Evaluation Criteria

This is comparative - feasibility is relative to alternatives:

1. **Technical Feasibility**: Which ideas require existing technology vs. unproven breakthroughs? Rank by technical ambition.

2. **Resource Requirements**: Compare capital requirements (bootstrappable vs. capital-intensive), talent needs, time-to-market.

3. **Regulatory and Legal Complexity**: Compare regulatory hurdles. Which ideas are safer from a legal perspective?

4. **Execution Risk Profile**: Rank by directness of path to market. Compare known vs. unknown risks and failure modes.