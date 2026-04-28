# Crucible Backend

This is the backend component of the Crucible project, providing a JSON schema generator utility.

## Features

- JSON Schema generation using `schemars`
- Async HTTP server with Axum
- PostgreSQL database integration with SQLx
- Redis caching and job queues
- Comprehensive error handling and tracing

## Usage

Add to your `Cargo.toml`:

```toml
[dependencies]
crucible-backend = { path = "../backend" }
```

Then use the JSON schema generator:

```rust
use crucible_backend::utils::json_schema::generate_json_schema;
use serde::{Deserialize, Serialize};
use schemars::JsonSchema;

#[derive(Serialize, Deserialize, JsonSchema)]
struct MyStruct {
    field: String,
}

let schema = generate_json_schema::<MyStruct>();
```

## Running Tests

```bash
cargo test --manifest-path backend/Cargo.toml
```

## Building

```bash
cargo build --manifest-path backend/Cargo.toml
```