# SigmaOS-runtime

Runtime component for SigmaOS.

## Development

```bash
cargo check
cargo test
```

Runtime interfaces should remain deterministic, memory-safe, and explicit about
platform assumptions and failure recovery.

## Process execution status

The process manager does not yet load or execute binary images. Its
`exec_process` API returns `false` even when a process has execution
capability, so callers do not mistake permission checks for successful
execution. The current library compile is blocked by pre-existing unresolved
runtime module exports in `pid_namespace.rs` and `lib.rs`.
