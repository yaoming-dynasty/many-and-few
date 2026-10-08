# Changelog

All notable changes to this project will be documented in this file.

The format is based on [Keep a Changelog](https://keepachangelog.com/en/1.0.0/), and this project adheres to [Semantic Versioning](https://semver.org/spec/v2.0.0.html).

## [v0.1.0] — 2026-10-08

### Added

- **Framework:** complete mathematical formalization with axioms (A1-A3), geometry (G1-G5), and bridge laws (Decomposition and Transformation)
- **README.md:** project overview, core idea, repository structure, and quick-start guide
- **Geometric.md:** detailed geometry of the framework and postulates
- **Bridges.md:** Decomposition and Transformation bridges and their commutativity properties
- **PROPOSAL.md:** research proposal linking fingerprints to 2-D DNA walk models, with evidence and testable hypotheses (H1-H3)
- **dnalink/:** complete implementation of reversible fingerprint ↔ DNA ↔ 2-D walk pipeline
  - `dnalink/encoding.py`: SHA-256 fingerprint to DNA string conversion
  - `dnalink/walk.py`: DNA sequence to 2-D walk generation (rules A and B)
  - `dnalink/analysis.py`: walk analysis (endpoints, slack, minimal paths, symmetries)
- **tests/:** unit tests covering round-trip correctness, tampering detection, and commutation with lattice symmetries
  - `tests/test_encoding.py`: fingerprint reversibility
  - `tests/test_walk.py`: walk generation and properties
  - `tests/test_bridges.py`: Decomposition and Transformation bridge laws
  - `tests/test_commutation.py`: walk commutes with 8 lattice symmetries
- **canonical/:** exact texts behind fingerprints (axioms, decomposition, transformation, crossed, geometric)
- **evidence/:** generated tables and figures
  - `evidence/results.md`: tabulated evidence for all 5 texts and both walk rules
  - `evidence/results.json`: machine-readable results
  - `evidence/walks.svg`: graphical visualization of walks in Z^2
- **scripts/:**
  - `scripts/verify.sh`: reproducibility check (fingerprints, tests, evidence)
  - `scripts/run_evidence.py`: generates evidence and results
- **fingerprints.sha256:** checkable SHA-256 fingerprints for canonical texts
- **CITATION.cff:** citation metadata
- **LICENSE:** MIT license
- **CONTRIBUTING.md:** guidelines for bug reports, questions, and contributions
- **.gitignore:** Python build artifacts

### Verified

- Fingerprint → DNA → walk → DNA → fingerprint round-trip correctness (both rules, all 5 texts)
- Single-base tampering detection (384/384 changes detected per sequence)
- Walk commutation with all 8 lattice symmetries (both rules, all 5 texts)
- Walk rules A and B are not related by any lattice symmetry
- Endpoint distance consistent with random walk (4.5–14.1 for 128-step walks, ~11.3 baseline)
- Endpoint carries only 8–10 bits of 256-bit fingerprint (max 14.0 bits)

### Known limitations

- Endpoints are lossy: fingerprints cannot be recovered from endpoints alone
- The encoding preserves sequence truth at the path level, not the minimal path level
- Hash output is pseudorandom by construction, so these walks resemble random walks
- No biological validation; H1, H2, H3 remain untested on real genomes
- Git history is not timestamped; consider publishing fingerprints with OpenTimestamps for provenance

### Open choices (from PROPOSAL.md section 8)

- [ ] Formal distinction between D_min (minimal path) and D_path (realized path) in Bridges.md
- [ ] Which walk rule is canonical for the framework (rule A makes complement pairs cancel)
- [ ] Real genome sets and sources for testing H1, H2, H3
- [ ] Whether 3-D or higher-dimensional representations are in scope
- [ ] Resolution of open choices in README.md, Geometric.md, and Bridges.md (Σ rule, others)

## Planned for future releases

- **v0.2.0:** testing H1, H2, H3 on public genomes (human, bacteria, ssDNA viruses)
- **v0.3.0:** extended walk rules (3-D, non-Manhattan metrics, custom symmetries)
- **v0.4.0:** formal definitions of D_min and D_path, refinement of bridge axioms
- **v1.0.0:** peer-reviewed publication and formal framework specification

---

## How to cite

```text
Ronio, C. T. (2026). Linking {Many & Few} fingerprints to 2-D DNA walk models. 
Working draft v0.1.0. GitHub: https://github.com/yaoming-dynasty/many-and-few
```

See CITATION.cff for metadata.
