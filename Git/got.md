## Git with a Custom `.got` Directory (`got` Alias)

This technique lets you manage Git version control in a directory without using the default `.git` folder.

### Setup

- Rename current `.git` folder to `.got`.
- Use this command `git --git-dir .got`, or set an alias.

### Setting an alias

- Add `alias got='git --git-dir .got'` as alias to your shell config (optional).
- Run commands like `got status`.
