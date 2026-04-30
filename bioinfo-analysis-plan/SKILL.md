---
name: bioinfo-analysis-plan
description: Use when planning or modifying a bioinformatics analysis workflow involving sequence files, genomic intervals, metadata tables, mapping, assembly, annotation, coverage, overlap, clustering, or HPC jobs. Do not use for ordinary non-bioinformatics coding tasks.
---

# Bioinformatics Analysis Plan

Use this skill to convert vague bioinformatics requests into executable, verifiable steps before writing code or commands.

## Required Plan

Before implementing, output this plan:

```text
Analysis objective:
Input files:
Unit of analysis:
Output files:
Task breakdown:
Validation plan:
Runtime class:
Failure risks:
```

`Unit of analysis` must be explicit, for example:

```text
read / read pair / contig / interval / gene / protein / bin / MAG / sample / sample pair / cluster / taxon / pathway
```

Prefer small, composable tasks. Do not start by writing a giant pipeline.

## Task Template

Each task must include:

```text
Task name:
Input:
Output:
Script or command:
Expected output schema:
Validation command:
Failure modes:
```

## Common Failure Risks

Consider these risks explicitly when planning:

```text
file format mismatch
missing index
sample ID mismatch
coordinate convention mismatch
contig name mismatch
empty output
duplicated IDs
low mapping rate
excessive runtime
disk or memory failure
```

## Completion Rules

Do not implement until the plan has explicit inputs, outputs, validation checks, and failure modes.

Do not mark complete unless expected outputs exist, are fresh, and pass validation.
