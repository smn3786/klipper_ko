# Build and Test Documentation

Help build and test the Klipper documentation locally using mkdocs.

## Build Options

1. **English docs only** (faster testing):
   ```bash
   cd /home/user/klipper_ko
   mkdocs serve --config-file docs/_klipper3d/mkdocs.yml -a 0.0.0.0:8000
   ```

2. **Multi-language docs** (includes translations):
   ```bash
   cd /home/user/klipper_ko
   ./docs/_klipper3d/build-translations.sh
   cd site/ && python3 -m http.server 8000
   ```

## Your Task

1. Ask the user which build option they prefer
2. Check if mkdocs and required dependencies are installed
3. Run the appropriate build command
4. Report any build errors or warnings
5. Provide the URL to access the documentation (usually http://localhost:8000)
6. Offer to fix any build issues that arise

If dependencies are missing, guide the user through installation:
```bash
pip install -r docs/_klipper3d/mkdocs-requirements.txt
```
