# {Many & Few}

A finite framework with 0 as the absolute, built around exact fingerprinting, canonical texts, and reversible links to 2-D DNA walk models.

This repository is a reproducible research sandbox and publication draft for the working idea that SHA-256 fingerprints can be linked to DNA-like walks in the plane, while preserving a tamper-evident, reversible encoding chain.

**Author:** Christopher Thomas Ronio

## Status

- Publication draft: active working draft
- Version: v0.1.0
- License: MIT
- Focus: mathematical framework + reproducible evidence + draft proposal

## Core idea

The repository formalizes a reversible encoding chain:

- fingerprint (SHA-256 hex)
- canonical text
- DNA string (128 bases)
- 2-D walk in Z^2
- endpoint and slack structure

The framework distinguishes between:

- exact information preserved by the full path;
- lossy reductions that compress the walk to an endpoint; and
- transformation rules that reframe the same underlying sequence without changing its fingerprint.

The repository is intentionally careful to separate what is established from what is proposed:

- Established: the encoding chain is reversible at the path level and tested against tampering.
- Proposed: the bridge laws and the DNA-walk analogy describe real biological sequences or a universal biological law.
- Not claimed: the repository's DNA strings are biological genomes or encodings of hash values in any literal genomic sense.

## Repository structure

- `README.md` — project overview and quick start
- `LICENSE` — MIT license
- `CITATION.cff` — citation metadata
- `PROPOSAL.md` — research proposal and draft manuscript
- `canonical/` — exact source texts behind the fingerprints
- `dnalink/` — implementation of the fingerprint/DNA/walk pipeline
- `tests/` — unit tests for round-trip correctness and framework laws
- `scripts/` — reproducibility scripts
- `evidence/` — generated evidence tables and figures

## Quick start

```bash
bash scripts/verify.sh
```

This checks:

- fingerprint integrity (`sha256sum -c fingerprints.sha256`)
- unit tests
- evidence regeneration

## Reproducible verification

```bash
bash scripts/verify.sh
```

The repository is designed so that the evidence and the key tests can be regenerated locally from source.

## Key research questions

The working proposal explores whether the framework's fingerprints can be linked to 2-D DNA walk models in a way that is both reversible and testable, and whether the framework's decomposition and transformation bridges predict measurable structure when applied to real sequences.

The current draft highlights two principal questions:

1. Can a fingerprint be recovered from its DNA-walk representation without losing the underlying sequence truth?
2. Do the framework's quantities — such as slack, endpoint distance, and zone labels — separate sequence classes in a way that survives the choice of walk rule?

## Evidence in this repo

The project includes generated evidence showing that:

- fingerprint -> DNA -> walk -> DNA -> fingerprint round trips correctly;
- single-base changes are detected;
- the walk law commutes with the lattice symmetries tested;
- rule choice changes the frame but not the underlying fingerprint;
- endpoint-only summaries are lossy and cannot recover the sequence fingerprint.

See `evidence/results.md` and `evidence/walks.svg` for the generated results.

## Citation

If you use this work, please cite it as:

```text
Ronio, C. T. (2026). Linking {Many & Few} fingerprints to 2-D DNA walk models. Working draft v0.1.
```

CITATION metadata is provided in `CITATION.cff`.

## Publication framing

This project should be read as a reproducible mathematical and computational draft rather than as a claim about biology. The proposal is intentionally explicit about the boundary between:

- an exact encoding result,
- a tested computational model,
- and a biological hypothesis requiring additional validation.

## Support continued research

If you find this work valuable and wish to support continued research and development, contributions are welcome:

**Bitcoin address:** `bc1qhl09nvanfsest9zy02hm8dx063jv8adhtteuh7`

## License

This project is licensed under the MIT License. See `LICENSE` for details.

## Contact

For questions or collaboration, please contact the repository maintainer or use the project discussion and issue tracker on GitHub.
