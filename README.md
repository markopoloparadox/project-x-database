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
                    "description": "Represents the CPU microarchitecture. Example: Zen 1 or Alder Lake."
                },
                "family": {
                    "type": "string",
                    "description": "Represents the CPU family. Example: Ryzen 7 or Core i7."
                },
                "model": {
                    "type": "string",
                    "description": "Represents the CPU model. Example: 7700X or 13700K."
                },
                "launch_price": {
                    "type": "number",
                    "description": "Represents the CPU launch price. If the price got reduced in the meantime it won't be visible here. It is in dollars and it represents the American MSRP."
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

## CPU Prices Schema
```json
{
    "$schema": "http://json-schema.org/draft-07/schema#",
    "title": "CPU history pricing",
    "type": "array",
    "items": [
        {
            "title": "CPU price details",
            "type": "object",
            "properties": {
                "manufacturer": {
                    "enum": [
                        "AMD",
                        "Intel"
                    ],
                    "description": "Represents the CPU manufacturer. It can only be either AMD or Intel."
                },
                "model": {
                    "type": "string",
                    "description": "Represents the CPU model. Example: 7700X or 13700K."
                },
                "price": {
                    "type": "number",
                    "description": "Price of that model in Euros (includes VAT). It doesn't include any discounts."
                },
                "date_time": {
                    "type": "string",
                    "format": "date-time",
                    "description": "The date and time when that model was available for that price."
                },
                "shop": {
                    "enum": [
                        "ADM",
                        "Links"
                    ],
                    "description": "Name of the shop that was selling that model."
                }
            },
            "required": [
                "manufacturer",
                "model",
                "price",
                "date_time",
                "shop"
            ]
        }
    ]
}
```