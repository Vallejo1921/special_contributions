# Ryanmahrez44's October Contributions

A summary of security contributions by Ryanmahrez44 in October 2026:

* Reported a security vulnerability in `tari-ootle`, submitted through GitHub Security Advisories and tracked in `GHSA-5qfh-xpq7-4rpq`.
* The report showed that unauthenticated follow-state-sync stream lets one minority committee member permanently poison the indexer store. It included a root-cause analysis and a suggested fix.
* Testing was performed locally only; no shared network was touched.
* Coordinated the finding through private disclosure; the fix is being implemented separately by the Tari team. Technical details remain in the advisory until it is published. The contribution is tracked in `tari-project/special_contributions#325`.
