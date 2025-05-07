# spellfix

A powerful CLI spelling correction tool for macOS that fixes spelling errors and applies text case transformations, with automatic clipboard integration.

![Version](https://img.shields.io/badge/version-1.0.0-blue)
![Platform](https://img.shields.io/badge/platform-macOS-lightgrey)
![License](https://img.shields.io/badge/license-MIT-green)

## Features

- ✅ Automatically fixes spelling errors using aspell
- ✅ Multiple case transformation options:
  - Sentence case
  - lowercase
  - UPPERCASE
  - Title Case
- ✅ Copies results to clipboard automatically
- ✅ Works with direct input or piped content
- ✅ Easy to install via Homebrew

## Installation

### Prerequisites

- macOS with Homebrew installed
- Terminal with Zsh shell (default on modern macOS)

### Quick Installation (Homebrew)

```bash
# First, install required dependency
brew install aspell

# Install spellfix
brew tap yourusername/tools
brew install spellfix
```

### Manual Installation

```bash
# Install aspell dependency
brew install aspell

# Download the script
curl -o spellfix https://raw.githubusercontent.com/yourusername/spellfix/main/spellfix

# Make it executable
chmod +x spellfix

# Move it to your bin folder
sudo mv spellfix /usr/local/bin/
```

## Usage

### Basic Usage

```bash
# Fix spelling in a sentence
spellfix "thiss is a misspeled sentence"
# Output: "this is a misspelled sentence"
```

### Case Transformations

```bash
# Convert to lowercase after fixing spelling
spellfix -l "Convert This text to lowercase"
# Output: "convert this text to lowercase"

# Convert to UPPERCASE after fixing spelling
spellfix -u "convert to uppercase after fixing"
# Output: "CONVERT TO UPPERCASE AFTER FIXING"

# Convert to Sentence case after fixing spelling
spellfix -s "this should be in sentence case. another sentence here."
# Output: "This should be in sentence case. Another sentence here."

# Convert to Title Case after fixing spelling
spellfix -t "this should be in title case"
# Output: "This Should Be In Title Case"
```

### Working with Pipes

```bash
# Pipe content into spellfix
echo "fix my speling" | spellfix
# Output: "fix my spelling"

# Combine with other commands
cat text.txt | spellfix -t
```

### Additional Options

```bash
# Don't copy to clipboard, just print the result
spellfix -n "just print dont copy"

# Show help information
spellfix --help

# Show version
spellfix --version
```

## Command Line Options

| Option | Long form | Description |
|--------|-----------|-------------|
| `-l` | `--lowercase` | Convert output to lowercase |
| `-u` | `--uppercase` | Convert output to UPPERCASE |
| `-s` | `--sentence` | Convert output to Sentence case |
| `-t` | `--title` | Convert output to Title Case |
| `-n` | `--no-clipboard` | Don't copy output to clipboard |
| `-h` | `--help` | Display help message |
| `-v` | `--version` | Display version information |

## Examples

```bash
# Fix basic spelling errors
spellfix "thiss is a misspeled sentence"
# Output: "this is a misspelled sentence"

# Fix spelling and convert to title case
spellfix -t "fixinng speeling and makeing it title case"
# Output: "Fixing Spelling And Making It Title Case"

# Process text from a file and apply uppercase
cat document.txt | spellfix -u
# Output: Text from document.txt with spelling fixed and converted to UPPERCASE

# Fix spelling without copying to clipboard
spellfix -n "dont copy this to my clipbord"
# Output: "don't copy this to my clipboard"
```

## How It Works

`spellfix` uses `aspell` to check and fix spelling errors, then applies case transformations as specified. The tool:

1. Processes each word in the input text
2. Checks if the word is misspelled using aspell
3. Replaces misspelled words with the best suggestion
4. Preserves punctuation during correction
5. Applies the specified case transformation
6. Outputs the result and copies it to the clipboard (unless `-n` flag is used)

## Contributing

Contributions are welcome! Please feel free to submit a Pull Request.

## License

This project is licensed under the MIT License - see the LICENSE file for details.

## Acknowledgments

- [aspell](http://aspell.net/) - The spell checking library used
- [Homebrew](https://brew.sh/) - The package manager for macOS
