# Claude Code Configuration for Klipper Translation

This directory contains Claude Code configuration for translating Klipper documentation to Korean.

## Project Overview

**Klipper** is a 3D printer firmware that combines a general purpose computer with micro-controllers. This setup helps translate the extensive documentation from English to Korean.

## Available Slash Commands

### `/translate`
Main translation helper for converting English documentation to Korean.
- Preserves all markdown formatting
- Keeps technical terms in English
- Maintains code blocks and examples unchanged
- Ensures consistent terminology

### `/check-translations`
Analyzes translation status across all documentation.
- Lists all documentation files
- Shows what's translated vs. what's pending
- Prioritizes documents by importance
- Provides statistics

### `/validate-markdown`
Validates markdown formatting in translated documents.
- Checks for broken links
- Verifies code block formatting
- Ensures proper header hierarchy
- Identifies formatting issues with line numbers

### `/build-docs`
Builds and tests documentation locally using mkdocs.
- Supports English-only or multi-language builds
- Checks for build errors
- Guides through dependency installation
- Provides local preview URL

## Translation Workflow

### 1. Check Status
```
/check-translations
```

### 2. Translate a Document
```
/translate
```
Then specify which document you want to translate.

### 3. Validate Translation
```
/validate-markdown
```
Check your translation for formatting issues.

### 4. Test Locally
```
/build-docs
```
Build and preview the documentation in your browser.

## Translation Guidelines

### What to Translate
- User-facing explanatory text
- Instructions and descriptions
- Error messages and warnings
- Navigation and UI text

### What NOT to Translate
- Code examples and snippets
- Configuration parameter names
- G-code commands
- File paths and URLs
- Command-line examples
- Technical identifiers

### Best Practices
1. **Consistency**: Use the same Korean terms for recurring concepts
2. **Clarity**: Prioritize clear communication over literal translation
3. **Technical Accuracy**: Preserve technical precision
4. **Formatting**: Maintain exact markdown structure
5. **Context**: Consider the 3D printing domain context

## Translation Repository

Translations are managed in a separate repository:
- **Repository**: https://github.com/Klipper3d/klipper-translations
- **Korean translations location**: `docs/locales/ko/`

## Technical Details

### Documentation Structure
- **Source docs**: `/docs/` (56 markdown files)
- **Build system**: MkDocs with Material theme
- **Build script**: `docs/_klipper3d/build-translations.sh`
- **Config**: `docs/_klipper3d/mkdocs.yml`

### Key Files
- `Navigation.md`: Table of contents translations
- `manual-index.md`: Custom index page (if exists)
- Individual `.md` files: Translated documentation pages

### Dependencies
```bash
pip install -r docs/_klipper3d/mkdocs-requirements.txt
```

## Getting Help

- For Klipper documentation: https://www.klipper3d.org/
- For translation issues: https://github.com/Klipper3d/klipper-translations
- For Claude Code help: Use `/help` or visit https://github.com/anthropics/claude-code/issues

## Notes

This configuration is specifically designed for Korean translation work but can be adapted for other languages by modifying the slash command prompts.
