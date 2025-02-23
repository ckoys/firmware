# Meshtastic RP2040-LoRa Optimized

Optimierte Version der Meshtastic-Firmware speziell für das RP2040-LoRa Board.

## Features

- Minimaler Speicherverbrauch
- Optimierte CPU-Nutzung
- Reduzierte Stromaufnahme
- Fokus auf LoRa-Kommunikation

## Optimierungen

- Deaktivierte nicht benötigte Hardware-Features (WiFi, Bluetooth, Display)
- Minimierte Debug- und Diagnose-Ausgaben
- Optimierte RadioLib-Konfiguration
- Statische Speicherallokation
- Reduzierte Task-Prioritäten und Stack-Größen
- Power Management Features aktiviert

## Entwicklung

### Voraussetzungen

- PlatformIO
- Git
- Python 3.x

### Setup

1. Repository klonen:
```bash
git clone https://github.com/[your-username]/[repo-name].git
cd [repo-name]
```

2. Dependencies installieren:
```bash
pio pkg install
```

### Build & Flash

```bash
# Build
pio run -e rp2040-lora

# Upload
pio run -e rp2040-lora -t upload

# Monitor
pio device monitor -e rp2040-lora
```

### Debug

Für Debug-Builds:
```bash
pio run -e rp2040-lora -t debug
```

## Source Directory Structure

```
src/
├── configuration.h          # Hauptkonfiguration
├── main.cpp                # Hauptprogramm
├── mesh/
│   ├── generated/         # Protobuf generierte Dateien
│   ├── Router.*          # Mesh Routing
│   ├── NodeDB.*          # Knotendatenbank
│   └── MeshRadio.*       # LoRa Radio Funktionalität
├── platform/
│   └── rp2xx0/           # RP2040 spezifischer Code
└── power.*               # Power Management
```
