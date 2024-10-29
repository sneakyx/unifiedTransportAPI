# JSON Files in the Project - Structure and Setup

The JSON files in this project are organized in a structured folder system to manage various regions, platforms, and transport types.

If anyone would like to add data, please do so on the project website. In the future, this data will also be managed directly in a database.
- [List of apps collected so far](https://unified-transport-api.linuxundmehr.de/collected-data-apps/)
- [List of transport companies collected so far](https://unified-transport-api.linuxundmehr.de/collected-data-companies/)


## 1. Folder Structure

- [**general/**](../../data/general): Contains general files like `transport_types.json` and `platforms.json`, which are applicable to all regions and projects.
- [**europe/**](../../data/europe): Contains country-specific files like `germany.json`, `france.json`, etc., to bundle regional data.
- [**worldwide/**](../../data/worldwide): Contains just the file `worldwide.json` for offers in one or more continents.

(It is allowed to add more countries and continents!)
## 2. Structure of transport_types.json

The `transport_types.json` file defines the supported transport types:
- **Key**: Defines the transport type, e.g., `"train"`.
- **Multilingual Values**: Each key contains labels in different languages.

### Example

```json
{
    "train": {
        "de": "Zug",
        "en": "Train",
        "fr": "Train",
        "es": "Tren"
    }
}
```

Remember: The goal is to save CO<sub>2</sub>- don't add `flight` here!

## 3. Structure of Country Files (e.g., europe/germany.json)

The country data is organized in a JSON array:
- **name**: The name of the app or platform.
- **description**: Short description of the app and its function.
- **type**: Array of transport types (refer to `transport_types.json`).
- **platform**: Array of available platforms, defined in `platforms.json`.
- **location**: Contains information on the country and region.

### Example

```json
[
    {
        "name": "DB Navigator",
        "description": "Public transport app covering trains, subways, and buses in Germany and Europe.",
        "type": ["train", "high_speed_train", "bus"],
        "platform": ["ios", "android", "website"],
        "website": "https://www.bahn.com/",
        "location": {
            "country": "Germany",
            "region": "All",
            "coordinates": [10.4515, 51.1657]
        }
    }
]
```
The file `europe.json` is for companies / apps that work in all or more than one countries in europe.