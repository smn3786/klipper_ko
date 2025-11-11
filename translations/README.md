# Korean Translation Directory

This directory contains Korean translations of Klipper documentation.

## Directory Structure

```
translations/
└── ko/                    # Korean translations
    ├── *.md              # Translated markdown files
    └── Navigation.md     # Table of contents (Korean)
```

## Translation Workflow

1. **Source**: English docs from `/docs/*.md`
2. **Translation**: Korean docs in `/translations/ko/*.md`
3. **Submission**: Eventually submit to https://github.com/Klipper3d/klipper-translations

## Guidelines

- Keep original English docs in `/docs/` unchanged
- Store Korean translations in `/translations/ko/`
- Preserve markdown formatting exactly
- Keep code examples, config names, and G-codes in English
- Translate only explanatory text and descriptions

## Translation Status

See `TRANSLATION_STATUS.md` for detailed progress tracking.

## Submitting Translations

When translations are ready:
1. Fork https://github.com/Klipper3d/klipper-translations
2. Copy files to `docs/locales/ko/`
3. Create pull request

The official klipper-translations repository structure:
- `docs/locales/ko/*.md` - Korean documentation files
- `docs/locales/ko/Navigation.md` - Korean table of contents
