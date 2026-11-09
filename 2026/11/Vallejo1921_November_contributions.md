# Vallejo1921's November Contributions

A summary of contributions by Vallejo1921 in November 2026:

- Contributed an exact CBOR decoding hardening to `tari-ootle` in [tari-project/tari-ootle#3331](https://github.com/tari-project/tari-ootle/pull/3331).
- The hardening enforces strict exact-length CBOR deserialization across non-consensus entrypoints (`Substate::from_bytes`, `TemplateMetadata::from_cbor`, and `arg_to_value`), rejecting inputs with trailing unconsumed bytes.
- Eliminates parser permissiveness where malicious or malformed payloads could embed trailing unparsed bytes past valid data.
- Merged into `development` by the Tari team.
- This contribution is tracked by `tari-project/special_contributions#458`.

- Contributed transaction validation hardening to `tari-ootle` in [tari-project/tari-ootle#3330](https://github.com/tari-project/tari-ootle/pull/3330) addressing issue #1210 (`Limiit permitted instructions for fee instructions`).
- Enforces restrictions on instructions permitted in fee instructions to prevent non-paying fee intent execution.
- This contribution is tracked by `tari-project/special_contributions#489`.

- Contributed deterministic validator node identity and fee claim key derivation to `tari-ootle` in [tari-project/tari-ootle#3386](https://github.com/tari-project/tari-ootle/pull/3386) addressing issue #601 (`Validator node identity and secret keys should be derived from a seed phrase`).
- Implemented derivation of validator node identity and fee claim keys from 24-word `CipherSeed` / `SeedWords`, added CLI support (`--seed-words`, `--seed-words-file`, `--seed-passphrase`), and automated fee claim key setup.
- Merged into `development` by the Tari team.
- This contribution is tracked by `tari-project/special_contributions#513`.
