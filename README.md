# OPN CODE </> 🕊️

> A lightweight Python utility for wrapping and protecting Python (`.py`) and Bash (`.sh`) source files into a self-contained launcher.

## Owner

**ONXX**

## Features

- Protects `.py` and `.sh` files
- Compresses the original source with GZIP
- Encodes the compressed payload with Base64
- Generates a standalone launcher
- No password required
- No external Python package required
- Preserves runtime arguments
- Interactive terminal menu
- Command-line mode with custom output path
- Designed for Termux/Linux environments

## Requirements

- Python 3
- Bash (required when protecting/running Bash scripts)

No third-party Python packages are required.

## Usage
```
git clone https://github.com/onxx-x145/OPN.git
cd OPN
Run the tool:

```bash
python3 opn
```

The interactive menu provides:

```text
[1] Protect Python (.py)
[2] Protect Bash (.sh)
[3] Exit
```

### Command-line mode

Protect a Python file:

```bash
python3 opn script.py
```

Protect a Bash file:

```bash
python3 opn script.sh
```

Choose a custom output file:

```bash
python3 opn script.py -o protected.py
```

## How it works

1. The selected source file is read as bytes.
2. The source is compressed using GZIP.
3. The compressed data is Base64 encoded.
4. A standalone launcher containing the payload is generated.
5. The generated launcher restores the source in memory and executes it.

This is **source wrapping/obfuscation**, not strong cryptographic encryption. Anyone who can access the generated launcher and has sufficient technical access may be able to recover the embedded source.

## Supported files

| File type | Supported |
|---|---|
| Python `.py` | Yes |
| Bash `.sh` | Yes |
| Other extensions | No |

## Output

By default, the generated file uses the `_protected.py` suffix:

```text
script.py
└── script_protected.py
```

For Bash input, the generated launcher is also a Python launcher because OPN embeds the original Bash payload inside it.

## Notes

- Test protected files before distributing them.
- Keep backups of your original source files.
- The tool is intended for legitimate source protection and packaging.
- Runtime behavior can depend on the original script's environment and installed dependencies.

## Credits

**OPN CodeProtector**

**Owner: ONXX**
