# sonson0910's October Contributions

A summary of security contributions by sonson0910 in October 2026:

* Reported a security vulnerability in `tari`: a consensus mismatch between archival nodes (`pruning_horizon == 0`) and pruned nodes on same-block re-mine and spend of a previously spent output in `tari_core` block validation, tracked in `GHSA-47hf-mmpx-vcm7`. The report included a root-cause analysis, runnable regression tests, and a suggested fix; testing was performed locally only. Coordinated through private disclosure; the fix is being implemented by the Tari team. Technical details remain in the advisory until it is published. This contribution is tracked in `tari-project/special_contributions#344`.
* Reported a High-severity security vulnerability in `tari`: permanent blacklisting of canonical block headers and honest peer banning via out-of-order header sync stream and median timestamp window ratchet in `BlockHeaderSyncValidator` (`GHSA-wmp5-x98r-r72j`, fixed in `tari-project/tari#8195`). The report included a root-cause analysis, runnable unit tests, and a suggested remediation. This contribution is tracked in `tari-project/special_contributions#383`.
