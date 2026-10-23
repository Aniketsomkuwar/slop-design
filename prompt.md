# Install slop-design with an AI agent

Paste this file into an agent that can run shell commands and edit files. It installs the skill into the directory the agent reads, verifies it, and reports how to load it.

## Step 0 - Detect the OS

- Windows: `$PSVersionTable.PSVersion`, `$env:OS`
- macOS or Linux: `uname -s`

Use the matching path and command style for the rest of this file.

## Step 1 - Choose the target

Default target, where OpenCode discovers skills:

- Windows: `%USERPROFILE%\.agents\skills\slop-design`
- macOS / Linux: `~/.agents/skills/slop-design`

If the user's agent reads skills from a different directory, ask and use that path instead. Do not install into a project directory unless the user asks for a project-scoped skill.

If the target already exists, stop and ask whether to update it in place. Do not delete an existing skill.

## Step 2 - Fetch

Clone to a temporary directory, not into the target:

```bash
git clone https://github.com/Aniketsomkuwar/slop-design.git /tmp/slop-design
```

If git is unavailable, download the repository zip and extract it.

## Step 3 - Copy

```bash
mkdir -p ~/.agents/skills/slop-design
cp -R /tmp/slop-design/SKILL.md /tmp/slop-design/references /tmp/slop-design/README.md ~/.agents/skills/slop-design/
```

Windows PowerShell:

```powershell
$target = Join-Path $env:USERPROFILE '.agents\skills\slop-design'
New-Item -ItemType Directory -Force -Path $target | Out-Null
Copy-Item "$env:TEMP\slop-design\SKILL.md" $target -Force
Copy-Item "$env:TEMP\slop-design\references" $target -Recurse -Force
Copy-Item "$env:TEMP\slop-design\README.md" $target -Force
```

Do not copy `.git`, `assets/` or `prompt.md` into the skill directory.

## Step 4 - Verify

- `SKILL.md` exists and starts with a `---` frontmatter block.
- The frontmatter has `name: slop-design` and a non-empty `description`.
- `references/` contains seven Markdown files.
- No file was truncated: `SKILL.md` is about 70 KB.

If a check fails, report it and stop. Do not patch the skill to make it pass.

## Step 5 - Optional pair

`slop-design` prevents slop; `slop-audit` detects it. If the user wants both, repeat these steps for:

```bash
git clone https://github.com/Aniketsomkuwar/slop-audit.git
```

Target: `~/.agents/skills/slop-audit`.

## Step 6 - Report

Tell the user:

- The target directory and the files installed.
- That a session restart is needed for the skill to appear.
- The load command: `/skill slop-design`.
- The reading order inside the skill: `references/slop-patterns.md` first, then `references/design-spec.md`.

## Hard rules

- Never modify `SKILL.md` or the references. They are the product.
- Never install into a project repository unless the user asks.
- Do not claim success before Step 4 passes.
