# Workspace compatibility policy

All workspace members inherit `edition = "2024"` and `rust-version = "1.85"` from the root `Cargo.toml`.

This is intentional. The integration suite uses Rust 2024 let-chain syntax, and downgrading an individual member to Rust 2021 causes `cargo fmt --all`, `cargo test --workspace`, and downstream path-dependency tooling to fail while parsing that member.

Do not replace `edition.workspace = true` with a package-local edition. Update the root policy only when changing the edition or minimum compiler for the entire fork.
