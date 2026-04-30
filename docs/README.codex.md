# Codex Bioinformatics Skills for Codex

Guide for using Codex Bioinformatics Skills with native Codex skill discovery.

These skills complement `superpowers`; they do not replace it. Use `superpowers`
for general software-development discipline, and use these skills for
bioinformatics workflow planning, validation, monitoring, and result review.

## Quick Install

Tell Codex:

```text
Fetch and follow instructions from https://raw.githubusercontent.com/stayn1ght/codex-bioinfo-skills/refs/heads/main/.codex/INSTALL.md
```

Restart Codex after installation.

## What Gets Installed

- `bioinfo-analysis-plan`: plan bioinformatics workflows before writing commands or code.
- `bioinfo-validation-pyramid`: validate inputs, small examples, biological sanity, and dry runs before full-scale analyses.
- `bioinfo-watchdog`: monitor long-running bioinformatics jobs in read-only mode.
- `bioinfo-result-review`: review outputs before declaring analyses complete or ready for downstream use.

## How It Works

Codex discovers skills from its skill directory at startup. The install guide
uses `$skill-installer` when available and falls back to cloning this repository
under `${CODEX_HOME:-$HOME/.codex}` and symlinking each skill folder into
`${CODEX_HOME:-$HOME/.codex}/skills`.

## Usage

Skills are activated automatically when:

- you mention a skill by name
- the task matches a skill's `description`
- another workflow skill directs Codex to use them

Example prompts:

```text
Use bioinfo-analysis-plan to plan an RNA-seq workflow from FASTQ to count matrix.
```

```text
Use bioinfo-validation-pyramid before launching this full metagenomics assembly.
```

```text
Use bioinfo-result-review to check whether these annotation outputs are ready for downstream analysis.
```

## Updating

Re-run the install instructions, or run this if you used the shell fallback:

```bash
git -C "${CODEX_HOME:-$HOME/.codex}/codex-bioinfo-skills" pull --ff-only
```

Restart Codex after updating.

## Getting Help

- Issues: https://github.com/stayn1ght/codex-bioinfo-skills/issues
- Repository: https://github.com/stayn1ght/codex-bioinfo-skills
