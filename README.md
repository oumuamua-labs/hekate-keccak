# hekate-keccak

[![Crates.io](https://img.shields.io/crates/v/hekate-keccak.svg)](https://crates.io/crates/hekate-keccak)
[![Docs.rs](https://docs.rs/hekate-keccak/badge.svg)](https://docs.rs/hekate-keccak)
[![CI](https://github.com/oumuamua-labs/hekate-keccak/actions/workflows/ci.yml/badge.svg)](https://github.com/oumuamua-labs/hekate-keccak/actions/workflows/ci.yml)
[![License: Apache 2.0](https://img.shields.io/badge/License-Apache2-yellow.svg)](./LICENSE)

Keccak-f[1600] AIR chiplet for the [Hekate](https://github.com/oumuamua-labs/hekate) ZK proving system. Includes
SHA-3-256, SHA-3-512, SHAKE128, and SHAKE256 sponge constructions.

Virtual packing: 1600 state bits stored in 25 physical B64 columns instead of 1600 bit columns. Bits expand JIT in
registers during evaluation. ~16x memory savings vs. naive bit-column layout.

```
Scaling (Apple M3 Max):
  2^15 permutations (1,310): 919 ms, 92 MB peak, 1,312 KiB proof
  2^20 permutations (41,943): 14.16 s, 2.3 GB peak, 5,156 KiB proof
  2^24 permutations (671,088): 268 s, 31 GB peak, 20,209 KiB proof
```

## Examples

- [Keccak isolated chiplet (standalone AIR)](https://github.com/oumuamua-labs/hekate/blob/main/hekate/examples/keccak.rs)
- [Keccak inline kernel (CPU AIR with embedded permutation)](https://github.com/oumuamua-labs/hekate/blob/main/hekate/examples/keccak_inline.rs)

## Security & Audits

> [!WARNING]
> This implementation is currently UNAUDITED.
>
> It is provided "AS IS" with ABSOLUTELY NO WARRANTY under the terms
> of the Apache 2.0 License. The authors assume zero liability for
> any damages arising from its use in production environments.

## License

Apache-2.0. See [LICENSE](LICENSE) and [NOTICE](NOTICE).