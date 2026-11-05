# Yzgaming005's November Contributions

A summary of security contributions by @Yzgaming005 in November 2026:

* Security report: the tari-ootle wallet builds transactions using values taken from its configured indexer — fee pool balances, a destination account's vault ids, and input substate versions — and does not verify them against a proof before signing. A dishonest or compromised indexer can supply values that cause the user's transaction to fail, or that misrepresent the state the wallet signs against. Reported in a GitHub issue (`tari-project/tari-ootle#2808`, ISSUE-2808); testing was performed locally only, no shared network was touched. The fix was implemented separately by the Tari team in several PRs relating to wallet lightclient proof verification. Tracked in `tari-project/special_contributions#379`.
