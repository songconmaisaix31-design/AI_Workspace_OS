# Project Memory

## Workspace

- Project: `AI_Workspace_OS`
- Created: `2026-07-30`
- Current stack: no project stack detected.

## Durable Decisions

- Use existing package or application channels for reinstalls instead of introducing parallel installations.
- Keep credentials, secret values, machine-specific paths, and private runtime data out of public history.
- Exclude downloads, temporary files, environment files, and private-key files from publication.

## Operations

- Open Design `0.16.1` was installed from the official `nexu-io/open-design` GitHub release.
- Official installer SHA-256: `8D6712A522517DE9FF7CA996645442F4E23E4DF6F1E95681C8603D94BA5BF7EA`.
- The Windows binaries are unsigned; require an exact match with the checksum published on the official GitHub release before installation.
- A smoke test using an isolated user-data directory opened a responsive Open Design window successfully.

## Publication

- The repository was published on `2026-08-13` from a sanitized root history.
- The public snapshot contains only `.gitignore`, `AGENTS.md`, and `MEMORY.md`; downloads, temporary files, environment files, and private-key files remain excluded.
- Directory and full-history Gitleaks scans passed before publication.
