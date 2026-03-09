# Rust Project: Hello World

A first Rust programming example.

## 🛠 Build & Quality Commands

- **Build**: `cargo build`
- **Test**: `cargo test`
- **Lint**: `cargo clippy -- -D warnings`
- **Format**: `cargo fmt`
- **Document**: `cargo doc --open`

## 🛡️ Critical Safety Guardrails

- **Zero Unwraps**: Use of `.unwrap()` or `.expect()` is FORBIDDEN. Use `thiserror` for library errors or `anyhow` for application-level propagation with `?`.
- **Borrow Checker First**: Before using `unsafe`, `Rc`, or `Arc`, attempt to resolve ownership issues through better data structure design.
- **Memory Safety**: Avoid unnecessary `.clone()` calls. Prefer borrowing (`&T`, `&mut T`) over ownership for function arguments unless the data is consumed.
- **No Side Effects**: Never commit commented-out code, debug `println!` statements, or `dbg!` macros.

## 🧪 Development Workflow

- **TDD Mandatory**: Create or update unit tests in a `tests` module BEFORE or alongside implementation. Ensure all edge cases for inputs are covered.
- **Plan Mode**: (Shift+Tab x2) Use Plan Mode to research the codebase and propose architectural changes before execution.
- **Atomic Commits**: Each commit must compile, pass `clippy`, and pass all tests. Use Conventional Commits format.

## 🦀 Rust Coding Style

- **Idiomatic Patterns**: Use iterator patterns (`map`, `filter`, `fold`) instead of manual loops. Use `match` and `if let` for expressive control flow.
- **Types**: Use PascalCase for types/traits, snake_case for functions/variables, and SCREAMING_SNAKE_CASE for constants.
- **Async**: Use the `Tokio` runtime for async code. Ensure all async operations are compatible with strict ownership rules.
- **Public API**: Include doc comments for all public functions, structs, and enums, including parameter and error documentation.

## 💡 Performance Guidelines

- **Allocations**: Minimize heap allocations. Move from `String` to `&str` or `Cow<str>` in hot paths where possible.
- **Concurrency**: Use `rayon` for CPU-bound parallelism and `tokio` for I/O-bound tasks. Prefer `RwLock` over `Mutex` when read-heavy.
- **Profiling**: If performance issues arise, prioritize algorithmic O(n) efficiency and SIMD opportunities.

## 📂 Project Structure

- `src/`: Main source code.
- `tests/`: Integration tests.
- `examples/`: Usage examples for the library.
