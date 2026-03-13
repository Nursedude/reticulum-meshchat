# Reticulum MeshChat - Claude Code Configuration

> **Fork maintainer**: WH6GXZ (Nursedude)
> **Upstream**: github.com/liamcottle/reticulum-meshchat

## Quick Context

Reticulum MeshChat is a mesh network communications app powered by the Reticulum Network Stack.
Supports messaging, file transfer, and audio calls over LoRa, WiFi, Ethernet, and internet.
Compatible with Sideband, NomadNet, and other LXMF clients.

## Key Commands

```bash
# Run from source
pip install -r requirements.txt
python meshchat.py

# Docker
docker-compose up
```

## Architecture

```
├── meshchat.py        # Main entry point (Python backend)
├── database.py        # Local message storage
├── setup.py           # Package setup
├── src/
│   ├── backend/       # Python RNS/LXMF backend
│   └── frontend/      # Web UI (Vite + Tailwind)
├── electron/          # Desktop app wrapper
└── docs/              # Platform-specific install guides
```

## Tech Stack

- **Backend**: Python, Reticulum, LXMF
- **Frontend**: JavaScript, Vite, Tailwind CSS
- **Desktop**: Electron
- **Audio**: Codec2 (low-bandwidth voice)

## Development Notes

- This is a **fork** — check upstream for changes before major modifications
- Web UI requires localhost or HTTPS for microphone access (AudioWorklet)
- Database is local SQLite for message persistence
- All mesh communication goes through Reticulum Network Stack

## Code Standards

- Python 3.9+
- Security: no `shell=True`, no bare `except:`, validate inputs
- Test changes against both direct RNode and TCP connections

## Contact

- GitHub: github.com/Nursedude/reticulum-meshchat
- Callsign: WH6GXZ
