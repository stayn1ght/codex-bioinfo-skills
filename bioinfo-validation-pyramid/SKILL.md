---
name: bioinfo-validation-pyramid
description: Use before launching full-scale bioinformatics analyses, especially expensive or long-running sequence analysis workflows. Applies to FASTQ, BAM, FASTA, GFF/GTF, TSV/CSV, mapping, assembly, binning, annotation, abundance, coverage, overlap, and clustering tasks.
---

# Bioinformatics Validation Pyramid

Use this skill before any full-scale bioinformatics run. Validate from cheap file checks to small end-to-end execution before launching expensive work.

## L0 File & Format Validity

Goal: confirm inputs exist, are readable, correctly formatted, indexed when needed, and match expected schema.

FASTQ:
- file exists
- gzip integrity
- read count > 0
- paired-end read counts match
- read IDs are compatible
- read length distribution is plausible

BAM:
- file exists
- index exists
- header readable
- contig names available
- mapped reads > 0
- sort status appropriate

FASTA:
- sequence count > 0
- sequence IDs unique
- length distribution plausible
- no invalid characters

GFF/GTF:
- contig IDs match FASTA
- start < end
- coordinates within contig length
- feature type valid

TSV/CSV:
- required columns exist
- numeric columns parse correctly
- key columns are not unexpectedly duplicated
- sample IDs match metadata

## L1 Small-data Correctness

Goal: validate script logic with toy data or very small real data before full inputs.

Check:
- row counts
- coordinate conversion
- overlap logic
- filtering logic
- join behavior
- empty input behavior
- expected vs observed output

Prefer hand-checkable tests and tiny fixtures. Do not jump straight to full-scale data to discover logic errors.

## L2 Biological / Sequence Sanity

Goal: confirm outputs are biologically and technically plausible.

Mapping:
- read count
- mapping rate
- mapped reads
- MAPQ distribution
- coverage distribution
- duplicate rate if available

Assembly:
- contig count
- total length
- N50
- GC distribution
- shortest and longest contig

Binning:
- bin count
- completeness / contamination if available
- bin coverage consistency
- taxonomy sanity if available

Annotation:
- feature count
- gene density
- coordinate validity
- annotation ID uniqueness
- target feature presence

Abundance / differential:
- sample count
- group labels
- library size distribution
- zero inflation
- top features not dominated by one sample

## L3 End-to-End Dry Run

Goal: run 1-2 small samples from input to final output.

Check:
- all expected outputs generated
- logs saved
- downstream reads upstream outputs
- checkpoints work
- summary report generated
- file naming consistent

## Full-scale Gate

A full-scale run is not allowed until L0-L3 pass or the user explicitly overrides.

When validation fails, report:

```text
failed layer:
evidence:
likely cause:
smallest safe next fix:
```
