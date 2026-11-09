# fandiyana's October Contributions

A summary of security contributions by fandiyana in October 2026:

* Reported a consensus availability vulnerability in `tari-ootle`, submitted through GitHub Security Advisories and tracked in `GHSA-6g74-qmhj-9gx9`.
* The report showed that a replica crashes fatally when a `LocalAccept` references a foreign input pledge it has not stored yet. It included a root-cause analysis and a suggested fix.
* Testing was performed locally only; no shared network was touched.
* Coordinated the finding through private disclosure; the fix was applied by the Tari team in `tari-ootle#3139`. Technical details remain in the advisory until it is published. The contribution is tracked in `tari-project/special_contributions#357`.