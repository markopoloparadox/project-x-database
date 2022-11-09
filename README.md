# Database

## CPU List Schema
```json
{
    "$schema": "http://json-schema.org/draft-07/schema#",
    "title": "CPU list",
    "type": "array",
    "items": [
        {
            "title": "CPU details",
            "type": "object",
            "properties": {
                "manufacturer": {
                    "enum": [
                        "AMD",
                        "Intel"
                    ],
                    "description": "Represents the CPU manufacturer. It can only be either AMD or Intel."
                },
                "architecture": {
                    "type": "string",
                    "description": "Represents the CPU microarchitecture. Example: Zen 1 or Alder Lake. "
                },
                "family": {
                    "type": "string",
                    "description": "Represents the CPU family. Example: Ryzen 7 or Core i7"
                },
                "model": {
                    "type": "string",
                    "description": "Represents the CPU model. Example: 7700X or 13700K"
                },
                "launch_price": {
                    "type": "string",
                    "description": "Represents the CPU launch price. If the price got reduced in the meantime it won't be visible here."
                },
                "release_date": {
                    "type": "string",
                    "format": "date",
                    "description": "Represents the CPU release date. Example: 2022-04-04 (YYYY-MM-DD)."
                }
            },
            "required": [
                "manufacturer",
                "architecture",
                "family",
                "model",
                "launch_price",
                "release_date"
            ]
        }
    ]
}
```