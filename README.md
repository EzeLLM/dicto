# dicto - Command-line Dictionary Lookup Tool

`dicto` is a simple bash script that allows you to quickly look up word definitions from the command line. It uses the Free Dictionary API to fetch definitions.

## Installation

1. Download the `dicto` script.
2. Make it executable:
   ```bash
   chmod +x dicto
   ```
3. Move it to a directory in your PATH. For example:
   ```bash
   mkdir -p ~/bin
   mv dicto ~/bin/
   ```
4. If `~/bin` is not in your PATH, add it:
   - For bash users, edit `~/.bash_profile`:
     ```bash
     echo 'export PATH="$HOME/bin:$PATH"' >> ~/.bash_profile
     source ~/.bash_profile
     ```
   - For zsh users (default on newer Macs), edit `~/.zshrc`:
     ```bash
     echo 'export PATH="$HOME/bin:$PATH"' >> ~/.zshrc
     source ~/.zshrc
     ```

## Usage

To look up a word, simply type `dicto` followed by the word:

```bash
dicto <word>
```

For example:

```bash
dicto cardinality
```

This will display the definitions of "cardinality" found in the dictionary.

## Dependencies

- `curl`: Used to make HTTP requests (usually pre-installed on most systems).
- `jq`: A lightweight command-line JSON processor (optional, but recommended for better output formatting).

If `jq` is not installed, the script will fall back to a simpler parsing method using `grep`.

To install `jq` on macOS using Homebrew:

```bash
brew install jq
```

## Notes

- This script requires an internet connection to fetch definitions.
- The Free Dictionary API is used, which provides English definitions.
- If a word is not found, the script will display an error message.

## Troubleshooting

If you encounter any issues:

1. Ensure the script is executable (`chmod +x dicto`).
2. Verify that the script's location is in your PATH.
3. Check your internet connection.
4. If definitions are not formatting correctly, try installing `jq`.

## License

This script is provided "as is", without warranty of any kind. Feel free to modify and distribute it as needed.