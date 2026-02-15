# CLAUDE.md

This file provides guidance to Claude Code when working with this repository.

## Project Overview

**BASB** is a personal knowledge management repository implementing the PARA method (Projects, Areas, Resources, Archives). This is NOT a traditional software project, but rather a structured documentation and knowledge organization system following the "Building a Second Brain" methodology.

## Repository Structure

The repository uses a strict PARA organizational structure with numbered directories:

- `0.inbox/` - Temporary holding area for new, unprocessed information
- `0.inbox/Journal-the-raw_and_not_yet_distilled_ver/` - Daily journals (filename: `YYYYMMDD.md`)
- `1.project/` - Active projects with defined goals and deadlines
- `2.area/` - Areas of ongoing responsibility and knowledge
- `3.resource/` - Reference materials and resources
- `4.archive/` - Completed or inactive items

## Git Setup

This repo uses a **personal SSH key** via SSH config alias (separate from work keys):

- **Remote:** `git@github.com-cyng93:cyng93/basb.git`
- **SSH Config Host:** `github.com-cyng93` → uses `~/.ssh/id_cyng93`
- **Key type:** ED25519

### SSH Config Entry

```
Host github.com-cyng93
  HostName github.com
  User git
  IdentityFile ~/.ssh/id_cyng93
```

### Clone / ghq Setup

```bash
# Clone with ghq (use GIT_SSH_COMMAND to keep clean ghq path)
GIT_SSH_COMMAND="ssh -i ~/.ssh/id_cyng93" ghq get git@github.com:cyng93/basb.git

# Then fix remote to use SSH config alias
git -C "$(ghq root)/github.com/cyng93/basb" remote set-url origin git@github.com-cyng93:cyng93/basb.git
```

## ghq

If user uses `ghq`, the repo lives at: `$(ghq root)/github.com/cyng93/basb`

## User Preferences

- **Shell:** Fish (primary), also uses Bash
- When providing shell command examples, **always provide Fish version followed by Bash version**
- **Editor:** VS Code
- **Documentation format:** Markdown (with Obsidian wikilinks)
