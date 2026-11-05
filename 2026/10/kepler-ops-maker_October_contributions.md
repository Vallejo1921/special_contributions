# kepler-ops-maker's October Contributions

A summary of security contributions by kepler-ops-maker in October 2026:

* Reported an indexer-trust vulnerability in `tari-ootle`, submitted through GitHub Security Advisories and tracked in `GHSA-3x9g-j64h-88m2`.
* The report showed that a malicious indexer can mark wallet stealth UTXOs frozen or burnt through unverified status reads, blocking stealth spends. It included a root-cause analysis and a suggested fix.
* Testing was performed locally only; no shared network was touched.
* Coordinated the finding through private disclosure; the fix was applied by the Tari team in `tari-ootle#3059`. Technical details remain in the advisory until it is published. The contribution is tracked in `tari-project/special_contributions#299`.

* Reported an indexer-trust vulnerability in `tari-ootle`, submitted through GitHub Security Advisories and tracked in `GHSA-f8q7-c3p5-2wpg`.
* The report showed that a malicious indexer can plant phantom unspent stealth outputs: recovered UTXOs are committed without up-state proof, even under `IndexerTrust::Verify`. It included a root-cause analysis and a suggested fix.
* Testing was performed locally only; no shared network was touched.
* Coordinated the finding through private disclosure; the fix was applied by the Tari team in `tari-ootle#3092`. Technical details remain in the advisory until it is published. The contribution is tracked in `tari-project/special_contributions#315`.
