# Vallejo1921's October Contributions

A summary of contributions by Vallejo1921 in October 2026:

- Contributed a consensus fix to `tari-ootle` in [tari-project/tari-ootle#2915](https://github.com/tari-project/tari-ootle/pull/2915) (resolving [tari-project/tari-ootle#2845](https://github.com/tari-project/tari-ootle/issues/2845)).
- The fix addresses an issue where `prepare_multishard_output_only_transaction` blindly collected duplicate foreign pledges into a `HashMap`, silently overwriting substate requirements without checking version consistency.
- Replaced the version-blind collection with an explicit loop that verifies that duplicate pledges for the same requirement match expected versions (`existing.version() == version`), returning an `InvariantError` if mismatched.
- Merged into `development` by the Tari team.
- This contribution is tracked by `tari-project/special_contributions#218`.
- Contributed a consensus fix to `tari-ootle` in [tari-project/tari-ootle#2912](https://github.com/tari-project/tari-ootle/pull/2912).
- The fix ensures deterministic local certificate construction by sorting signatures when building `ProposalCertificate` and `TimeoutCertificate` from collected votes.
- Prevents nondeterministic certificate IDs and canonical vote ordering discrepancies across validator nodes.
- Merged into `development` by the Tari team.
- This contribution is tracked by `tari-project/special_contributions#259`.
- Contributed an indexer fix to `tari-ootle` in [tari-project/tari-ootle#2913](https://github.com/tari-project/tari-ootle/pull/2913).
- The fix verifies the template address against its published binary hash at the network boundary before caching in `tari_indexer_lib`, discarding responses from Byzantine validator nodes and querying honest members.
- Prevents cache poisoning and address spoofing for published WASM templates.
- Merged into `development` by the Tari team.
- This contribution is tracked by `tari-project/special_contributions#242`.
