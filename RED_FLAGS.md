# Red Flag Triggers

Any one of these, raised by any research agent, hard-caps the final asset score
at **3.0 / 10** regardless of the weighted average.

Agents read this file at runtime. Edit here to tune triggers without modifying
the skill itself.

## Triggers

### FLAG_BRIDGE_WEAK_DVN
**When:** LayerZero DVN configuration is ≤ 1/1, or CCIP is used without a
risk-management module, or any bridge exposes a single-sig admin role.
**Raised by:** cross-chain-surface

### FLAG_UNSAFE_PROXY_ADMIN
**When:** The upgrade proxy admin is an EOA, or a multisig with threshold < 3.
**Raised by:** governance-security

### FLAG_NO_TIMELOCK_ON_CRITICAL_OPS
**When:** Critical funds-moving operations (upgrade, pause, asset-withdrawal,
role grants for asset minting) can be executed with zero timelock delay.
**Raised by:** governance-security

### FLAG_UNSAFE_MINT_AUTHORITY
**When:** Infinite-mint or unbounded-mint capability is held by an EOA or a
multisig with threshold < 3/5.
**Raised by:** asset-controls

### FLAG_UNVERIFIED_CORE_CONTRACT
**When:** Any core contract (token, oracle, adapter, vault, router) is NOT
verified on the canonical block explorer for its chain.
**Raised by:** code-quality

### FLAG_RECENT_UNRECOVERED_EXPLOIT
**When:** The protocol itself OR a direct dependency had an exploit in the last
90 days that has not been fully remediated or recovered from.
**Raised by:** controversy

### FLAG_SUSPICIOUS_SAFE_MODULE
**When:** A high-security Safe multisig has a non-standard module enabled
(e.g., delay-modifier with short delay, unknown/custom module, Zodiac modules
with broad scope).
**Raised by:** governance-security

### FLAG_ANON_TEAM_WITH_PRIVILEGE
**When:** The team is fully anonymous AND holds a red-flag-eligible on-chain
role (multisig signer on a critical op, mint authority, timelock admin).
**Raised by:** team-transparency + asset-controls (coordinate via findings)
