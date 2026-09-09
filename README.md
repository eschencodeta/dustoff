# dustoff

A tiny CLI to clean, rotate and archive old log files

Started as a weekend hack, grew on me.

## Highlights

- Archive matched logs into a timestamped .tar.gz
- Exit codes friendly for cron and CI
- Scan directories for log files by glob pattern
- Filter by age (--older-than) or size (--larger-than)
- Dry-run mode shows what would happen, touches nothing

## Usage

```bash
# show what would be cleaned, change nothing
logwash ./logs --older-than 30 --dry-run

# archive logs older than 30 days
logwash ./logs --older-than 30 --archive ./backup
```

## Install

```bash
pip install -r requirements.txt
python -m logwash --help
```

## Project structure

```text
├── docs/
│   └── usage.md
├── examples/
│   └── quickstart.md
├── logwash/
│   ├── __init__.py
│   ├── __main__.py
│   └── cli.py
├── tests/
│   └── test_cli.py
├── .editorconfig
├── .gitattributes
├── .gitignore
├── CHANGELOG.md
├── CONTRIBUTING.md
├── LICENSE
├── Makefile
├── SECURITY.md
├── pyproject.toml
└── requirements.txt
```

## Development

```bash
python -m venv .venv && source .venv/bin/activate
pip install -r requirements.txt
python -m pytest -q
```

## License

MIT. Do whatever you want.
