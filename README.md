# Codex Bioinformatics Skills

Instruction-only Codex skills for bioinformatics analysis workflows.

## Skills

- `bioinfo-analysis-plan`: plan bioinformatics workflows before writing commands or code.
- `bioinfo-validation-pyramid`: validate inputs, small examples, biological sanity, and dry runs before full-scale analyses.
- `bioinfo-watchdog`: monitor long-running bioinformatics jobs in read-only mode.
- `bioinfo-result-review`: review outputs before declaring analyses complete or ready for downstream use.

## Install from Codex

Tell Codex:

```text
Fetch and follow instructions from https://raw.githubusercontent.com/stayn1ght/codex-bioinfo-skills/main/.codex/INSTALL.md
```

See [docs/INSTALL.md](docs/INSTALL.md) for the detailed install guide.

## Alternative Install

You can also install each skill from inside Codex with `$skill-installer`:

```text
$skill-installer install https://github.com/stayn1ght/codex-bioinfo-skills/tree/main/bioinfo-analysis-plan
$skill-installer install https://github.com/stayn1ght/codex-bioinfo-skills/tree/main/bioinfo-validation-pyramid
$skill-installer install https://github.com/stayn1ght/codex-bioinfo-skills/tree/main/bioinfo-watchdog
$skill-installer install https://github.com/stayn1ght/codex-bioinfo-skills/tree/main/bioinfo-result-review
```

Restart Codex after installation so the new skills are discovered.

## Local Development Fallback

If you are working from a local clone, link or copy the skill folders into
Codex's skill directory.

Symlink local folders:

```bash
mkdir -p "${CODEX_HOME:-$HOME/.codex}/skills"
ln -s "$PWD/bioinfo-analysis-plan" "${CODEX_HOME:-$HOME/.codex}/skills/bioinfo-analysis-plan"
ln -s "$PWD/bioinfo-validation-pyramid" "${CODEX_HOME:-$HOME/.codex}/skills/bioinfo-validation-pyramid"
ln -s "$PWD/bioinfo-watchdog" "${CODEX_HOME:-$HOME/.codex}/skills/bioinfo-watchdog"
ln -s "$PWD/bioinfo-result-review" "${CODEX_HOME:-$HOME/.codex}/skills/bioinfo-result-review"
```

Or copy local folders:

```bash
mkdir -p "${CODEX_HOME:-$HOME/.codex}/skills"
cp -r bioinfo-analysis-plan bioinfo-validation-pyramid bioinfo-watchdog bioinfo-result-review "${CODEX_HOME:-$HOME/.codex}/skills/"
```

Restart Codex after copying.
