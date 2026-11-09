# moneyhoneypot98-star's November Contributions

A summary of security contributions by moneyhoneypot98-star in November 2026:

- Reported a cross-caller lock hijack vulnerability in `tari-ootle` walletd, submitted through GitHub Security Advisories and tracked in `GHSA-57p9-3cv5-5hqm`.
- The report showed that a `Transactions(Create)`-scoped API key could bind other callers' locks, make walletd sign with other callers' account and stealth keys, and force fee expenditure on the victim's account on chain.
- Testing was performed locally on the Tari testnet/lab environment only; no shared network was touched.
- Coordinated the finding through private disclosure; the fix was implemented by the Tari team in `tari-project/tari-ootle#3225`. Technical details remain in the advisory until it is published. The contribution is tracked in `tari-project/special_contributions#447`.
