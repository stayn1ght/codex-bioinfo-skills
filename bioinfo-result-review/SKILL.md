---
name: bioinfo-result-review
description: Use before declaring a bioinformatics analysis complete, ready for downstream use, or ready for full-scale execution. Applies after scripts, commands, or workflows generate sequence-analysis outputs.
---

# Bioinformatics Result Review

Use this skill before saying a bioinformatics analysis is done, fixed, complete, ready for downstream use, or ready for full-scale execution.

## Review Checklist

Output existence:
- all expected files exist

Output freshness:
- outputs are newer than the command/script that generated them when relevant
- logs correspond to the current run

Output size:
- files are not empty unless expected
- sizes are plausible

Row count:
- rows match expected units
- no unexpected massive expansion or collapse

Key consistency:
- sample_id / contig_id / gene_id / cluster_id join correctly
- no unexpected duplicated keys
- no large unexplained drop after joins

Metric sanity:
- key metrics in plausible ranges
- no impossible values
- no all-zero outputs unless expected

Failure samples:
- failed or suspicious samples listed explicitly

Reproducibility:
- commands recorded
- parameters recorded
- software versions recorded when possible
- logs saved

Decision:
- ready for next step
- needs manual inspection
- failed validation

## Completion Rules

Do not say "done", "fixed", "complete", or "ready for full run" unless result review has fresh evidence.

If evidence is incomplete, say exactly what is missing and propose the smallest validation step.
