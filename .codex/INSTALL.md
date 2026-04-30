# Codex Bioinformatics Skills Install

Install these skills into Codex so they can be discovered at startup.

## Preferred Install

Use the `skill-installer` skill to install these GitHub skill directories:

```text
$skill-installer install https://github.com/stayn1ght/codex-bioinfo-skills/tree/main/bioinfo-analysis-plan
$skill-installer install https://github.com/stayn1ght/codex-bioinfo-skills/tree/main/bioinfo-validation-pyramid
$skill-installer install https://github.com/stayn1ght/codex-bioinfo-skills/tree/main/bioinfo-watchdog
$skill-installer install https://github.com/stayn1ght/codex-bioinfo-skills/tree/main/bioinfo-result-review
```

Restart Codex after installation.

## Shell Fallback

If `skill-installer` is unavailable, clone this repository and symlink each skill
into Codex's skill directory:

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

## Updating

If installed with `skill-installer`, reinstall the skills when you want a fresh
copy.

If installed with the shell fallback:

```bash
git -C "${CODEX_HOME:-$HOME/.codex}/codex-bioinfo-skills" pull --ff-only
```

Restart Codex after updating.
