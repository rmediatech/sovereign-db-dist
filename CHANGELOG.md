# Changelog

All notable changes to this project will be documented in this file.

The format is based on [Keep a Changelog](https://keepachangelog.com/en/1.0.0/),
and this project adheres to [Semantic Versioning](https://semver.org/spec/v2.0.0.html).

## [0.2.0] - 2026-11-06

### Added & Re-Architected (`SOVEREIGN-CHANGELOG-E2E-01`)
- **`[State / Replication]` Hybrid Logical Clocks (HLC) & Merkle-DAG WAL CRDT Replication (`sovereign-db::replication`)**:
  - *Root Cause Dissection*: Multi-node distributed read replicas previously suffered from clock drift and potential double-spend windows during transient partition splits.
  - *Architectural & Mathematical Resolution*: Implemented Lamport Hybrid Logical Clocks (RFC 3339 monotonic physical + logical counter) combined with Merkle-DAG WAL delta streaming, guaranteeing deterministic convergent causality across private fleet mesh nodes.
  - *Empirical Verification*: Verified with adversarial split-brain and concurrent mutation crucible tests.

---

## [0.1.0] - 2026-10-15

### Added
- Bare-metal NVMe SQLite WAL engine with 256MB memory mapping.
- Microsecond query evaluation with atomic conditional anti-double-spend guardrails.
- Cryptographic Merkle provenance anchoring via `sovereign-ledger`.
