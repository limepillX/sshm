# sshm

Simple interactive SSH selector for `~/.ssh/config` using `gum`.

## Requirements

- bash
- ssh
- gum (`brew install gum`)

## Install

```bash
git clone <repo-url>
cd sshm
chmod +x sshm
sudo cp sshm /usr/local/bin/
```

## Usage

```
sshm
```

# How it works
- Reads Host entries from ~/.ssh/config
- Filters out Host *
- Shows selection menu with gum
- Runs ssh <selected-host>
