# Codex Bioinformatics Skills Install

Install these skills into Codex so they can be discovered at startup.

## Prerequisites

- Git

## Installation

Clone this repository and link each skill directory into Codex's skill directory:

```bash
CODEX_HOME="${CODEX_HOME:-$HOME/.codex}"
REPO_DIR="$CODEX_HOME/codex-bioinfo-skills"

if [ -d "$REPO_DIR/.git" ]; then
  git -C "$REPO_DIR" pull --ff-only
else
  git clone https://github.com/stayn1ght/codex-bioinfo-skills.git "$REPO_DIR"
fi

mkdir -p "$CODEX_HOME/skills"

for skill in bioinfo-analysis-plan bioinfo-validation-pyramid bioinfo-watchdog bioinfo-result-review; do
  target="$CODEX_HOME/skills/$skill"
  if [ -e "$target" ] || [ -L "$target" ]; then
    echo "Already exists: $target"
  else
    ln -s "$REPO_DIR/$skill" "$target"
  fi
done
```

Restart Codex after installation.

## Verify

```bash
ls -la "${CODEX_HOME:-$HOME/.codex}/skills" | grep bioinfo-
```

You should see these skill directories:

```text
bioinfo-analysis-plan
bioinfo-validation-pyramid
bioinfo-watchdog
bioinfo-result-review
```

## Alternative Install

If you prefer Codex's built-in skill installer, ask Codex:

```text
$skill-installer install https://github.com/stayn1ght/codex-bioinfo-skills/tree/main/bioinfo-analysis-plan
$skill-installer install https://github.com/stayn1ght/codex-bioinfo-skills/tree/main/bioinfo-validation-pyramid
$skill-installer install https://github.com/stayn1ght/codex-bioinfo-skills/tree/main/bioinfo-watchdog
$skill-installer install https://github.com/stayn1ght/codex-bioinfo-skills/tree/main/bioinfo-result-review
```

Restart Codex after installation.

## Updating

If installed with the symlink method:

```bash
git -C "${CODEX_HOME:-$HOME/.codex}/codex-bioinfo-skills" pull --ff-only
```

If installed with `skill-installer`, reinstall the skills when you want a fresh
copy.

Restart Codex after updating.

## Uninstalling

```bash
rm "${CODEX_HOME:-$HOME/.codex}/skills/bioinfo-analysis-plan"
rm "${CODEX_HOME:-$HOME/.codex}/skills/bioinfo-validation-pyramid"
rm "${CODEX_HOME:-$HOME/.codex}/skills/bioinfo-watchdog"
rm "${CODEX_HOME:-$HOME/.codex}/skills/bioinfo-result-review"
```

Optionally delete the clone:

```bash
rm -rf "${CODEX_HOME:-$HOME/.codex}/codex-bioinfo-skills"
```
