# Dotfiles for configurations
Version control for reused dot files

# Installation

### Setup Alias

Add the following alias to `.bashrc`.
```bash
alias config='/usr/bin/git --git-dir=$HOME/.cfg/ --work-tree=$HOME'
```

### Add to `.gitignore`

Create a `.gitignore` in `$HOME` (if it doesn't already exist) and add this repo.
```bash
touch ~/.gitignore
echo ".cfg" >> .gitignore
```

### Clone this Repo
```bash
git clone --bare git@github.com:schackartk/dotfiles.git $HOME/.cfg
```

### Checkout Contents

Source `.bashrc` so that aliases are in scope. Then checkout the contents of the repo.
```bash
source ~/.bashrc
config checkout
```

### Ignore Untracked Files

This will not show untracked files when using `config status`
```
config config --local status.showUntrackedFiles no
```

# Working with this Repository

When working with version control of dotfiles, `config` is now an alias for `git` in those cases.

```bash
config status
config add .adotfile
config commit -m "add adotfile"
config push
```
