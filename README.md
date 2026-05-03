# pipeline-architect

A Claude Code slash command (`/pipeline-architect`) that generates a complete bioinformatics pipeline from a methods section or experiment description.

## What it does

Paste a sequencing experiment description and the command will:

1. Detect the sequencing type (currently supports **scRNA-seq** and **shotgun metagenomics**)
2. Produce a numbered **Pipeline Plan** with recommended tools, versions, and rationale
3. Generate a ready-to-run **Snakemake skeleton** (`Snakefile` + `config.yaml`)
4. Output a pinned **conda environment** (`environment.yml`)
5. Write all three files to a directory of your choosing

## Installation

Copy `pipeline-architect.md` into your Claude Code commands directory:

```
# macOS / Linux
cp pipeline-architect.md ~/.claude/commands/

# Windows
copy pipeline-architect.md %USERPROFILE%\.claude\commands\
```

Then invoke it in any Claude Code session:

```
/pipeline-architect <paste your methods section here>
```

## Supported experiment types

| Experiment | Key signals detected |
|---|---|
| Shotgun metagenomics | Assembly, taxonomic classification, microbial/environmental samples |
| scRNA-seq | Cell barcodes, UMIs, 10x Genomics, Cell Ranger, per-cell expression |
