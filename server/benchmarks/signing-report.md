# Signing Benchmark Report

Generated: 2026-03-25T06:37:01.370Z
Iterations: 5000
Warmup iterations: 500

| Implementation | Avg (ms) | P50 (ms) | P95 (ms) | Ops/sec | Relative to Node |
| --- | ---: | ---: | ---: | ---: | ---: |
| Node stellar-sdk | 0.0860 | 0.0747 | 0.1338 | 11630.50 | 1.00x |
| Rust ed25519-dalek | 0.1595 | 0.1506 | 0.1755 | 6268.10 | 0.54x |

Node min/max: 0.0653 ms / 4.1136 ms
Rust min/max: 0.1221 ms / 6.7547 ms

Methodology:
- Builds one unsigned fee-bump transaction per benchmark run.
- Signs the same transaction repeatedly after clearing signatures to isolate signing latency.
- Verifies parity first to ensure the Rust signer produces the same Ed25519 signature over the Stellar transaction hash as the current Node implementation.
