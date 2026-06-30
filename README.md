# sshm

Simple interactive SSH selector for `~/.ssh/config` using `gum`.

<img width="809" height="540" alt="Interface demonstration" src="https://github.com/user-attachments/assets/6c8e77ca-064c-472c-bd1e-d73b07e04a18" />

## Requirements

- bash
- ssh
- gum (`brew install gum`)

## Install

```bash
git clone https://github.com/limepillX/sshm
cd sshm
chmod +x install.sh
./install.sh
```

## Usage

```
sshm
```

Navigate with arrow keys, select with Enter, exit with Escape.

## Categories

Group hosts by adding category words before the host alias on the `Host` line. The last word is the SSH alias used to connect.

```
# ~/.ssh/config
Host bastion
Host eu prod web-1
Host eu prod db-1
Host eu staging api
Host us prod web-1
```

The first menu shows `bastion` alongside **`▶ eu`** and **`▶ us`**. Selecting a category opens a submenu. Use **← Back** to return to the previous level.

Hosts whose alias starts with `_` are hidden from the menu but still usable directly via `ssh`.

```
Host _jump-box
    HostName 10.0.0.1
```

## How it works

- Reads `Host` entries from `~/.ssh/config`, ignoring wildcards and `_`-prefixed aliases
- Groups hosts by the words preceding the last word on each `Host` line
- Shows an interactive menu via `gum`
- Runs `ssh <selected-host>`
