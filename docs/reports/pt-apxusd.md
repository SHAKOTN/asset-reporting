---
title: PT-apxUSD
score: 3.0
verdict: "technically exists, regrettably"
redFlags: ['FLAG_NO_TIMELOCK_ON_CRITICAL_OPS', 'FLAG_NO_TIMELOCK_ON_CRITICAL_OPS', 'CODE_QUALITY_CONCERN', 'CODE_QUALITY_CONCERN', 'CODE_QUALITY_CONCERN', 'CODE_QUALITY_CONCERN', 'CODE_QUALITY_CONCERN', 'CONTROVERSY_CONCERN', 'CONTROVERSY_CONCERN', 'CONTROVERSY_CONCERN', 'CONTROVERSY_CONCERN', 'CONTROVERSY_CONCERN', 'CONTROVERSY_CONCERN', 'CONTROVERSY_CONCERN', 'CONTROVERSY_CONCERN']
date: 2026-04-21
---

<div class="score-banner">
  <div class="speedometer"><svg width="400" height="220" viewBox="0 0 400 220" xmlns="http://www.w3.org/2000/svg">
  <!-- arc background -->
  <path d="M 40 200 A 160 160 0 0 1 360 200" stroke="#ddd" stroke-width="20" fill="none"/>
  <!-- arc colored zones -->
  <path d="M 40 200 A 160 160 0 0 1 152 51" stroke="#d33" stroke-width="20" fill="none"/>
  <path d="M 152 51 A 160 160 0 0 1 248 51" stroke="#e80" stroke-width="20" fill="none"/>
  <path d="M 248 51 A 160 160 0 0 1 360 200" stroke="#3a3" stroke-width="20" fill="none"/>
  <!-- needle, rotates around center (200, 200) -->
  <line x1="200" y1="200" x2="200" y2="60"
        stroke="#111" stroke-width="4" stroke-linecap="round"
        transform="rotate(-36.0, 200, 200)"/>
  <circle cx="200" cy="200" r="8" fill="#111"/>
  <!-- score label -->
  <text x="200" y="190" text-anchor="middle" font-family="sans-serif" font-size="36" font-weight="bold" fill="#111">3.0</text>
</svg></div>
  <div class="meme"><img src="/assets/score-3.png" alt="score 3 meme"/></div>
</div>

<p class="verdict-tagline"><em>technically exists, regrettably</em></p>

## ⚠ Red flags raised

