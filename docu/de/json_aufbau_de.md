# JSON-Dateien im Projekt - Struktur und Aufbau

Die JSON-Dateien in diesem Projekt sind in einer klar strukturierten Ordnerstruktur angelegt, um verschiedene Regionen, Plattformen und Transporttypen geordnet darzustellen.
Wenn jemand Daten hinzufügen möchte, bitte ich darum, dass auf der Projektwebseite zu tun. In Zukunft werden diese Daten auch direkt in einer Datenbank verwaltet.
- [Liste der bisher gesammelten Apps](https://unified-transport-api.linuxundmehr.de/collected-data-apps/)
- [Liste der bisher gesammelten Transportunernehmen](https://unified-transport-api.linuxundmehr.de/collected-data-companies/)
## 1. Ordnerstruktur

- [**general/**](../../data/general): Enthält allgemeine Dateien wie `transport_types.json` und `platforms.json`, die universell für alle Regionen und Projekte gültig sind.
- [**europe/**](../../data/europe): Enthält länderspezifische Dateien wie `germany.json`, `france.json` etc., um regionale Daten zu bündeln.
- [**worldwide/**](../../data/worldwide): Enthält nur die Datei `worldwide.json`, die Angebote enthält, die auf mehreren/allen Kontinenten verfügbar sind.

(Es dürfen auch weitere Länder und Kontinente hinzugefügt werden!)

## 2. Aufbau der transport_types.json

Die Datei `transport_types.json` definiert die unterstützten Transporttypen:
- **Schlüssel**: Definiert den Transporttyp, z.B. `"train"`.
- **Mehrsprachige Werte**: Jeder Schlüssel enthält Bezeichnungen in verschiedenen Sprachen.

### Beispiel

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
Bitte daran denken, dass es um Vermeidung von CO<sub>2</sub>, deshalb bitte hier keine Flüge eintragen!

## 3. Aufbau der Länder-Dateien (z.B. europe/germany.json)

Die Länderdaten sind im JSON-Array organisiert:
- **name**: Der Name der App oder Plattform.
- **description**: Kurzbeschreibung der App und ihrer Funktion.
- **type**: Array der Transporttypen (siehe `transport_types.json`).
- **platform**: Array für verfügbare Plattformen, die in `platforms.json` definiert sind.
- **location**: Enthält Informationen zum Land und zur Region.

### Beispiel

```json
[
    {
        "name": "DB Navigator",
        "description": "ÖPNV-App für Züge, U-Bahnen und Busse in Deutschland und Europa.",
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
Die `europe.json` ist für Anbieter, die in mehreren oder allen europäischen Ländern Angebote haben.