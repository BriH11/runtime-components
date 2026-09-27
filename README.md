# runtime-components

My personal collection of "rc" files (Runtime Components) — the config files
read by bash, zsh, vim, git, and gdb every time they start. Cloning this repo
onto a new machine and running `install.sh` gets my shell and tools set up
the way I like them, without configuring everything from scratch.

## What's here

| File        | Read by | When                                  |
|-------------|---------|----------------------------------------|
| `.bashrc`   | bash    | every interactive terminal              |
| `.zshrc`    | zsh     | every interactive terminal (macOS default) |
| `.vimrc`    | vim     | every time vim opens                    |
| `.gdbinit`  | gdb     | every time the debugger starts          |
| `.gitconfig`| git     | every git command (aliases + core settings) |
| `install.sh`| —       | installs everything above into `$HOME`  |

## Usage

```bash
git clone git@github.com:<your-username>/runtime-components.git
cd runtime-components
chmod +x install.sh
./install.sh
```

Run with `--dry-run` first to preview changes without touching anything:

```bash
./install.sh --dry-run
```

Existing files are never deleted — anything in the way is backed up as
`~/.NAME.backup-<timestamp>` before being replaced.

## Notes

- `~/.gitconfig` (with your name and email) is left alone. `install.sh`
  copies this repo's `.gitconfig` to `~/.gitconfig.rc` and adds an
  `include.path` line so git reads both.
- `install.sh` will also install [oh-my-zsh](https://ohmyz.sh) if `zsh` is
  available (skip with `--no-omz`).