- **[FLAG_NO_TIMELOCK_ON_CRITICAL_OPS]** (governance-security) — AccessManager 0xe167330E2Eac88666de253e9607C6d9ae0cA2824.canCall(0xabdd8c8ee69e5f5180eb9352aeffc5ceead65e96, 0x2037a5Eb67aa9B2FBF50042B724D8c4dB80F23b4, 0x4f1ef286) returns (true, 0): the 4-of-6 ADMIN Safe can upgradeToAndCall the Apyx Capped CR feed (part of the Morpho oracle stack for PT-apxUSD) with ZERO timelock. Same result for the uncapped CR feed at 0x823210Eb6390B88e2b8ad7152DF5D8F30B8FD305.
- **[FLAG_NO_TIMELOCK_ON_CRITICAL_OPS]** (governance-security) — AccessManager.getTargetAdminDelay(0x2037a5Eb67aa9B2FBF50042B724D8c4dB80F23b4) = 0 and getTargetAdminDelay(0x823210Eb6390B88e2b8ad7152DF5D8F30B8FD305) = 0. No function-role mappings have ever been set on either CR feed so every selector defaults to role 0 (ADMIN) with 0-second execution delay. A malicious upgrade of the CR oracle can be executed in a single 4-of-6 Safe tx, with no advance-warning window for Fira's liquidator bot or users to unwind.
- **[CODE_QUALITY_CONCERN]** (code-quality) — Audit reports not committed to repo — /reports folder contains only .gitkeep, audit PDFs not publicly linked from GitHub. Findings/remediation status cannot be independently verified.
- **[CODE_QUALITY_CONCERN]** (code-quality) — No public bug bounty program found (no Immunefi, HackerOne, or security@ contact surfaced in docs or README).
- **[CODE_QUALITY_CONCERN]** (code-quality) — Solo-dominant contributor pattern — commits heavily concentrated on one dev (ddaws), self-merged to main, open issues=0 which suggests private issue tracking rather than community engagement. Copilot co-authored commits indicate AI-assisted rather than peer-reviewed dev flow.
- **[CODE_QUALITY_CONCERN]** (code-quality) — UUPS-upgradeable oracle proxy (ApyxRedemptionOracle, ApyxCollateralRatioOracle) last upgraded 29 days ago — admin upgrade keys held by AccessManager, centralization surface affecting Fira liquidations.
- **[CODE_QUALITY_CONCERN]** (code-quality) — Low repo visibility — apyx-labs/evm-contracts has 1 star, 2 forks, 264 commits; nobody from the broader security community has paid attention yet. Fresh, unproven codebase.
- **[CONTROVERSY_CONCERN]** (controversy) — Apyx protocol is <4 months old (evm-contracts repo created 2026-01-05, pushed 2026-03-27; points campaign launched 2026-02-27). Zero track record through a full market cycle. Listing as collateral against fixed-rate BT is premature.
- **[CONTROVERSY_CONCERN]** (controversy) — No public third-party smart contract audit found. Apyx docs reference an 'audits' section but no report from Sherlock / Spearbit / Cantina / OpenZeppelin / Trail of Bits surfaced in web search. Github repo has no LICENSE, 1 star, 1 open issue — essentially zero external scrutiny.
- **[CONTROVERSY_CONCERN]** (controversy) — STRUCTURAL TWIN OF COLLAPSED xUSD (Stream Finance, Nov 4 2025). Both are synthetic yield-backed stables pushed as Pendle PT / Morpho collateral via looped borrow strategies. Stream lost $93M to an 'external fund manager,' xUSD depegged 87-93%, cascaded to deUSD (-98%), ~$285M+ in bad debt across Morpho/Euler/Gearbox/Silo. Apyx occupies the same structural niche (offchain-backed, curator-allocated, looped on Morpho) — the market has already demonstrated this model is fragile.
- **[CONTROVERSY_CONCERN]** (controversy) — ACTIVE 2026 CONTAGION WINDOW. Kelp DAO $292M rsETH drain on 2026-04-19 (2 days ago) triggered $13B TVL wipeout across DeFi, AAVE lost $6-8B in 48h, Aave/Compound/Fluid/Spark/Euler froze rsETH markets. Broader DeFi is in an adverse liquidity regime RIGHT NOW. Onboarding a new, untested collateral asset during this window is poor timing.
- **[CONTROVERSY_CONCERN]** (controversy) — CR (collateralization ratio) oracle feed confirmed stale 25 days on 2026-04-16 per Fira's own due diligence. Apyx response 'updated as needed atm, will be daily in future' is NOT enforced on-chain. No heartbeat, no fallback oracle, no circuit breaker — direct depeg/insolvency attack surface.
- **[CONTROVERSY_CONCERN]** (controversy) — Backing assets (STRC, SATA) are variable-rate perpetual preferreds from leveraged BTC treasury companies (Strategy/MSTR, Strive/ASST). Reflexive death-spiral risk: BTC crash → STRC dividend rises → Strategy raises more debt / sells BTC → BTC falls more. Multiple commentators explicitly draw Terra-Luna parallels. Industry analysts warned in Q1 2026 of 'DAT shakeout' post-$19B Q4 2025 deleveraging event.
- **[CONTROVERSY_CONCERN]** (controversy) — DFDV (Apyx's primary sponsor/backer) is the former Janover Inc., which pivoted to Solana treasury in April 2025 after Blake Janover sold control for $4M. The company is <12 months into its crypto identity. Apyx's $300M valuation on a $3M raise is a signal of insider-network-driven pricing, not market-validated demand.
- **[CONTROVERSY_CONCERN]** (controversy) — Yield source is offchain dividend cash flow from publicly-traded preferred shares held at BitGo custody. Full counterparty chain: DAT issuer (pays dividend) -> custodian -> Apyx operator (keys) -> minter contract -> on-chain CR. Any single link failure freezes or mispriced apxUSD. Attestations are offchain, monthly (PCAOB), not real-time.

  Hard-caps final score at 3.0 (weighted would have been 5.1).

## Judge's verdict

The one genuine strength here is the human layer: team-transparency scored 8 on fully doxxed ex-Kraken leadership backed by DFDV (NASDAQ-listed), and the cross-chain surface is clean — Chainlink CCIP with RMN enabled, no LayerZero/Wormhole sprawl. That is as good as founder/bridge hygiene gets for a <3-month-old asset. But it is dwarfed by the governance finding: the Apyx Capped CR feed — which IS the Morpho oracle dependency PT-apxUSD would inherit — can be `upgradeToAndCall`'d in a single 4-of-6 Safe tx with `getTargetAdminDelay = 0` and no function-role mappings set. A malicious or coerced upgrade gives Fira liquidators zero warning window on the price of the collateral. That is a hard structural defect, not a config nit, and it is what anchors the red-flag cap to 3.0.

Second-order issues compound the governance defect rather than offset it. The CR feed is already stale 29.7 days with no heartbeat bot — the oracle isn't just centrally upgradeable, it's unmaintained. The 4/6 ADMIN and 3/6 MAINTAINER Safes share 5 of 6 owner keys, so "separation of duties" is cosmetic; the effective bar on every critical lever is 3 signatures. Pause is 3/6 with 0 delay, which is a direct DoS vector on Fira's liquidation flow. On the liquidity side, aggregators (Paraswap, Odos) don't route PT-apxUSD at all — liquidators must build a bespoke PT→SY→apxUSD→USDC path, and the Pendle AMM holds only 2.39M PT, so a $2M seizure is ~85% of AMM depth pre-expiry. Layer in the controversy surface — structural twin of the Stream/xUSD November 2025 collapse (Morpho-looped + Pendle-PT'd + $285M bad debt), active Kelp contagion window, reflexive STRC/SATA backing, insider-priced $300M valuation, and three tier-1 audits listed but no PDFs retrievable — and the "we're not Stream" thesis rests on trust rather than verifiable evidence.

For this to clear, at minimum: (1) Apyx binds a non-zero `adminDelay` (ideally 7d) on the CR feed `upgradeToAndCall` selector and makes it enforceable; (2) a heartbeat bot brings the CR feed within a bounded staleness window with monitoring; (3) the ADMIN Safe threshold rises and owner overlap with MAINTAINER drops below full quorum; (4) at least one of the three claimed audit PDFs becomes public for finding-level review. Absent those, even a tightly-capped fixed-rate market inherits an oracle that can be hot-swapped faster than Fira can react.

**Verdict:** hard no


## Per-criterion scores

| Criterion | Weight | Score | Confidence |
|---|---:|---:|---:|
| Governance & Security | 30% | 3.0 | 0.88 |
| Asset Controls | 25% | 6.0 | 0.85 |
| Cross-Chain Surface | 15% | 8.0 | 0.85 |
| Code Quality | 10% | 6.0 | 0.65 |
| Controversy | 10% | 3.0 | 0.75 |
| Team Transparency | 5% | 8.0 | 0.75 |
| Liquidity Depth | 5% | 5.0 | 0.85 |

## Detailed findings

### Governance & Security  (score 3, confidence 0.88)

- **[INFO]** Multisig & privileged role inventory (mandatory table)
  All role assignments and delays verified on-chain via AccessManager 0xe167330E2Eac88666de253e9607C6d9ae0cA2824 (hasRole, getAccess, getTargetFunctionRole, getTargetAdminDelay). Threshold/owners pulled directly from each Safe via getThreshold()/getOwners(). "Exec delay" is the per-member executionDelay from AccessManager.getAccess; "target admin delay" is the delay enforced on setTargetFunctionRole / setTargetAdminDelay against that target. For a scheduled-then-executed operation the effective wait is max(execDelay, targetAdminDelay).

```markdown
| Role | Address | Type | Threshold | Controls |
|------|---------|------|-----------|----------|
| ADMIN Safe (AccessManager role 0) | 0xabdd8c8ee69e5f5180eb9352aeffc5ceead65e96 | Gnosis Safe 4/6 | 4/6 (0 exec delay, 0 target admin delay on CR feeds, 3d on apxUSD) | AccessManager self-admin (grant/revoke any role, setTargetFunctionRole, setTargetAdminDelay); upgradeToAndCall on CR capped 0x2037a5Eb... and CR raw 0x8232... (INSTANT); mint(address,uint256) authority on apxUSD (selector 0x40c10f19 → role 0) |
| MAINTAINER-LONG Safe (role 2 + 21 + 22 + 23 + 24 + 25) | 0xf9862efc1704ac05e687f66e5cd8c130e5663ce2 | Gnosis Safe 3/6 | 3/6 | role 2 general maintainer ops; role 21 MAINTAINER_INSTANT (0 delay) → apxUSD pause() 0x8456cb59; role 22 MAINTAINER_SHORT (14400s=4h) → apxUSD unpause() 0x3f4ba83a; role 23 MAINTAINER_MEDIUM (86400s=1d); role 24 MAINTAINER_LONG (259200s=3d) → apxUSD upgradeToAndCall 0x4f1ef286; role 25 MAINTAINER_MAXIMUM (604800s=7d) |
| GUARDIAN role 31 holders | 7 EOAs incl. 0xb51F89DEA7Df709cEbb4809B40c6431361e61d0d, 0xcFCF3C9Ed3d97DB54c99BDd197E59952a0973f6e, 0xB98cD8C868cf00cEA934977dBE4AC090E808fb87, 0x5db416BcFc1a8b5b921f55C1E078d1F39194e99F, 0xd66a0Fc924fAb7476D35aFe5941856ef76BA0839, 0xD6bB3f9718D4f30ed2851c713275dEf7529D1411, plus 1 additional granted in tx block 0x17b182f | AccessManager role 31 members (EOAs) | 1-of-any (each EOA acts independently) | cancel() scheduled operations of supervised roles via AccessManager; roleGrantDelay=0 → ADMIN can add new guardians instantly |
| apxUSD proxy admin authority | 0xe167330E2Eac88666de253e9607C6d9ae0cA2824 (AccessManager itself) | AccessManager (OZ AccessManagedUpgradeable) | Target admin delay = 259200s (3d) | Acts as proxyAdmin for UUPS proxy 0x98A878b1Cd98131B271883B390f68D2c90674665; upgradeToAndCall routed to role 24 (MAINTAINER_LONG = 0xf986...) |
| CR capped feed authority | 0xe167330E2Eac88666de253e9607C6d9ae0cA2824 | AccessManager | Target admin delay = 0 (INSTANT) | UUPS proxy 0x2037a5Eb67aa9B2FBF50042B724D8c4dB80F23b4 (Morpho PT-apxUSD oracle BASE_FEED_2); all selectors default to ADMIN role 0 → 4/6 Safe can swap impl in one tx |
| CR raw feed authority | 0xe167330E2Eac88666de253e9607C6d9ae0cA2824 | AccessManager | Target admin delay = 0 (INSTANT) | UUPS proxy 0x823210Eb6390B88e2b8ad7152DF5D8F30B8FD305 (source for capped feed); same 4/6 instant-upgrade surface |
| apxUSD mint controller (role 0 default) | 0xabdd8c8ee69e5f5180eb9352aeffc5ceead65e96 | Gnosis Safe 4/6 (via AccessManager role 0, no custom role assigned) | 4/6 (0 exec delay) | mint(address,uint256) on apxUSD falls through to default role 0 since no ROLE_MINT_STRAT (role 1) has been assigned on this selector — verified via getTargetFunctionRole = 0. Effective mint cap = unlimited |
| Role 1 ROLE_MINT_STRAT holders | NONE granted on-chain | AccessManager role 1 | n/a | Despite RoleLabel event, no addresses hold role 1; mint selector therefore falls through to role 0 ADMIN. Documentation drift from docs.apyx.fi |
| Role 8 ROLE_REDEEMER holders | Not held by either Safe per hasRole probe | AccessManager role 8 | n/a | Redemption gating — not exercised in current deployment |
| Safe Modules on ADMIN + MAINTAINER | None (getModulesPaginated = []) | — | — | No Zodiac / Roles Modifier / Delay module. No module attack surface, but also no automated policy enforcement |
| Safe Guards on ADMIN + MAINTAINER | None (guard storage slot = 0x00) | — | — | No transaction-level guard; no pre/post-exec hooks |
| apxUSD implementation | 0xDd71Fd677fde2ed2579a3c45204f41a11016ccB4 | Logic contract (non-proxy) | n/a | Runtime bytecode executed by proxy 0x98A8...; swappable by role 24 with 3d delay |
| CCIP admin | Not applicable | — | — | apxUSD has no CCIPAdmin / TokenAdminRegistry binding on mainnet as of 2026-04-21 |
```

Effective-control summary: an attacker with 4 of 6 ADMIN signers can (a) instantly upgrade either CR feed implementation, (b) mint unlimited apxUSD, (c) reconfigure AccessManager itself (self-admin delay 0). An attacker with 3 of 6 MAINTAINER signers can (a) pause apxUSD instantly (denial-of-service to Fira liquidators), (b) schedule apxUSD upgrade with 3-day warning, (c) unpause with 4h delay. The two Safes share 5 of 6 owners (0xb51F, 0xD6bB, 0xcFCF, 0xB98c, 0x5db4, 0xd66a overlap; maintainer differs only in the 0x0442... addition visible in role 31 grants), so "separation of duties" is nominal.

  *Evidence:* AccessManager 0xe167330E2Eac88666de253e9607C6d9ae0cA2824 — hasRole/getAccess/getTargetFunctionRole/getTargetAdminDelay; Safe 0xabdd8c8ee69e5f5180eb9352aeffc5ceead65e96 getThreshold=4, getOwners=[0xb51F...,0xD6bB...,0xcFCF...,0xB98c...,0x5db4...,0xd66a...]; Safe 0xf9862efc1704ac05e687f66e5cd8c130e5663ce2 getThreshold=3, getOwners overlap 5/6; apxUSD proxy 0x98A878b1Cd98131B271883B390f68D2c90674665 impl=0xDd71Fd67...; CR capped 0x2037a5Eb..., CR raw 0x8232... both AccessManaged
- **[CRITICAL]** 4-of-6 ADMIN Safe can swap CR oracle implementation instantly (no timelock)
  The Apyx Capped Collateralization Ratio feed (0x2037a5Eb67aa9B2FBF50042B724D8c4dB80F23b4) and the uncapped CR feed (0x823210Eb6390B88e2b8ad7152DF5D8F30B8FD305) are UUPS proxies authorized to AccessManager 0xe167330E2Eac88666de253e9607C6d9ae0cA2824. Both targets have getTargetAdminDelay = 0, and no function roles have ever been assigned on either target (0 TargetFunctionRoleUpdated events), so every selector is gated by the default ADMIN_ROLE (role 0) with 0-second execution delay. ADMIN_ROLE is held exclusively by the 4-of-6 Safe 0xabdd8c8ee69e5f5180eb9352aeffc5ceead65e96 (verified: AccessManager.hasRole(0, 0xabdd...) = (true, 0)). The same Safe can therefore upgradeToAndCall either CR feed in a single tx with no advance-warning delay. Because the Morpho market oracle (0x4DFceF82eaEE9eA817bEb1279336F7D0Ebf2b685) uses the capped CR feed as BASE_FEED_2 — and any Fira PT-apxUSD oracle that wraps the same Pendle/Chainlink adapter will inherit the same dependency — a hostile 4-of-6 quorum can instantaneously inflate or zero the apxUSD price, triggering either mass liquidation or unliquidatable bad debt in the Fira market before the Hexagate monitor or liquidator bot can react.
  *Evidence:* cast call 0xe167330E2Eac88666de253e9607C6d9ae0cA2824 'canCall(address,address,bytes4)' 0xabdd... 0x2037a5Eb... 0x4f1ef286 -> (true, 0); eth_getLogs topic0=0x9ea6790c... target=0x2037a5Eb... returns []
- **[CRITICAL]** CR oracle feed stale ~30 days — no heartbeat, no operator role
  latestRoundData().updatedAt = 1774192391 on both CR1 and CR2. Current block timestamp 1776757235 → 2,564,844 s = 29.7 days stale. eth_getLogs shows only 3 events total on CR1 (one init + effectively zero subsequent AnswerUpdated) and 4 events on CR2. No dedicated oracle-operator role has ever been bound to an updater selector (TargetFunctionRoleUpdated count = 0 for both targets), meaning the 4-of-6 ADMIN is the only entity with write authority. The feed therefore does not have a functioning heartbeat bot. For Fira this is a second-order hazard: (a) if the underlying basket re-values upward, the stale CR feed fails to propagate the gain and borrowers can be over-liquidated at liquidation events against an out-of-date denominator; (b) the staleness prevents downstream consumers (Chainlink wrappers, Aave/Morpho adapters) from enforcing staleness reverts unless explicitly guarded. Matches Fira-side due diligence dated 2026-04-16 which observed the same CR feed was 25 days stale at the time.
  *Evidence:* cast call 0x2037a5Eb67aa9B2FBF50042B724D8c4dB80F23b4 'latestRoundData()' -> (1, 1e8, 1774192391, 1774192391, 1). Current latest block timestamp 1776757235.
- **[HIGH]** ADMIN Safe is only 4-of-6; threshold too low for unilateral oracle/upgrade authority
  ADMIN_ROLE is held by 4-of-6 Safe 0xabdd8c8ee69e5f5180eb9352aeffc5ceead65e96 (getThreshold() = 4, getOwners() returns 6 EOAs). Given this Safe has both (i) zero-delay upgrade power over both CR oracle feeds and (ii) zero-delay authority to reconfigure AccessManager itself (getTargetAdminDelay for the AccessManager target is 0 and role 0 admin = role 0), the effective trust assumption is that any 4-of-6 signers cannot be compromised or collude. Fira's internal policy requires 5/9+ on fund-critical surfaces; 4/6 falls below that bar. There is also no Safe Guard (storage slot 0x4a204f62... is 0x00) and no Safe modules (getModulesPaginated returns empty), so no secondary override or monitoring hook is in place.
  *Evidence:* cast call 0xabdd8c8ee69e5f5180eb9352aeffc5ceead65e96 'getThreshold()' -> 4; 'getOwners()' -> [0xb51F..., 0xD6bB..., 0xcFCF..., 0xB98c..., 0x5db4..., 0xd66a...]; 'getModulesPaginated(0x1,100)' -> ([], 0x1); eth_getStorageAt guard slot -> 0x00
- **[HIGH]** No effective separation of duties between ADMIN and MAINTAINER Safes
  The ADMIN Safe (0xabdd..., 4-of-6) and the MAINTAINER-LONG Safe (0xf9862efc1704ac05e687f66e5cd8c130e5663ce2, 3-of-6) share 5 of 6 signers. The Apyx blog claims configuration authority is/will be transferred to 'a separate master multi-sig' so that operators and governors are distinct, but that claim is not reflected on-chain: the two Safes are effectively the same key-holder set with different thresholds. A single set of 4 compromised signers (or 3 for the MAINTAINER path) can reach either Safe; true separation of duties requires non-overlapping owner sets, which does not exist here.
  *Evidence:* getOwners() returns identical 5-address overlap between 0xabdd... and 0xf9862efc1704ac05e687f66e5cd8c130e5663ce2 (owners 0xb51F..., 0xcFCF..., 0xB98c..., 0x5db4..., 0xd66a... appear in both). blog.apyx.fi/minting-controls/ claims an upcoming split.
- **[MEDIUM]** apxUSD upgradeToAndCall gated by only 3-of-6 + 3 day exec delay
  apxUSD (proxy 0x98A878b1Cd98131B271883B390f68D2c90674665) is a UUPS proxy (EIP-1967 impl = 0xDd71Fd677fde2ed2579a3c45204f41a11016ccB4). Function role for upgradeToAndCall(0x4f1ef286) is role 24 (ROLE_MAINTAINER_LONG) — held by 3-of-6 Safe 0xf986... with an executionDelay of 259,200 s (3 days). Target admin delay on apxUSD is also 3 days. So the fastest path to ship a malicious apxUSD implementation requires (3-of-6 quorum) + (3-day schedule → execute window). 3 days is on the short side of acceptable for an upgradeable stablecoin; Fira liquidators must be able to detect OperationScheduled events on the AccessManager and unwind before execution.
  *Evidence:* cast call AM 'canCall(0xf986..., 0x98A878..., 0x4f1ef286)' -> (false, 259200); cast call AM 'getTargetAdminDelay(0x98A878...)' -> 259200; cast call AM 'getTargetFunctionRole(0x98A878..., 0x4f1ef286)' -> 24
- **[MEDIUM]** Role 31 (GUARDIAN) grantDelay is 0 with 7 EOA members
  Role 31 (relabeled DELEGATE_OPERATOR/GUARDIAN) has getRoleGrantDelay = 0 and 7 members, including multiple EOA addresses matching ADMIN Safe owners. GUARDIAN can cancel scheduled operations of supervised roles (including role 24 upgrader); conversely, ADMIN can add/remove guardians instantly. The guardian set is therefore co-extensive with the ADMIN Safe owners, providing no independent stop.
  *Evidence:* cast call AM 'getRoleGrantDelay(31)' -> 0; RoleGranted events show 7 distinct addresses granted role 31 in blocks 0x17a780b and 0x17b182f
- **[MEDIUM]** apxUSD pause() is instant-role (0 delay, 3-of-6 quorum)
  Function role for pause()(0x8456cb59) on apxUSD is role 21 (ROLE_MAINTAINER_INSTANT), held by 0xf986... 3-of-6 with 0 execution delay. Good from an emergency-response perspective, but introduces a censorship/DoS vector: any 3 of 6 signers can freeze apxUSD redemptions, which would break the Fira liquidation flow (liquidators need to convert seized apxUSD back to USDC) and could leave borrowers unable to repay close to maturity. pause() shares the instant-action property with unpause() (role 22, 4h delay) and the guardian cancel flow (role 31, 0 delay).
  *Evidence:* cast call AM 'getTargetFunctionRole(0x98A878..., 0x8456cb59)' -> 21; RoleGranted events bind 0xf986... to roles 21,22,23,24,25
- **[MEDIUM]** AccessManager self-admin delay = 0
  getTargetAdminDelay(AccessManager) = 0. Combined with role 0 being its own admin (getRoleAdmin(0) = 0), ADMIN can reconfigure the manager itself without a delay — including adding new ADMIN members (subject to 7-day roleGrantDelay), adjusting target delays (subject to minSetback=5d only when *reducing* an existing non-zero delay), or rerouting function→role mappings on targets with 0 target-admin delay (i.e. both CR feeds). The only hard backstop is the 7-day grant delay for role 0 itself; any mis-configuration that forgot to put a delay in place (as with the CR feeds) is exploitable in a single tx.
  *Evidence:* cast call AM 'getTargetAdminDelay(AM)' -> 0; 'getRoleAdmin(0)' -> 0; 'minSetback()' -> 432000; 'getRoleGrantDelay(0)' -> 604800
- **[LOW]** No Safe Modules and no Safe Guards (positive) but also no MEV-aware execution delay
  Both admin Safes (0xabdd..., 0xf986...) return empty module lists from getModulesPaginated and zero in the guard storage slot (0x4a204f62...). No suspicious module surface. Positive signal, but also means there is no automated policy enforcement layer; any valid N-of-M execution goes through unconditionally.
  *Evidence:* getModulesPaginated(0x1,100) on both Safes returns ([], 0x1); eth_getStorageAt guard slot on both returns 0x00
- **[INFO]** Role labels and delay posture (reference)
  Enumerated roles via RoleLabel events: 0=ADMIN, 1=ROLE_MINT_STRAT, 2=MINTER_CONTRACT_4HR, 3=ROLE_MINT_GUARD, 4=MINTER_CONTRACT_4HR (rebinding), 6=ROLE_YIELD_DISTRIBUTOR, 7=YIELD_OPERATOR, 8=ROLE_REDEEMER, 21=MAINTAINER_INSTANT, 22=MAINTAINER_SHORT, 23=MAINTAINER_MEDIUM, 24=MAINTAINER_LONG, 25=MAINTAINER_MAXIMUM, 31=GUARDIAN. Grant delays: role 0 = 7d, roles 1/2/4/8 = 3d, roles 6/7 = 1d, roles 21-25 = 7d, role 31 = 0. apxUSD target admin delay = 3d. CR feeds target admin delay = 0d. AccessManager self delay = 0d. minSetback = 5d.
  *Evidence:* RoleLabel events on AccessManager; getRoleGrantDelay and getTargetAdminDelay calls per row
- **[INFO]** Docs -> on-chain drift on 'separate master multisig'
  Apyx blog post 'Minting Controls' (blog.apyx.fi/minting-controls/) claims configuration authority will be transferred to a 'separate master multi-sig', distinct from the minting multisig. On-chain the two admin Safes 0xabdd... (4-of-6, ADMIN) and 0xf986... (3-of-6, MAINTAINER+GUARDIAN) share 5 of 6 owners, so the separation is nominal at best. The public docs (docs.apyx.fi) do not disclose specific multisig addresses, thresholds, or timelock durations, making independent verification dependent on on-chain archaeology.
  *Evidence:* blog.apyx.fi/minting-controls/; getOwners() on both Safes; docs.apyx.fi has no explicit governance addresses

### Asset Controls  (score 6, confidence 0.85)

- **[INFO]** AccessManager ADMIN_ROLE (role 0) currently held by 4-of-6 Safe, not an EOA
  Verified live via hasRole(0, 0xabdd8c8ee69e5f5180eb9352aeffc5ceead65e96) => (true, 0). The Safe at 0xabdd8c8ee69e5f5180eb9352aeffc5ceead65e96 has threshold 4 and 6 signers (verified via getThreshold()/getOwners()). ADMIN was transferred from the genesis deployer EOA 0x0442cC5BBfBc4B7Dc3A14F9766c21C82b45f0024 (confirmed hasRole(0, EOA) => (false, 0)) and also from the 3/6 ops Safe 0xf9862EfC1704aC05e687f66E5cD8c130E5663cE2 (confirmed hasRole(0, f9862) => (false, 0)). Admin ownership move to the 4/6 Safe occurred at block 24721241 (timestamp 1772908091 ~ 2026-03-04). ADMIN has 0 execution delay but role 0 grant delay is 7 days, so adding a new admin takes 7 days.
  *Evidence:* AccessManager 0xe167330E2Eac88666de253e9607C6d9ae0cA2824 | Safe 0xabdd8c8ee69e5f5180eb9352aeffc5ceead65e96 (4/6) | grant tx 0x8b6b1a3a2e7900bd0b5f1d49a1d6fe840cedb4b2af26da7147eb52ca3e5af417 block 24721241
- **[MEDIUM]** apxUSD.mint gated by MinterV0 contract (role 4) with 10M/day rate limit, 4h exec delay, and signed orders
  apxUSD.mint(address,uint256,uint256) selector 0x156e29f6 is gated by role 4 (verified via raw call getTargetFunctionRole @ 0x6d5115bd). Role 4 is held solely by the MinterV0 mint-strategy contract at 0x2c36e1adFaA80ee0324B04cC814F5207Bb7Ba76e with a 14400s (4h) execution delay. Role 4 grant delay is 259200s (3 days). MinterV0 enforces: max 10,000,000 apxUSD per tx, rate limit 10,000,000 apxUSD per 86,400s (1 day), supply cap 300,000,000 apxUSD (live read supplyCap() = 3e26). Current totalSupply() = 1.8e26 (~180M). MinterV0 requires EIP-712 signed orders; requestMint (selector 0xeecd570d) and executeMint (0x14d39415) on MinterV0 are gated by role 2 (MINTER_CONTRACT), held by the 3-of-6 Safe 0xf9862EfC1704aC05e687f66E5cD8c130E5663cE2 with 0 exec delay. Effective minting bar: 3 of 6 Safe signers sign an EIP-712 order -> MinterV0 validates + enforces 10M/day + 10M/tx + cap -> tokens minted after 4h role-4 execution delay. Layered and capped, but the human bar is 3/6 (50%) which is at the low end for a dollar-stable with $180M live supply.
  *Evidence:* MinterV0 0x2c36e1adFaA80ee0324B04cC814F5207Bb7Ba76e (Etherscan verified 'MinterV0') | role 4 RoleGranted tx 0x75e353f8a1e894fbfc2cd4361f1e16997c48c3f3810b48b51410030308f4f5b5 block 24849935 (delay 14400) | role 2 RoleGranted tx 0x00f7dd292e9b611709879d357bceabede5c1bed180431911520eea47d508f185 block 24734715 (delay 0) | supplyCap() = 3e26, totalSupply() = 1.8e26
- **[MEDIUM]** UUPS upgradeToAndCall held by 3-of-6 Safe with only 3-day delay
  apxUSD is a UUPS upgradeable proxy. Selector 0x4f1ef286 (upgradeToAndCall(address,bytes)) is gated by role 24, held by Safe 0xf9862EfC1704aC05e687f66E5cD8c130E5663cE2 (3/6) with 259200s (3 day) execution delay. A 3/6 Safe (50% of signers) can push any new implementation after a 3-day wait, effectively bypassing mint caps, rate limits, deny list, or pause state. 3 days is the industry floor for defensible upgrade delay and the signer bar (3/6 = 50%) is below the typical 4/7 (57%) bar for a stablecoin with $180M live supply. ADMIN (4/6 Safe) can at any moment (0 delay) revoke or re-assign role 24, but an already-scheduled upgrade would still execute per OZ AccessManager semantics unless explicitly canceled.
  *Evidence:* TargetFunctionRoleUpdated(target=apxUSD, selector=0x4f1ef286, role=24) tx 0x79ff2a3aaf7c1eba6a18eb96b0aa2d3aed541a4cd408704bdd2c951e3560db02 block 24828844 logIndex 242 | RoleGranted(24, 0xf9862..., delay=0x3f480=259200) tx 0x01ff58d25be1119379d42ebc2d72e1039e4d374d7ad3ee823340589afbf31990 block 24792767
- **[MEDIUM]** DenyList (blacklist) and supplyCap gated by 3-of-6 Safe with 1-day delay
  setDenyList(address) selector 0x0de2731d and setSupplyCap(uint256) selector 0xb6a3f59a are both gated by role 23, held by Safe 0xf9862EfC1704aC05e687f66E5cD8c130E5663cE2 (3/6) with 86400s (1 day) execution delay. apxUSD IS a blacklist token: individual addresses can be denied sends/receives. For Fira as a collateral holder this matters indirectly — the vault/market could in principle be placed on the deny list, blocking apxUSD flows. 3/6 + 1-day is weak for blacklist power: 3 colluding signers can blacklist the Fira market or LPs with 24h notice. supplyCap increase is similarly gated (could raise from 300M to unlimited with 24h notice, though MinterV0's 10M/day drip still caps velocity). Fira holds PT-apxUSD not apxUSD at rest, so direct exposure is limited, but the Apyx CR feed path and Pendle TWAP both rely on an un-censored apxUSD spot market.
  *Evidence:* TargetFunctionRoleUpdated logIndex 240 (setSupplyCap -> role 0x17=23) and logIndex 241 (setDenyList -> role 0x17=23) tx 0x79ff2a3aaf7c1eba6a18eb96b0aa2d3aed541a4cd408704bdd2c951e3560db02 block 24828844 | RoleGranted(23, 0xf9862, delay=0x15180=86400) tx 0x01ff58d25be1119379d42ebc2d72e1039e4d374d7ad3ee823340589afbf31990 block 24792767
- **[LOW]** Pause held by 3-of-6 Safe with ZERO execution delay; unpause 4h delay
  pause() selector 0x8456cb59 is gated by role 21, held by Safe 0xf9862... (3/6) with 0 execution delay — 3 signers can freeze all apxUSD transfers immediately. unpause() selector 0x3f4ba83a is gated by role 22 (same 3/6 Safe) with 14400s (4h) execution delay. During a paused window, any Fira flow requiring apxUSD movement reverts. Fira does not hold apxUSD directly (holds PT-apxUSD) but arbitrage and Pendle TWAP updates depend on apxUSD being transferable. Pause-with-no-delay is standard for stablecoin incident response but also provides a censorship vector.
  *Evidence:* TargetFunctionRoleUpdated(apxUSD, 0x8456cb59, 21) block 24828844 logIndex 238 | TargetFunctionRoleUpdated(apxUSD, 0x3f4ba83a, 22) logIndex 239 | RoleGranted(21, 0xf9862, delay=0) and RoleGranted(22, 0xf9862, delay=14400) tx 0x01ff58d25be1119379d42ebc2d72e1039e4d374d7ad3ee823340589afbf31990
- **[LOW]** setCCIPAdmin and setAuthority gated by 3-of-6 Safe with 7-day delay
  setCCIPAdmin(address) selector 0xa8fa343c and setAuthority(address) selector 0x7a9e5e4b are both gated by role 25, held by Safe 0xf9862... (3/6) with 604800s (7 day) execution delay. setAuthority is the most sensitive function — it can replace the entire AccessManager; 7-day delay is appropriate. setCCIPAdmin controls the CCIP token admin (Chainlink cross-chain adapter) — 7-day delay also reasonable. Signer threshold is still 3/6 across all operational roles.
  *Evidence:* TargetFunctionRoleUpdated(apxUSD, 0xa8fa343c, 25) and (apxUSD, 0x7a9e5e4b, 25) block 24828844 logIndex 243/244 | RoleGranted(25, 0xf9862, delay=604800) block 24792767
- **[INFO]** Role taxonomy: labeled vs unlabeled roles
  AccessManager RoleLabel events emitted at deployment (block 24481041-24481052) cover: role 1=ROLE_MINT_STRAT, role 2=ROLE_MINTER (MINTER_CONTRACT), role 3=ROLE_MINT_GUARD, role 6=ROLE_YIELD_DISTRIBUTOR, role 7=ROLE_YIELD_OPERATOR, role 8=ROLE_REDEEMER. Roles 4, 21-25 that currently gate apxUSD's critical functions were NOT emitted with RoleLabel events — they were introduced in later setTargetFunctionRole batches (block 24734715 for MinterV0 wiring, 24828844 for apxUSD ops, 24849935 for the mint-role swap from role 1 to role 4). Unlabeled roles are a documentation gap: UIs, monitoring, and third-party risk systems that rely on role labels will miss the real gating. Role 31 was also assigned to MinterV0.cancelMint in a later batch.
  *Evidence:* RoleLabel events (topic 0x1256f5b5ecb89caec12db449738f2fbcd1ba5806cf38f35413f4e5c15bf6a450) block 24481041-24481052 on AccessManager 0xe167330E2Eac88666de253e9607C6d9ae0cA2824
- **[INFO]** Both Safes share the same 6 owner keys — effective bar is 3-of-6 for all ops
  The 4/6 ADMIN Safe 0xabdd8c8ee69e5f5180eb9352aeffc5ceead65e96 and the 3/6 ops Safe 0xf9862EfC1704aC05e687f66E5cD8c130E5663cE2 share IDENTICAL owner sets: [0xb51F89DEA7Df709cEbb4809B40c6431361e61d0d, 0x5db416BcFc1a8b5b921f55C1E078d1F39194e99F, 0xD6bB3f9718D4f30ed2851c713275dEf7529D1411, 0xcFCF3C9Ed3d97DB54c99BDd197E59952a0973f6e, 0xB98cD8C868cf00cEA934977dBE4AC090E808fb87, 0xd66a0Fc924fAb7476D35aFe5941856ef76BA0839]. Effective governance redundancy is the LOWER threshold (3/6), not the higher one — 3 colluding keys can: (a) trigger mints via MinterV0 (subject to 10M/day cap), (b) pause immediately, (c) deny-list or raise supplyCap with 1-day notice, (d) push an upgrade in 3 days. The 4/6 ADMIN only controls role management (grant/revoke/target wiring). Key-concentration risk: compromise of 3 of these 6 keys (phishing, device compromise, coercion) enables malicious upgrade in 3 days.
  *Evidence:* getOwners() on 0xabdd... and 0xf9862... both return same 6-address array | getThreshold() returns 4 and 3 respectively
- **[INFO]** Fira exposure is indirect — PT-apxUSD not apxUSD
  Fira's collateral is PT-apxUSD (Pendle Principal Token expiring 2026-06-18), not apxUSD at rest. PT redeems 1:1 to apxUSD at expiry. Mint authority + pause/deny list primarily affect apxUSD holders (Fira does not hold apxUSD directly). Two indirect exposures: (1) the Apyx CR capped feed 0x2037a5eb67aa9b2fbf50042b724d8c4db80f23b4 feeds the Morpho oracle 0x4DFceF82eaEE9eA817bEb1279336F7D0Ebf2b685 that drives Fira liquidations — its authority is the same AccessManager 0xe167330E2Eac88666de253e9607C6d9ae0cA2824, so the 3/6 Safe's upgrade path also threatens the CR feed (needs a separate verification of which role gates the CR feed's upgrade, not covered in this pass); (2) Pendle TWAP oracle depends on PT trading, which depends on apxUSD being usable. Fira should treat the 3/6-Safe upgrade path as the dominant governance risk vector, not the mint cap (which is reasonably constrained by MinterV0 + 10M/day + 4h exec delay + 300M hard cap).
  *Evidence:* docs/research/pt-apxusd-market.md | Morpho oracle 0x4DFceF82eaEE9eA817bEb1279336F7D0Ebf2b685 | Apyx CR capped feed 0x2037a5eb67aa9b2fbf50042b724d8c4db80f23b4 (authority 0xe167330E2Eac88666de253e9607C6d9ae0cA2824)

### Code Quality  (score 6, confidence 0.65)

- **[INFO]** ETHERSCAN VERIFICATION: All 5 core Apyx contracts verified with Exact Match status…
  ETHERSCAN VERIFICATION: All 5 core Apyx contracts verified with Exact Match status. apxUSD (0x98A8...4665), CR capped proxy (0x2037...f23b4, ERC1967Proxy) + impl (0xbcc4...d682, ApyxRedemptionOracle), CR raw proxy (0x8232...FD305, ERC1967Proxy) + impl (0x0e1e...c49c, ApyxCollateralRatioOracle), AccessManager (0xe167...2824). All compiled with Solc v0.8.30, optimizer enabled 200 runs, Prague EVM. No FLAG_UNVERIFIED_CORE_CONTRACT.
- **[INFO]** AUDIT HISTORY: Three audits at docs…
  AUDIT HISTORY: Three audits at docs.apyx.fi/resources/audits — Quantstamp (Feb 2026), Certora (Mar 2026), Zellic (Mar 2026). All top-tier firms (Quantstamp = YC-backed established, Certora = formal verification gold standard, Zellic = respected post-Trail-of-Bits). However, individual audit report PDFs were not retrievable for finding-by-finding review — severity distribution and remediation status UNVERIFIED from public sources.
- **[INFO]** REPO HEALTH: apyx-labs/evm-contracts actively maintained…
  REPO HEALTH: apyx-labs/evm-contracts actively maintained. 264 total commits, recent activity through Mar 27, 2026 (last 30 days: 30+ commits). Foundry + Soldeer tooling. 2 named contributors (ddaws dominant, apyx-rook minor). 1 open PR, 0 open issues.
- **[INFO]** CI PIPELINE: Multiple GitHub Actions workflows — forge…
  CI PIPELINE: Multiple GitHub Actions workflows — forge.yml (tests), Slither static analysis, NatSpec docs deployment, commit email validation, Copilot review. 318 total workflow runs, latest green (38s). Security-tooling hygiene above average.
- **[INFO]** TEST STRUCTURE: test/ directory contains contracts/, deploy/, exts/, invariant/, mocks/, u…
  TEST STRUCTURE: test/ directory contains contracts/, deploy/, exts/, invariant/, mocks/, utils/, views/ subdirectories plus BaseTest.sol. Dedicated invariant/ folder = invariant testing present. foundry.toml sets invariant runs=256, depth=1024 (reasonable). Fuzz runs not specified (uses Foundry default 256).
- **[INFO]** CORE CONTRACTS: src/ contains ApxUSD…
  CORE CONTRACTS: src/ contains ApxUSD.sol, ApyUSD.sol, CommitToken.sol, MinterV0.sol, UnlockToken.sol, LinearVestV0.sol, RedemptionPoolV0.sol, YieldDistributor.sol plus curve/, oracles/, orders/, interfaces/, deploy/, exts/, errors/, views/ subfolders. Roles.sol + AddressList.sol for access control. ApyxRedemptionOracle implements Chainlink AggregatorV3Interface (good — Fira can consume directly).
- **[INFO]** ARCHITECTURE: Oracle contracts use UUPS upgradeable pattern + OpenZeppelin AccessManaged +…
  ARCHITECTURE: Oracle contracts use UUPS upgradeable pattern + OpenZeppelin AccessManaged + Pausable. OpenZeppelin Contracts v5.5.0 (current). Standard, modern patterns — not rolled-from-scratch.
- **[INFO]** NO KNOWN INCIDENTS: Search of Immunefi, Rekt News, GitHub Security Advisories returned no …
  NO KNOWN INCIDENTS: Search of Immunefi, Rekt News, GitHub Security Advisories returned no exploits or incidents for Apyx. However, protocol is very young (<3 months public per CR proxy creation date) — not yet battle-tested. DefiLlama tracks apxUSD as live stablecoin.
- **[INFO]** PENDLE PT LAYER: PT-apxUSD, SY, YT, and Market contracts are standard Pendle V2 deployment…
  PENDLE PT LAYER: PT-apxUSD, SY, YT, and Market contracts are standard Pendle V2 deployments (reused battle-tested code audited by Spearbit/Code4rena/etc.). Risk concentrates on apxUSD collateral layer, not PT wrapper.
- **[INFO]** SCORE JUSTIFICATION: Three audits from solid firms (+) verified contracts (+) active CI wi…
  SCORE JUSTIFICATION: Three audits from solid firms (+) verified contracts (+) active CI with Slither (+) invariant tests (+) modern OZ v5 patterns (+) BUT no retrievable audit finding details (-) empty on-repo audit folder (-) solo-dev concentration (-) no bug bounty (-) young protocol without production track record (-) upgradeable centralization. Net score 6/10 — solid engineering hygiene but lacks public transparency. Not 7-8 because audit findings/remediations not publicly verifiable; not 3-4 because tooling + verified contracts + top audit firms are real.

### Cross-Chain Surface  (score 8, confidence 0.85)

- **[INFO]** apxUSD underlying token (0x98a878b1cd98131b271883b390f68d2c90674665 on Ethereum) is curren…
  apxUSD underlying token (0x98a878b1cd98131b271883b390f68d2c90674665 on Ethereum) is currently live on 2 EVM chains: Ethereum mainnet and Base.
- **[INFO]** PT-apxUSD itself (0x92a6a01b07984de46c24e8eba248449beb8b1dcb) is a Pendle PT and lives on …
  PT-apxUSD itself (0x92a6a01b07984de46c24e8eba248449beb8b1dcb) is a Pendle PT and lives on Ethereum only. SY-apxUSD wrapper: 0x4f116eE5BCD227d1a1C4f57918D694a4aBe7b3FC. Underlying yield token: 0x98A878b1Cd98131B271883B390f68D2c90674665.
- **[INFO]** Cross-chain bridging is done via Chainlink CCIP (not LayerZero, Wormhole, or a custom brid…
  Cross-chain bridging is done via Chainlink CCIP (not LayerZero, Wormhole, or a custom bridge). Apyx announced Base expansion via CCIP in official blog post (blog.apyx.fi/apyx-expands-to-base-with-chainlink-powered-cross-chain-support-2).
- **[INFO]** CCIP has RMN (Risk Management Network) enabled by default on all lanes — RMN is a secondar…
  CCIP has RMN (Risk Management Network) enabled by default on all lanes — RMN is a secondary independent DON that vigilantly monitors and can veto the primary Committing DON. This is the strongest bridge-layer defense available in the CCIP design.
- **[INFO]** No LayerZero OFT deployment, no custom multisig-admin bridge, no Wormhole, no Axelar — onl…
  No LayerZero OFT deployment, no custom multisig-admin bridge, no Wormhole, no Axelar — only CCIP with RMN.
- **[INFO]** Solana expansion publicly announced as 'coming soon' (not yet live)…
  Solana expansion publicly announced as 'coming soon' (not yet live). This will require a non-EVM bridge pathway (likely still CCIP, which supports Solana) and should be re-assessed when deployed. Current score reflects live-chain surface only.
- **[INFO]** No deployments on Polygon, Arbitrum, Optimism, Avalanche, or any other EVM chain outside E…
  No deployments on Polygon, Arbitrum, Optimism, Avalanche, or any other EVM chain outside Ethereum + Base as of 2026-04-21.
- **[INFO]** Base-side apxUSD token pool + CCIP token admin registry configuration not inspected on-cha…
  Base-side apxUSD token pool + CCIP token admin registry configuration not inspected on-chain in this pass (would require Base RPC). Not treated as a red flag because (a) CCIP lanes ship with RMN by default, and (b) Apyx is the canonical issuer on both ends — no third-party synthetic wrapper.
- **[INFO]** Rubric placement: 2 chains via canonical bridge with RMN sits between '10' (single chain) …
  Rubric placement: 2 chains via canonical bridge with RMN sits between '10' (single chain) and '5-6' (5-7 chains, LZ 2/3 DVN or CCIP+RMN). Scored 8: very small surface (2 chains) + reputable bridge + RMN, with a slight deduction vs. single-chain because multi-chain surface exists at all and Solana expansion will grow it.

### Team Transparency  (score 8, confidence 0.75)

- **[INFO]** Leadership is fully doxxed…
  Leadership is fully doxxed. Four named public figures are associated with Apyx: Joseph Onorati (CEO, ex-Kraken Chief Strategy Officer 2016-2024, current Chairman/CEO of NASDAQ-listed DeFi Development Corp / DFDV), Dan Kang (ex-Kraken Head of Strategy 3y, current CSO at DFDV, prior Morgan Stanley / Snap Corp Dev), Dawson Reid (9y at Kraken full-stack engineering, 15+ years SWE), and Pete Humiston (ex-Jefferies Sales & Trading, current CMO at DFDV, crypto full-time since 2018). All have verifiable LinkedIn profiles.
- **[INFO]** Real-name identities cross-verified against press releases (globenewswire, Nasdaq, Blockwo…
  Real-name identities cross-verified against press releases (globenewswire, Nasdaq, Blockworks), SEC filings (DFDV S-3), and LinkedIn. No pseudonymous core-team members surfaced in public sources.
- **[INFO]** Apyx is characterized in press releases and docs as 'supported by the team behind DeFi Dev…
  Apyx is characterized in press releases and docs as 'supported by the team behind DeFi Development Corp.' DFDV is a US-listed public company (Nasdaq: DFDV), which imposes SEC disclosure, officer-level accountability, and exchange-listing rules on the individuals above — a strong transparency signal.
- **[INFO]** Primary institutional backer: DeFi Development Corp (NASDAQ: DFDV) announced as first inst…
  Primary institutional backer: DeFi Development Corp (NASDAQ: DFDV) announced as first institutional capital in Apyx on 2026-02-26. No tier-1 crypto VC (a16z, Paradigm, Pantera, Polychain, Multicoin, etc.) identified as a backer in public sources — funding base is narrow but reputable rather than obscure.
- **[INFO]** Prior projects of Joseph Onorati include CaVirtEx (Canada's first Bitcoin exchange, he was…
  Prior projects of Joseph Onorati include CaVirtEx (Canada's first Bitcoin exchange, he was interim CEO 2013-2015). CaVirtEx suffered a material security breach/hack in Feb 2015 and subsequently shut down; assets were acquired by Coinsetter (~$2M), later rolled into Kraken. Public sources frame this as a business transaction with no allegation of personal misconduct against Onorati, but any Fira reviewer should note he has been at the helm of a crypto exchange that was hacked and wound down.
- **[INFO]** No evidence of rugpulls, token-launch scams, insider controversies, or sanctioned-jurisdic…
  No evidence of rugpulls, token-launch scams, insider controversies, or sanctioned-jurisdiction connections for any named team member. CaVirtEx hack (2015) was an infrastructure breach, not founder misconduct.
- **[INFO]** Corporate entity of 'Apyx Labs' itself is NOT publicly disclosed on docs…
  Corporate entity of 'Apyx Labs' itself is NOT publicly disclosed on docs.apyx.fi per current sources (team page behind docs site was not directly accessible in this research; public searches return Apyx Medical Corporation, an UNRELATED Delaware-incorporated NASDAQ medical-device company — do not confuse the two).
- **[INFO]** Jurisdiction inference (low confidence): team is US-based (DFDV is headquartered Boca Rato…
  Jurisdiction inference (low confidence): team is US-based (DFDV is headquartered Boca Raton, FL; press releases are US-issued; executives have US LinkedIns). Most likely Delaware C-corp or LLC, but unverified. No Cayman / BVI / Panama footprint observed.
- **[INFO]** GitHub org github…
  GitHub org github.com/apyx-labs lists no public members and no individually attributed top contributors on public repos (evm-contracts, .github, customized-token-list fork). Engineering attribution to named individuals (Dawson Reid) comes from bio text, not commit history. This is a minor opacity but typical for stealth-launch crypto orgs.
- **[INFO]** Apyx has published operational-security posts (blog…
  Apyx has published operational-security posts (blog.apyx.fi/minting-controls/) describing manual minting with multi-sig controls and hard minting limits. Identity of multi-sig signers not publicly disclosed — so while the team is doxxed, the specific individuals holding privileged on-chain keys are not named. Cannot independently confirm that signers == the four named public figures, but absent any anon-team evidence this is a mild concern rather than a red flag.
- **[INFO]** FLAG_ANON_TEAM_WITH_PRIVILEGE NOT raised: team is public, not pseudonymous, so the flag tr…
  FLAG_ANON_TEAM_WITH_PRIVILEGE NOT raised: team is public, not pseudonymous, so the flag trigger (anon + unchecked privilege) is not met. Judge may still want to cross-reference with governance-security findings if that agent uncovers specific privileged addresses without disclosed controllers.
- **[INFO]** Confidence 0…
  Confidence 0.75 (not higher) because: corporate entity/jurisdiction unconfirmed; docs.apyx.fi team page not fetched directly; specific multi-sig signer identities not disclosed; funding cap table beyond DFDV not visible; 'first institutional capital' phrasing suggests other private investors may exist but are undisclosed.

### Liquidity Depth  (score 5, confidence 0.85)

- **[INFO]** On-chain discovery: PT 0x92a6a01b07984de46c24e8eba248449beb8b1dcb -> SY 0x4f116eE5BCD227d1…
  On-chain discovery: PT 0x92a6a01b07984de46c24e8eba248449beb8b1dcb -> SY 0x4f116eE5BCD227d1a1C4f57918D694a4aBe7b3FC -> apxUSD 0x98A878b1Cd98131B271883B390f68D2c90674665. Expiry 1781740800 (2026-06-18). SY:apxUSD is 1:1 (exchangeRate=1e18). SY only accepts/returns apxUSD - no alternate redemption tokens.
- **[INFO]** apxUSD total supply 180M (18 dec)…
  apxUSD total supply 180M (18 dec). Trades at $0.9997 per CoinGecko. DefiLlama confirms circulating supply.
- **[INFO]** Only two meaningful apxUSD/USDC pools on mainnet: Curve StableSwap-NG 0xe1b96555bbeca40e58…
  Only two meaningful apxUSD/USDC pools on mainnet: Curve StableSwap-NG 0xe1b96555bbeca40e583bbb41a11c68ca4706a414 ($16.5M TVL, 0.01% fee, A=100, verified on-chain reserves 8.24M apxUSD + 8.28M USDC) and Uniswap V4 poolId 0x2480aea56b9b5d691713fc84efe6443eadd888773490ef12aed44655d96a63b1 ($17.75M TVL, 0.01% fee, concentrated). Combined ~$34M apxUSD/USDC TVL.
- **[INFO]** Curve slippage ladder apxUSD -> USDC (verified via get_dy on-chain): $100k -> 0…
  Curve slippage ladder apxUSD -> USDC (verified via get_dy on-chain): $100k -> 0.018%, $500k -> 0.066%, $1M -> 0.127%, $2M -> 0.259%, $3M -> 0.416%, $5M -> 0.920%, $7M -> 2.472%. Curve alone: ~$6M depth at 2% slippage.
- **[INFO]** Uniswap V4 slippage ladder (verified via V4 Quoter 0x52f0e24d1c21c8a0cb1e5a5dd6198556bd9e1…
  Uniswap V4 slippage ladder (verified via V4 Quoter 0x52f0e24d1c21c8a0cb1e5a5dd6198556bd9e1203): $500k-$3M -> <0.01% slippage each (extremely tight concentrated liquidity around peg). Swap reverts at $3.5M-$5M - concentrated-liquidity cliff edge, exhausts active tick range. V4 gives effectively free execution up to ~$3M but no tail depth.
- **[INFO]** Aggregator routing (Paraswap, Odos): BOTH route 100% through Curve for all sizes tested ($…
  Aggregator routing (Paraswap, Odos): BOTH route 100% through Curve for all sizes tested ($500k-$10M). Neither aggregator currently integrates the V4 apxUSD/USDC pool. Paraswap at $10M: 8.12M USDC out = 18.8% slippage (Curve-only). Odos priceImpact: $1M=0.12%, $3M=0.41%, $5M=0.91%. 1inch API requires auth - not tested, but historically trails V4 integration.
- **[INFO]** COMBINED practical depth (router using V4 + Curve manually split): at 2% slippage, approxi…
  COMBINED practical depth (router using V4 + Curve manually split): at 2% slippage, approximately $9M total ($3M via V4 until cliff + $6M via Curve before 2% threshold). Realistic single-route aggregator depth today = Curve-only, ~$6M at 2%.
- **[INFO]** PT-apxUSD -> USDC routing: aggregators DO NOT support PT-apxUSD as input…
  PT-apxUSD -> USDC routing: aggregators DO NOT support PT-apxUSD as input. Paraswap returns 'No routes found', Odos returns 'Routing unavailable for token'. Liquidator cannot do single-tx PT->USDC via aggregator - must 3-step: (1) swap PT->SY via Pendle market, (2) redeem SY->apxUSD, (3) swap apxUSD->USDC via aggregator/Curve/V4. Fira-side bot needs custom routing logic (Pendle Router 0x888888888889758F76e7103c6CbF23ABbF58F946 first, then DEX).
- **[INFO]** Pendle AMM state (via routerstatic + on-chain): PT balance in market 2…
  Pendle AMM state (via routerstatic + on-chain): PT balance in market 2.39M, SY balance 3.64M, AMM USD liquidity $5.98M per Pendle data API. Implied APY 14.71%, PT discount 2.15%. PT total supply 49.99M (so only ~4.8% of PT supply is in the AMM). Pendle Pro tool confirms $52.5M total TVL in the pool ecosystem (PT + SY + LP fees). Pendle PT->SY swap depth is quote-constrained - Pendle public SDK/REST API for swap quotes not accessible from this environment (returns 404), could not empirically ladder, but: $500k PT sale ~21% of AMM PT balance, $1M ~43%, $2M ~85%. Rough expectation for a stable 58-day-to-expiry PT with $6M AMM: $500k = 0.2-0.5% slippage, $1M = 0.5-1.2%, $2M = 2-4%, $3M+ likely hits significant slippage. Would need fork simulation to ladder precisely.
- **[INFO]** Post-expiry path (2026-06-18+): PT redeems 1:1 via YT/PT burn through YieldContractFactory…
  Post-expiry path (2026-06-18+): PT redeems 1:1 via YT/PT burn through YieldContractFactory into SY, SY unwraps 1:1 to apxUSD, apxUSD -> USDC via Curve/V4. Post-expiry is significantly safer (no AMM price impact on PT leg), but Fira's fixed-rate market has a maturity grace period mechanism; for PT-apxUSD spec the 24h grace was specified. Liquidator must handle both pre-expiry (PT->SY through Pendle AMM) and post-expiry (PT->SY via redemption) paths.
- **[INFO]** Liquidity concentration risk: two pools totaling ~$34M TVL, both on single chain, apxUSD i…
  Liquidity concentration risk: two pools totaling ~$34M TVL, both on single chain, apxUSD is young (~600 holders per GeckoTerminal). Supply is 180M but concentrated, and Apyx is protocol-owned-liquidity (POL) heavy - if Apyx withdraws POL the depth evaporates. Kraken lists APXUSD/USD but CEX volume is negligible ($3.3k/24h).
- **[INFO]** Fira-specific liquidation sizing: at 88% LLTV and $1-3M position cap, a full liquidation o…
  Fira-specific liquidation sizing: at 88% LLTV and $1-3M position cap, a full liquidation of a max-sized 88% LLTV position yields ~$880k-$2.64M apxUSD to dump. At 2% slippage: $500k-$1M fully liquidatable through Curve alone with <0.15% cost; $2-3M liquidation through Curve = 0.26-0.42% cost (well below 3.73% liq penalty). With V4 manually integrated, liquidator can fit $3M with near-zero cost. Conclusion: at proposed $1M initial cap the liquidation plumbing is viable; at $3M cap it's still viable but thinner. Scaling beyond $5M total market size starts eating the liquidation incentive.
- **[INFO]** Scoring: $6M at 2% single-pool (Curve) + $3M at ~0% single-pool (V4) + aggregator routing …
  Scoring: $6M at 2% single-pool (Curve) + $3M at ~0% single-pool (V4) + aggregator routing works for apxUSD->USDC (not PT input). Two pools, ~$34M combined TVL, but thin tail beyond $6M on Curve and V4 cliff at $3M. Fits rubric band '5-6: $2-10M at 2%, 1-2 pools, routing works'. Net score 5 - viable for proposed $1-3M cap but not scalable, and PT input aggregator gap forces custom multi-hop liquidator routing.

### Controversy  (score 3, confidence 0.75)

- **[INFO]** Apyx = first 'Dividend-Backed Stablecoin' protocol…
  Apyx = first 'Dividend-Backed Stablecoin' protocol. apxUSD is backed by preferred equity (STRC ~11.5%, SATA ~12.75-13%) issued by BTC treasury companies Strategy (MSTR) and Strive (ASST, Vivek Ramaswamy-backed). apyUSD is the yield-bearing savings token. Both live on Pendle (PT/YT 17 Jun 2026 expiry, market `0x50dce085af29caba28f7308bea57c4043757b491`) and Morpho.
- **[INFO]** Founders: Joseph Onorati (CEO Apyx / CEO DFDV; 8 years at Kraken through 2024 as Chief Str…
  Founders: Joseph Onorati (CEO Apyx / CEO DFDV; 8 years at Kraken through 2024 as Chief Strategy Officer; prior interim CEO of CaVirtEx, Canada's first Bitcoin exchange, sold to Coinsetter 2015). Parker White (COO/CIO DFDV, CFA, UT Austin). Both have LEGITIMATE prior-project histories, no rugpull pattern, no reputational red flags. This is NOT a scam team — which is why the score isn't 0-2.
- **[INFO]** GitHub `apyx-labs/evm-contracts`: Solidity, public, created 2026-01-05, last pushed 2026-0…
  GitHub `apyx-labs/evm-contracts`: Solidity, public, created 2026-01-05, last pushed 2026-03-27. Core contracts: ApxUSD.sol, ApyUSD.sol, CommitToken.sol, MinterV0.sol (21KB), RedemptionPoolV0.sol, Roles.sol (12KB), YieldDistributor.sol. 'V0' naming + no audits = early-stage code.
- **[INFO]** Stream Finance xUSD collapse (Nov 2025) was triggered partly by a Balancer hack ($120M exp…
  Stream Finance xUSD collapse (Nov 2025) was triggered partly by a Balancer hack ($120M exploit Nov 3-4 2025) plus a $93M fund manager loss. QuillAudits and others publicly criticized the 'risk curator' model on Morpho/Euler where MEV Capital and others allocated USDC to looped xUSD strategies. Pendle is integrated with Morpho for exactly this kind of loop — PT-apxUSD on Fira as collateral sets up the same mechanical pattern that blew up in November.
- **[INFO]** Elixir deUSD (separate protocol) shut down Nov 2025 after 65% of reserves (~$68M) were len…
  Elixir deUSD (separate protocol) shut down Nov 2025 after 65% of reserves (~$68M) were lent to Stream. Token went from $1.00 to $0.015. This is the worked example of how 'looped' yield-backed stables die.
- **[INFO]** DAT structural risk: Grayscale argues DATs won't be a major 2026 swing factor…
  DAT structural risk: Grayscale argues DATs won't be a major 2026 swing factor. Other research (Tiger Research, AI Invest) explicitly warns DATs 'face shakeout,' 'fragile future,' 'systemic risk.' STRC is described by critics as a potentially reflexive structure; Michael Saylor has been forced to hike STRC dividend multiple times (to 10.75%, then 11.5%) to maintain par. SATA hiked to 13%.
- **[INFO]** BitGo custody is a positive (qualified institutional custodian)…
  BitGo custody is a positive (qualified institutional custodian). Apyx claims monthly PCAOB-registered attestations. But custody ≠ solvency, and attestation lag (30+ days) vs on-chain mark-to-market creates a window for undetected insolvency.
- **[INFO]** Pendle/Penpie precedent: Sept 2024 Penpie reentrancy stole $27M (Pendle saved $105M by pau…
  Pendle/Penpie precedent: Sept 2024 Penpie reentrancy stole $27M (Pendle saved $105M by pausing). Not a recent unrecovered Pendle exploit — Pendle's core contracts were unaffected. Pendle as a dependency is well-trodden, but any PT market inherits Pendle + Aave-style oracle + CR oracle risk.
- **[INFO]** No evidence of tainted on-chain flow (Tornado / OFAC / Lazarus) found in web searches…
  No evidence of tainted on-chain flow (Tornado / OFAC / Lazarus) found in web searches. No rugpull, no SEC/CFTC/FinCEN/OFAC enforcement against Apyx or DFDV team. Would require direct Etherscan/Chainalysis check for final confirmation — marking confidence 0.75 because this one axis was not on-chain-verified.
- **[INFO]** Aggregate positional call: The team is legitimate, the contracts exist publicly, the custo…
  Aggregate positional call: The team is legitimate, the contracts exist publicly, the custody path is institutional. BUT the protocol is structurally and temporally in the exact category + window that just caused $285M+ in DeFi losses. For a FIXED-RATE lending market where liquidations on BT expiry are forced and unrecoverable, the risk-adjusted return for Fira is poor. Wait 6+ months, require a full Sherlock/Spearbit audit, require on-chain CR heartbeat, require independent oracle with fallback, before listing. The red flags are severe enough to hard-cap the final pipeline score at 3.0 per rubric.

## Inputs used for this assessment

- **RPC chain:** unspecified (URL redacted)
- **Docs:** https://apyx.fi/, https://docs.apyx.fi/, https://app.pendle.finance/trade/markets/0x50DCE085af29CABa28f7308beA57C4043757b491, https://app.morpho.org/ethereum/market/0xed05fcc2893b78b3fa468d21b6e4d2925e7f2c64eb1f16279757c43f87502a99/pt-apxusd-18jun2026-usdc
- **Repos:** https://github.com/apyx-labs
- **Controversy seeds:** "(none)"
- **Asset address:** `0x92a6a01b07984de46c24e8eba248449beb8b1dcb`
- **Market type:** fixed
- **Assessment date:** 2026-04-21
