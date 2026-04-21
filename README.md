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

# How it works
- Reads Host entries from ~/.ssh/config
- Filters out Host *
- Shows selection menu with gum
- Runs ssh <selected-host>
