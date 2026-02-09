# Execution Feasibility Ranker

A vector function that evaluates all startup ideas simultaneously for relative feasibility.

## Input Schema

The input is an object with a single required field called `items` containing an array of startup ideas.

Each item in the array can be:
- A string (plain text pitch)
- An image (schema type: image)
- An audio clip (schema type: audio)
- A video (schema type: video)
- A composite array containing any mix of the above

Use this exact input schema:
```json
{
  "type": "object",
  "properties": {
    "items": {
      "type": "array",
      "minItems": 2,
      "items": {
        "anyOf": [
          {"type": "string"},
          {"type": "image"},
          {"type": "audio"},
          {"type": "video"},
          {
            "type": "array",
            "minItems": 1,
            "items": {
              "anyOf": [
                {"type": "string"},
                {"type": "image"},
                {"type": "audio"},
                {"type": "video"}
              ]
            }
          }
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

Dynamic - equals the number of items: `{"$starlark": "len(input['items'])"}`

## Evaluation Criteria

1. **Technical Feasibility**: Existing tech vs breakthroughs?
2. **Resource Requirements**: Bootstrappable vs capital-intensive?
3. **Regulatory Complexity**: Legal hurdles?
4. **Execution Risk Profile**: Direct path to market?