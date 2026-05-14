# hekate-keccak

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

## License

Apache-2.0. See [LICENSE](LICENSE) and [NOTICE](NOTICE).