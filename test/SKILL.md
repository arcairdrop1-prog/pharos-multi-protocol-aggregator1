Pharos Multi-Protocol Aggregator
Use this skill for supported Pharos vault positions, rate comparison, deposit routing and withdrawal routing.

Require chain 1672, an explicit account, and an explicit receiver and positive USDC amount for actions.
Query every configured adapter independently at a pinned block. Preserve per-venue failures.
Treat RockawayX and SharpByte as two Morpho vaults, not two independent protocols.
Do not interpret Morpho Vault V2 standard max* == 0 as zero capacity; disclose the documented limitation and validate the account-specific action.
Compare only the same USDC asset and fixed-share historical window. Never label it guaranteed APY or personal profit.
For deposits, read USDC balance and allowance. Add only a bounded approval to the selected vault when necessary.
For withdrawals, require a non-zero verified share position and sufficient converted exposure. Keep owner, caller and receiver explicit.
Decode prepared calldata and use read-only gas estimation. Approval-dependent actions remain CONDITIONAL.
Never sign, broadcast, create a wallet, request funding, or deploy a contract.
