# Claude Code Setup for Klipper Translation

This repository has been configured for use with Claude Code to assist with translating Klipper documentation to Korean.

## Quick Start

If you're using Claude Code, you have access to helpful slash commands:

- `/translate` - Translate documentation from English to Korean
- `/check-translations` - Check translation status
- `/validate-markdown` - Validate markdown formatting
- `/build-docs` - Build and test documentation locally

## What is This Setup?

The `.claude/` directory contains configuration files that enhance Claude Code's ability to help with translation tasks. This includes:

- **Translation helpers**: Commands that understand Klipper's documentation structure
- **Validation tools**: Markdown formatting checkers
- **Build automation**: Easy documentation building and testing
- **Guidelines**: Best practices for technical translation

## For Translators

### First Time Setup

1. **Install dependencies** (if you want to test locally):
   ```bash
   pip install -r docs/_klipper3d/mkdocs-requirements.txt
   ```

2. **Start translating**:
   - Open Claude Code in this repository
   - Use `/check-translations` to see what needs translation
   - Use `/translate` to start translating documents

### Translation Workflow

1. Pick a document to translate
2. Use `/translate` command in Claude Code
3. Review the translation
4. Use `/validate-markdown` to check formatting
5. Use `/build-docs` to preview locally (optional)
6. Submit to the klipper-translations repository

## Translation Guidelines

- Keep code examples in English
- Preserve markdown formatting exactly
- Maintain technical terms in English
- Use consistent Korean terminology
- Focus on clarity and accuracy

## Documentation

For detailed information about the Claude setup, see `.claude/README.md`.

For Klipper documentation guidelines, visit: https://www.klipper3d.org/

## Repository Structure

```
klipper_ko/
├── .claude/                  # Claude Code configuration
│   ├── README.md            # Detailed Claude setup docs
│   └── commands/            # Slash commands
│       ├── translate.md
│       ├── check-translations.md
│       ├── validate-markdown.md
│       └── build-docs.md
├── docs/                    # English documentation (source)
│   ├── *.md                # Documentation files
│   └── _klipper3d/         # Build configuration
└── CLAUDE_SETUP.md         # This file
```

## Contributing

Translations are managed in the official repository:
https://github.com/Klipper3d/klipper-translations

Please follow the contribution guidelines in that repository when submitting translations.

## Need Help?

- **Claude Code**: Use `/help` or visit https://github.com/anthropics/claude-code
- **Klipper**: Visit https://www.klipper3d.org/
- **Translations**: Check https://github.com/Klipper3d/klipper-translations
