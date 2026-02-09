# Execution Feasibility Ranker

A vector function that evaluates all startup ideas simultaneously for relative feasibility.

## Input Schema

The input is an object with an `items` field containing an array of startup ideas. Each item uses anyOf to accept:
- A string (text pitch)
- An image (type: image)
- An audio (type: audio)
- A video (type: video)
- An array of the above (composite pitch)

Example input schema structure:
```json
{
  "type": "object",
  "properties": {
    "items": {
      "type": "array",
      "items": {
        "anyOf": [
          {"type": "string"},
          {"type": "image"},
          {"type": "audio"},
          {"type": "video"},
          {"type": "array", "items": {"anyOf": [{"type": "string"}, {"type": "image"}, {"type": "audio"}, {"type": "video"}]}}
        ]
      }
    }
  },
  "required": ["items"]
}
```

## Output

A vector of scores (one per item) summing to ~1.

## Output Length

Dynamic - equals len(input['items']).

## Evaluation Criteria

1. **Technical Feasibility**: Existing tech vs breakthroughs needed?
2. **Resource Requirements**: Bootstrappable vs capital-intensive?
3. **Regulatory Complexity**: Legal hurdles?
4. **Execution Risk Profile**: Direct path to market?