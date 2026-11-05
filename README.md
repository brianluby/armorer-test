# Armorer consumer rehearsal fixture

This dependency-free Rust library is an inert, non-publishing fixture for an
**authorized rehearsal only**. `Cargo.toml` sets `publish = false`; it has no
runtime behavior, build script, credentials, workflows, signing, attestation,
or dispatch surface.

`armorer.toml` declares only this fixture and its intended Rust 1.95.0 toolchain.
`ci-policy.PROPOSED.toml` is copied from Armorer's dependency-free MIT library
bootstrap example and is explicitly **PROPOSED**, not reviewed project policy.
It grants no production authority.

## Boundaries and blockers

No bootstrap catalog, Armorer lock, roots, or runtime has been approved for this
consuming repository. Do not apply a catalog or bootstrap plan here. Armorer
bootstrap examples render catalog-backed locks and workflow pins, which would
introduce unapproved authority; they are intentionally not copied into this fixture.
Rehearsal plan artifacts, if any, must remain outside this repository. No signing,
attestation, privileged, or dispatch workflow exists or may be added before the
relevant approvals.

## Owner-authorized single-owner rehearsal exception

The owner authorized a **SINGLE-OWNER REHEARSAL EXCEPTION** for the configured
`armorer-test` release-signing environment: reviewer `brianluby` (ID `3779002`),
with self-review allowed, administrator bypass disabled, and the `main` branch as
the only allowed deployment branch. Manual approval is still required. This
exception does **not** satisfy independent-approval acceptance and does not relax
any implementation verifier. It authorizes neither publication nor the missing
roots, catalog, runtime, project-policy, workflow, attestation, or signing work in
this fixture.

This fixture does not assert CI, release, publication, provenance, or signing
readiness.

## Local verification

Run only the requested locked Cargo checks with the Rust 1.95.0 toolchain:

```sh
RUSTC_WRAPPER= rustup run 1.95.0 cargo fmt --check
RUSTC_WRAPPER= rustup run 1.95.0 cargo clippy --locked --all-targets --all-features -- -D warnings
RUSTC_WRAPPER= rustup run 1.95.0 cargo test --locked
RUSTC_WRAPPER= rustup run 1.95.0 cargo build --locked
```
