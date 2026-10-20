# okansaglam016161-pixel's October Contributions

A summary of contributions by okansaglam016161-pixel in October 2026:

- Reported a bug in the `tari-ootle` indexer's substate cache to the Tari team.
- The report showed that the cache turns every null in a cached component state into an empty array. `Value::Null` was serialized through `serialize_unit`, which `tari_bor::serde_codec` encodes as an empty array (`0x80`), so an `Option::None` field reads back as `[]`.
- Consequence: a dry run against a component with an `Option::None` field works on the first, uncached fetch, then fails with an `EngDcdFail` decode error once the corrupted copy is served from the cache. Provided the root cause, an offline reproduction of the codec round trip, and live dry runs showing the failure on a caching indexer.
- The fix was implemented separately by @sdbondi in `tari-project/tari-ootle#2870`. The contribution is tracked in `tari-project/special_contributions#136`.
- Reported a bug in `tari-ootle`'s walletd transaction input detection to the Tari team, as a public GitHub issue (`tari-project/tari-ootle#2950`).
- The report showed that walletd detects a transaction's inputs with `IndexedValue::referenced_substates()`, which listed only four substate kinds, while the engine validates a call's arguments against the full ten-kind list. Any argument holding one of the six missing kinds (templates, transaction receipts, claimed-output tombstones, UTXOs, confidential outputs, validator fee pools) is never declared as an input, so the transaction is rejected with "Template referenced substate but it was not found" after the fee is paid.
- Provided the root cause with file and line, a minimal dry-run reproduction, the affected walletd and SDK paths, and a proposed fix with a regression-test idea.
- The fix was implemented separately by @sdbondi in `tari-project/tari-ootle#2942`. The contribution is tracked in `tari-project/special_contributions#210`.
- Reported a bug in `tari-ootle`'s transaction manifest encoding to the Tari team, as a public GitHub issue (`tari-project/tari-ootle#2951`).
- The report showed that a manifest argument written as `address!("template_…")` is encoded as a tagged `PublishedTemplateAddress` (CBOR tag 137), whereas a template method's `TemplateAddress` parameter is a plain `Hash32` decoded as untagged bytes. The argument fails to decode even when the template substate is declared as an input, which makes template-address parameters unusable from a manifest.
- Provided the root cause with file and line, a dry-run reproduction of the decode error, the `hex_bytes!` workaround, and the open question of which side should change.
- The fix was implemented separately by @sdbondi in `tari-project/tari-ootle#2942`. The contribution is tracked in `tari-project/special_contributions#211`.
- Reported a bug in `tari-ootle`'s stealth-amount handling at the WASM boundary to the Tari team, as a public GitHub issue (`tari-project/tari-ootle#2982`).
- The report showed that the ootle-wasm / ootle.ts SDK takes stealth amounts as `u64`, so a `bigint` outside the `u64` range is reduced modulo 2^64 by the WebAssembly JS boundary (`ToBigInt64`) while the TypeScript SDK checks only that it is positive. An amount of 2^64 + 5 is built, proven and validated as 5, and -1 becomes `u64::MAX`, so an SDK caller can produce a statement for a different amount than it passed.
- Provided the root cause with file and line, an offline reproduction against the published packages, the engine-side bound that keeps it off-chain, and a proposed guard with a regression test.
- The fix was implemented separately by @sdbondi in `tari-project/tari-ootle#2983`. The contribution is tracked in `tari-project/special_contributions#237`.
- Reported a security vulnerability in `tari-ootle`'s consensus to the Tari team through a private GitHub Security Advisory (`GHSA-x45g-95p8-g67h`).
- The report showed that the cross-shard LocalPrepared path could lock a transaction's local inputs without the validity-window check, and that the `tari-project/tari-ootle#2905` expiry timeout did not cover a transaction whose `max_epoch` is outside the window. Tari confirmed the code gap and treated it as hardening.
- Provided the root cause with file and line, lock-step regression tests demonstrating the stuck lock, and a proposed fix. The fix was implemented separately by @sdbondi in `tari-project/tari-ootle#2988`. The contribution is tracked in `tari-project/special_contributions#240`.
