# Contributing to {Many & Few}

Thank you for your interest in contributing to this research project. This document outlines how to participate, report issues, and propose improvements.

## Code of conduct

This project follows a code of respect and scientific integrity. Be civil, constructive, and open to differing viewpoints.

## How to contribute

### Reporting issues

If you find a bug or have a question, please open an issue on GitHub:

1. **Check existing issues** first to avoid duplicates
2. **Use a clear title** that describes the problem or question
3. **Include details:**
   - What you did (steps to reproduce)
   - What you expected
   - What actually happened
   - Your environment (Python version, OS, etc.)
4. **Attach relevant files** (code snippets, output logs) if helpful

### Asking research questions

If you have a question about the framework, the DNA walk model, or the proposal, please use **GitHub Discussions** rather than Issues. This keeps the issue tracker focused on bugs and concrete improvements.

### Proposing improvements

Before starting large work, please open a Discussion or Issue to check that your idea aligns with the project scope:

1. **Describe the improvement** and why it matters
2. **Link to relevant sections** of the framework (README.md, Geometric.md, Bridges.md, PROPOSAL.md)
3. **Wait for feedback** before investing significant effort

### Submitting changes

To contribute code or documentation:

1. **Fork the repository** on GitHub
2. **Create a feature branch** from `main`:
   ```bash
   git checkout -b your-feature-name
   ```
3. **Make your changes** and commit with clear messages:
   ```bash
   git commit -m "Brief description of the change"
   ```
4. **Add tests** if your change affects code:
   ```bash
   python3 -m unittest discover -s tests
   ```
5. **Run the full verification suite:**
   ```bash
   bash scripts/verify.sh
   ```
6. **Push to your fork:**
   ```bash
   git push origin your-feature-name
   ```
7. **Open a pull request** on the main repository with:
   - A clear title and description
   - A reference to any related issues
   - Confirmation that `bash scripts/verify.sh` passes

## What kinds of contributions are welcome

### Bug fixes
- Errors in the code or documentation
- Typos or clarity issues
- Test failures or edge cases

### Code improvements
- Optimizations (speed, memory, clarity)
- Better test coverage
- Cleaner API design

### Framework refinements
- Clarifications or corrections to the axioms (A1-A3)
- Refinements to the geometry (G1-G5)
- Extensions or corrections to the Decomposition or Transformation bridges

### Real genome tests
- Implementation of H1, H2, H3 on public genomes
- New walk rules or representations
- Analysis of sequence composition and structure

### Documentation
- Clearer explanations in README.md, Geometric.md, Bridges.md
- Additional examples or worked problems
- Background references or related work

## Scope and boundaries

**In scope:**
- The mathematical framework and its formal properties
- Reversible encoding between fingerprints, DNA strings, and walks
- Code that implements or tests the framework
- Hypothesis testing on real sequences (H1, H2, H3)

**Out of scope (for now):**
- Claims about biological mechanisms or evolutionary significance
- Medical or diagnostic applications
- 3-D or higher-dimensional representations (listed as open in PROPOSAL.md section 8)
- Integration with external databases or APIs (except as test data sources)

If you're unsure whether your idea is in scope, please open a Discussion first.

## Testing and verification

All changes must pass:

```bash
bash scripts/verify.sh
```

This runs:
- SHA-256 fingerprint checks
- Unit tests
- Evidence regeneration

If you add new code or change existing logic, also add unit tests in the `tests/` directory.

## Commit messages

Write clear commit messages:
- First line: 50 characters or less, imperative mood ("Add feature" not "Added feature")
- Blank line
- Body: explain *why* the change matters, not just what changed
- Reference issues or discussions where relevant

Example:
```
Fix off-by-one error in slack calculation

The slack computation was adding 1 to the walk length, which
produced incorrect values for endpoints near the origin.
Fixes issue #42.
```

## Pull request process

1. One feature or fix per pull request
2. Keep PRs focused and reasonably sized (aim for <500 lines of changes)
3. Ensure your branch is up to date with `main` before submitting
4. Respond to review feedback promptly
5. Squash commits if requested during review

## Attribution

Contributors will be acknowledged in:
- Pull request descriptions
- CHANGELOG.md
- Project documentation where appropriate

## Questions?

- **GitHub Issues:** bug reports and concrete problems
- **GitHub Discussions:** questions, ideas, and research directions
- **Contact:** reach out to the repository maintainer

## License

By contributing, you agree that your contributions will be licensed under the same MIT License as the project.

---

Thank you for helping improve {Many & Few}!
