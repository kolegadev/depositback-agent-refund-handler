# depositback-agent-refund-handler

Processes 30-day money-back guarantee claims via Revolut API

## DepositBack Agent Network — Operations

Part of the DepositBack autonomous marketing system.

## Quick Start

```bash
git clone https://github.com/kolegadev/depositback-agent-refund-handler.git
cd depositback-agent-refund-handler
pip install -r requirements.txt
python runtime/main.py
```

## Structure

```
.
├── SKILL.md, manifest.json, README.md
├── runtime/main.py
├── skills/skill_resolver.py, noop.py
├── data/inbox/, data/outbox/
└── .github/workflows/heartbeat.yml, scan.yml
```

## License

MIT — DepositBack Agent Network
