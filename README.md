# Codex Bioinformatics Skills

Instruction-only Codex skills for bioinformatics analysis workflows.

## Skills

- `bioinfo-analysis-plan`: plan bioinformatics workflows before writing commands or code.
- `bioinfo-validation-pyramid`: validate inputs, small examples, biological sanity, and dry runs before full-scale analyses.
- `bioinfo-watchdog`: monitor long-running bioinformatics jobs in read-only mode.
- `bioinfo-result-review`: review outputs before declaring analyses complete or ready for downstream use.

## Install

Recommended: install from inside Codex with `$skill-installer`.

Replace `<owner>` with the GitHub owner or organization that hosts this repository.

```text
$skill-installer install https://github.com/<owner>/codex-bioinfo-skills/tree/main/bioinfo-analysis-plan
$skill-installer install https://github.com/<owner>/codex-bioinfo-skills/tree/main/bioinfo-validation-pyramid
$skill-installer install https://github.com/<owner>/codex-bioinfo-skills/tree/main/bioinfo-watchdog
$skill-installer install https://github.com/<owner>/codex-bioinfo-skills/tree/main/bioinfo-result-review
```

Restart Codex after installation so the new skills are discovered.

## Local Development Fallback

If you are working from a local clone or cannot download from GitHub, copy the
skill folders into Codex's skill directory:

```bash
mkdir -p "${CODEX_HOME:-$HOME/.codex}/skills"
cp -r bioinfo-analysis-plan bioinfo-validation-pyramid bioinfo-watchdog bioinfo-result-review "${CODEX_HOME:-$HOME/.codex}/skills/"
```

Restart Codex after copying.
