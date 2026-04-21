---
title: PT-apxUSD
score: 5.5
verdict: "fine, I guess, sigh"
redFlags: []
date: 2026-04-21
---

<div class="score-banner">
  <div class="speedometer"><svg class="risk-speedometer" width="420" height="240" viewBox="0 0 420 240" xmlns="http://www.w3.org/2000/svg" role="img" aria-label="Asset risk score 5.5 of 10">
  <!-- subtle drop-shadow filter -->
  <defs>
    <filter id="dsoft" x="-20%" y="-20%" width="140%" height="140%">
      <feGaussianBlur stdDeviation="2"/>
    </filter>
  </defs>
  <!-- background arc (mid-gray, visible on both themes) -->
  <path d="M 50 210 A 160 160 0 0 1 370 210" stroke="#6b7280" stroke-width="22" fill="none" stroke-linecap="round"/>
  <!-- colored zones: red 0-3, amber 3-7, green 7-10 -->
  <path d="M 50 210 A 160 160 0 0 1 162 61" stroke="#ef4444" stroke-width="22" fill="none" stroke-linecap="round"/>
  <path d="M 162 61 A 160 160 0 0 1 258 61" stroke="#f59e0b" stroke-width="22" fill="none" stroke-linecap="round"/>
  <path d="M 258 61 A 160 160 0 0 1 370 210" stroke="#10b981" stroke-width="22" fill="none" stroke-linecap="round"/>
  <!-- needle shadow -->
  <line x1="210" y1="210" x2="210" y2="70" stroke="black" stroke-opacity="0.35" stroke-width="8" stroke-linecap="round" filter="url(#dsoft)" transform="rotate(9.0, 210, 210)"/>
  <!-- needle: white fill with dark outline for legibility on both themes -->
  <line x1="210" y1="210" x2="210" y2="70" stroke="#111" stroke-width="7" stroke-linecap="round" transform="rotate(9.0, 210, 210)"/>
  <line x1="210" y1="210" x2="210" y2="70" stroke="#ffffff" stroke-width="4" stroke-linecap="round" transform="rotate(9.0, 210, 210)"/>
  <!-- hub -->
  <circle cx="210" cy="210" r="11" fill="#111" stroke="#ffffff" stroke-width="2"/>
  <!-- score label: white fill with black stroke outline so it works on any bg -->
  <text x="210" y="195" text-anchor="middle" font-family="system-ui, -apple-system, Segoe UI, sans-serif" font-size="44" font-weight="800" fill="#ffffff" stroke="#000000" stroke-width="4" paint-order="stroke fill" stroke-linejoin="round">5.5</text>
  <!-- "/10" subscript -->
  <text x="210" y="225" text-anchor="middle" font-family="system-ui, -apple-system, Segoe UI, sans-serif" font-size="14" font-weight="600" fill="#9ca3af" stroke="#000000" stroke-width="2" paint-order="stroke fill">out of 10</text>
</svg></div>
  <div class="meme"><img src="/assets/score-6.png" alt="score 6 meme"/></div>
</div>

<p class="verdict-tagline"><em>fine, I guess, sigh</em></p>

## Judge's verdict

### ✅ What looks good

- Fully-doxxed, high-reputation team: ex-Kraken ops (Onorati/Kang/Reid/Humiston) with NASDAQ-listed DFDV as sponsor — strong transparency signal (team-transparency 8.0).
- Custody + attestation stack is institutional-grade: BitGo qualified custodian plus PCAOB-audited monthly reserve attestations — rare in DeFi stables.
- All 5 core Apyx contracts verified on Etherscan (apxUSD, CR capped+raw, AccessManager, impls) and audit bar met: Quantstamp, Certora, Zellic all 2026.
- Cross-chain surface is small and safe-by-construction: Chainlink CCIP with RMN enabled, limited to Ethereum + Base (cross-chain 8.0).
- Pendle PT layer is standard V2 code — engineering risk concentrates on the apxUSD collateral layer, not the wrapper.
- apxUSD minting is not unbounded EOA: MinterV0 enforces 10M/day cap gated by 3/6 Safe + 4h delay.
- Liquidity plumbing adequate at proposed cap: Curve NG + Uni v4 ≈ $34M combined TVL, max-dump slippage 0.15–0.42%.

### ⚠ What worries me

- Governance (3.0): 4/6 ADMIN Safe can `upgradeToAndCall` CR feeds with ZERO timelock — no function-role mappings, `getTargetAdminDelay=0`. Biggest single fixable issue.
- CR oracle feeds are stale ~30 days with no on-chain heartbeat and no operator role bound — Fira's Apyx oracle-DD concern, still unaddressed.
- ADMIN (4/6) and MAINTAINER-LONG (3/6) Safes share 5-of-6 signer keys — separation of duties is nominal, not real.
- Structural echo of Nov 2025 xUSD/Stream collapse (yield-stable → Pendle PT → Morpho loop); BitGo custody + public-equity sponsor mitigate, but pattern recently failed at scale.
- apxUSD `pause()` is instant at 3/6 quorum → direct DoS lever on Fira liquidation flow if Apyx pauses mid-liquidation.
- AccessManager self-admin delay = 0; ADMIN can re-route role mappings on any zero-delay target in a single tx.
- No public bug-bounty program (Immunefi/Cantina) — pulls code-quality down despite 3 audits.
- Aggregators (Paraswap, Odos) do not route PT-apxUSD as input — liquidator needs a bespoke 3-hop PT→SY→apxUSD→USDC path pre-expiry.

### 🎯 Verdict

**Verdict:** borderline — moderate risk, listable only at a conservative cap

Rationale one-liner: Score 5.5 reflects strong team/custody/liquidity and standard Pendle wrapping against a zero-delay CR-oracle upgrade path, stale feeds, and 5/6 signer overlap between ADMIN and MAINTAINER Safes.


## Contracts & Multisigs

Canonical addresses for the protocol. Click any address to open it on the block explorer.

| Label | Address | Type | Notes |
|---|---|---|---|
| PT-apxUSD-18JUN2026 (Pendle PT) | [`0x92a6a01b07984de46c24e8eba248449beb8b1dcb`](https://etherscan.io/address/0x92a6a01b07984de46c24e8eba248449beb8b1dcb) | ERC-20 (PT) | Collateral token. Expiry 1781740800 (2026-06-18). |
| SY-apxUSD | [`0x4f116eE5BCD227d1a1C4f57918D694a4aBe7b3FC`](https://etherscan.io/address/0x4f116eE5BCD227d1a1C4f57918D694a4aBe7b3FC) | ERC1967Proxy (Pendle SY) | Holds ~53.6M apxUSD. Upgradeable. |
| YT-apxUSD | [`0x7807c638383B95aC5d58De10d3079e2140D47C22`](https://etherscan.io/address/0x7807c638383B95aC5d58De10d3079e2140D47C22) | ERC-20 (YT) | Pendle yield token. |
| Pendle PT↔SY AMM | [`0x50DCE085af29CABa28f7308beA57C4043757b491`](https://etherscan.io/address/0x50DCE085af29CABa28f7308beA57C4043757b491) | Pendle Market | Primary liquidation path pre-expiry. |
| apxUSD token | [`0x98A878b1Cd98131B271883B390f68D2c90674665`](https://etherscan.io/address/0x98A878b1Cd98131B271883B390f68D2c90674665) | UUPS proxy | Implementation 0xDd71…ccB4. Mint gated by MinterV0. |
| apxUSD implementation | [`0xDd71Fd677fde2ed2579a3c45204f41a11016ccB4`](https://etherscan.io/address/0xDd71Fd677fde2ed2579a3c45204f41a11016ccB4) | Logic | Swappable via role 24 + 3d delay. |
| MinterV0 (mint controller) | [`0x2c36e1adFaA80ee0324B04cC814F5207Bb7Ba76e`](https://etherscan.io/address/0x2c36e1adFaA80ee0324B04cC814F5207Bb7Ba76e) | Contract (role 4) | 10M/day mint cap, signed EIP-712 orders, 4h role delay. |
| AccessManager | [`0xe167330E2Eac88666de253e9607C6d9ae0cA2824`](https://etherscan.io/address/0xe167330E2Eac88666de253e9607C6d9ae0cA2824) | OZ AccessManager | Self-admin delay = 0. Role 0 grant delay = 7d. |
| Apyx Capped CR oracle (Morpho BASE_FEED_2) | [`0x2037a5Eb67aa9B2FBF50042B724D8c4dB80F23b4`](https://etherscan.io/address/0x2037a5Eb67aa9B2FBF50042B724D8c4dB80F23b4) | UUPS proxy | Target admin delay = 0. Stale ~30 days at assessment. |
| Apyx Raw CR oracle | [`0x823210Eb6390B88e2b8ad7152DF5D8F30B8FD305`](https://etherscan.io/address/0x823210Eb6390B88e2b8ad7152DF5D8F30B8FD305) | UUPS proxy | Target admin delay = 0. Feeds capped oracle. |
| Morpho PT-apxUSD oracle | [`0x4DFceF82eaEE9eA817bEb1279336F7D0Ebf2b685`](https://etherscan.io/address/0x4DFceF82eaEE9eA817bEb1279336F7D0Ebf2b685) | MorphoChainlinkOracleV2 | Consumes capped CR feed as BASE_FEED_2. |
| ADMIN Safe (4/6) | [`0xabdd8c8ee69e5f5180eb9352aeffc5ceead65e96`](https://etherscan.io/address/0xabdd8c8ee69e5f5180eb9352aeffc5ceead65e96) | Gnosis Safe 4-of-6 | Holds AccessManager role 0. 0 exec delay. No Safe Guard/Modules. |
| MAINTAINER-LONG Safe (3/6) | [`0xf9862efc1704ac05e687f66e5cd8c130e5663ce2`](https://etherscan.io/address/0xf9862efc1704ac05e687f66e5cd8c130e5663ce2) | Gnosis Safe 3-of-6 | Roles 2/21/22/23/24/25. Shares 5-of-6 owners with ADMIN Safe. |

## Access-control walk

A numbered walkthrough for verifying this asset's access-control surface yourself. Start at step 1, run the commands, follow the `Next` pointers.

### Step 1 — PT-apxUSD token (Pendle PT)

Address: [`0x92a6a01b07984de46c24e8eba248449beb8b1dcb`](https://etherscan.io/address/0x92a6a01b07984de46c24e8eba248449beb8b1dcb)

*Why*: Start here — this is the asset Fira would seize on liquidation. Pendle PTs are non-upgradeable and only the paired YT can mint/burn, so you confirm immutability and follow the YT/SY pointer.

```bash
# PT mint/burn is gated to paired YT — confirm the address
cast call 0x92a6a01b07984de46c24e8eba248449beb8b1dcb 'YT()(address)' --rpc-url $RPC
# → expect: 0x7807c638383B95aC5d58De10d3079e2140D47C22
# Find the SY (owns the underlying apxUSD)
cast call 0x92a6a01b07984de46c24e8eba248449beb8b1dcb 'SY()(address)' --rpc-url $RPC
# → expect: 0x4f116eE5BCD227d1a1C4f57918D694a4aBe7b3FC
# Confirm non-upgradeable — no EIP-1967 impl slot
cast storage 0x92a6a01b07984de46c24e8eba248449beb8b1dcb 0x360894a13ba1a3210667c828492db98dca3e2076cc3735a920a3ca505d382bbc --rpc-url $RPC
# → expect: 0x0000…0000 (not a proxy)
```

**Next:** Step 2 (YT-apxUSD) → Step 3 (SY-apxUSD (Pendle Standardized Yield wrapper))

### Step 2 — YT-apxUSD

Address: [`0x7807c638383B95aC5d58De10d3079e2140D47C22`](https://etherscan.io/address/0x7807c638383B95aC5d58De10d3079e2140D47C22)

*Why*: The YT is the only address allowed to call mint/burn on the PT. Standard Pendle V2 YieldContract — no admin of its own; it delegates to the Pendle factory and the SY.

```bash
# Confirm YT's SY pointer matches step 1's SY
cast call 0x7807c638383B95aC5d58De10d3079e2140D47C22 'SY()(address)' --rpc-url $RPC
# → expect: 0x4f116eE5BCD227d1a1C4f57918D694a4aBe7b3FC
# Find the Pendle factory that deployed this YT (for gov context)
cast call 0x7807c638383B95aC5d58De10d3079e2140D47C22 'factory()(address)' --rpc-url $RPC
# → expect: Pendle YieldContractFactory (immutable)
```

**Next:** Step 4 (apxUSD token (underlying, AccessManaged UUPS))

### Step 3 — SY-apxUSD (Pendle Standardized Yield wrapper)

Address: [`0x4f116eE5BCD227d1a1C4f57918D694a4aBe7b3FC`](https://etherscan.io/address/0x4f116eE5BCD227d1a1C4f57918D694a4aBe7b3FC)

*Why*: SY holds the real apxUSD on behalf of PT/YT holders. It is an ERC1967 proxy — confirm who can upgrade it, since a malicious SY upgrade is the cleanest exit route for held apxUSD.

```bash
# Read the EIP-1967 implementation slot
cast storage 0x4f116eE5BCD227d1a1C4f57918D694a4aBe7b3FC 0x360894a13ba1a3210667c828492db98dca3e2076cc3735a920a3ca505d382bbc --rpc-url $RPC
# → expect: current SY implementation address
# Read the EIP-1967 admin slot — who can call upgradeToAndCall
cast storage 0x4f116eE5BCD227d1a1C4f57918D694a4aBe7b3FC 0xb53127684a568b3173ae13b9f8a6016e243e63b6e8ee1178d6a717850b5d6103 --rpc-url $RPC
# → expect: Pendle governance multisig or ProxyAdmin — cross-check against Pendle's published governance
# Confirm SY's yield-token pointer is apxUSD
cast call 0x4f116eE5BCD227d1a1C4f57918D694a4aBe7b3FC 'yieldToken()(address)' --rpc-url $RPC
# → expect: 0x98A878b1Cd98131B271883B390f68D2c90674665 (apxUSD)
```

**Next:** Step 4 (apxUSD token (underlying, AccessManaged UUPS))

### Step 4 — apxUSD token (underlying, AccessManaged UUPS)

Address: [`0x98A878b1Cd98131B271883B390f68D2c90674665`](https://etherscan.io/address/0x98A878b1Cd98131B271883B390f68D2c90674665)

*Why*: This is where all the real access-control risk lives. apxUSD is a UUPS proxy governed by an OpenZeppelin AccessManager. `mint`, `pause`, `setDenyList`, `upgradeToAndCall` all route through it.

```bash
# Find the AccessManager (the authority)
cast call 0x98A878b1Cd98131B271883B390f68D2c90674665 'authority()(address)' --rpc-url $RPC
# → expect: 0xe167330E2Eac88666de253e9607C6d9ae0cA2824
# Read current implementation
cast storage 0x98A878b1Cd98131B271883B390f68D2c90674665 0x360894a13ba1a3210667c828492db98dca3e2076cc3735a920a3ca505d382bbc --rpc-url $RPC
# → expect: 0xDd71Fd677fde2ed2579a3c45204f41a11016ccB4
# Which role gates mint? (selector 0x40c10f19)
cast call 0xe167330E2Eac88666de253e9607C6d9ae0cA2824 'getTargetFunctionRole(address,bytes4)(uint64)' 0x98A878b1Cd98131B271883B390f68D2c90674665 0x40c10f19 --rpc-url $RPC
# → expect: 4 (MINTER_CONTRACT_4HR — points at MinterV0)
# Which role gates upgradeToAndCall? (selector 0x4f1ef286)
cast call 0xe167330E2Eac88666de253e9607C6d9ae0cA2824 'getTargetFunctionRole(address,bytes4)(uint64)' 0x98A878b1Cd98131B271883B390f68D2c90674665 0x4f1ef286 --rpc-url $RPC
# → expect: 24 (MAINTAINER_LONG)
# apxUSD target admin delay
cast call 0xe167330E2Eac88666de253e9607C6d9ae0cA2824 'getTargetAdminDelay(address)(uint32)' 0x98A878b1Cd98131B271883B390f68D2c90674665 --rpc-url $RPC
# → expect: 259200 (3 days)
```

**Next:** Step 5 (MinterV0 (mint controller, AccessManager role 4)) → Step 6 (MAINTAINER-LONG Safe (3-of-6, apxUSD upgrader))

### Step 5 — MinterV0 (mint controller, AccessManager role 4)

Address: [`0x2c36e1adFaA80ee0324B04cC814F5207Bb7Ba76e`](https://etherscan.io/address/0x2c36e1adFaA80ee0324B04cC814F5207Bb7Ba76e)

*Why*: MinterV0 is what actually mints apxUSD. It enforces a 10M/day rate cap and requires signed EIP-712 orders — but its `requestMint` is gated by role 2, held by the MAINTAINER 3/6 Safe, so a 3/6 quorum ultimately controls issuance subject to the per-day cap.

```bash
# Confirm MinterV0's authority is the same AccessManager
cast call 0x2c36e1adFaA80ee0324B04cC814F5207Bb7Ba76e 'authority()(address)' --rpc-url $RPC
# → expect: 0xe167330E2Eac88666de253e9607C6d9ae0cA2824
# Which role gates MinterV0.requestMint?
cast call 0xe167330E2Eac88666de253e9607C6d9ae0cA2824 'getTargetFunctionRole(address,bytes4)(uint64)' 0x2c36e1adFaA80ee0324B04cC814F5207Bb7Ba76e $(cast sig 'requestMint(...)' || echo '0x00000000') --rpc-url $RPC
# → expect: 2 (MINTER_CONTRACT) — held by MAINTAINER Safe 0xf9862…
# Inspect the daily mint cap (state var — varies by impl)
cast call 0x2c36e1adFaA80ee0324B04cC814F5207Bb7Ba76e 'mintCapDaily()(uint256)' --rpc-url $RPC
# → expect: 10_000_000e18 (10M apxUSD/day)
```

**Next:** Step 7 (ADMIN Safe (4-of-6, AccessManager role 0))

### Step 6 — MAINTAINER-LONG Safe (3-of-6, apxUSD upgrader)

Address: [`0xf9862efc1704ac05e687f66e5cd8c130e5663ce2`](https://etherscan.io/address/0xf9862efc1704ac05e687f66e5cd8c130e5663ce2)

*Why*: Holds role 24 (apxUSD upgradeToAndCall, 3-day exec delay) plus pause (role 21, instant), setDenyList/setSupplyCap (role 23, 1-day), setCCIPAdmin (role 25, 7-day). 3 of its 6 keys can push an apxUSD upgrade after 3 days.

```bash
# Threshold
cast call 0xf9862efc1704ac05e687f66e5cd8c130e5663ce2 'getThreshold()(uint256)' --rpc-url $RPC
# → expect: 3
# Owners (compare to ADMIN Safe owners from Step 7)
cast call 0xf9862efc1704ac05e687f66e5cd8c130e5663ce2 'getOwners()(address[])' --rpc-url $RPC
# → expect: 6 EOAs — 5 overlap with ADMIN Safe at step 7
# No Safe Guard active
cast storage 0xf9862efc1704ac05e687f66e5cd8c130e5663ce2 0x4a204f620c8c5ccdca3fd54d003badd85ba500436a431f0cbda4f558c93c34c8 --rpc-url $RPC
# → expect: 0x0000…0000
```

**Next:** Step 7 (ADMIN Safe (4-of-6, AccessManager role 0))

### Step 7 — ADMIN Safe (4-of-6, AccessManager role 0)

Address: [`0xabdd8c8ee69e5f5180eb9352aeffc5ceead65e96`](https://etherscan.io/address/0xabdd8c8ee69e5f5180eb9352aeffc5ceead65e96)

*Why*: Top of the tree. Role 0 can grant/revoke any role, rewrite target↔role mappings, and upgrade the two CR oracle feeds INSTANTLY (their target admin delay is 0). Losing 4 keys here = total compromise.

```bash
# Threshold
cast call 0xabdd8c8ee69e5f5180eb9352aeffc5ceead65e96 'getThreshold()(uint256)' --rpc-url $RPC
# → expect: 4
# Owners
cast call 0xabdd8c8ee69e5f5180eb9352aeffc5ceead65e96 'getOwners()(address[])' --rpc-url $RPC
# → expect: 6 EOAs (5 overlap with MAINTAINER Safe)
# Confirm ADMIN holds role 0
cast call 0xe167330E2Eac88666de253e9607C6d9ae0cA2824 'hasRole(uint64,address)(bool,uint32)' 0 0xabdd8c8ee69e5f5180eb9352aeffc5ceead65e96 --rpc-url $RPC
# → expect: (true, 0)  # bool=true, execDelay=0
# No Safe modules
cast call 0xabdd8c8ee69e5f5180eb9352aeffc5ceead65e96 'getModulesPaginated(address,uint256)(address[],address)' 0x0000000000000000000000000000000000000001 100 --rpc-url $RPC
# → expect: ([], 0x0000…0001)
```

**Next:** Step 8 (Apyx Capped CR oracle (Morpho BASE_FEED_2, AccessManager target))

### Step 8 — Apyx Capped CR oracle (Morpho BASE_FEED_2, AccessManager target)

Address: [`0x2037a5Eb67aa9B2FBF50042B724D8c4dB80F23b4`](https://etherscan.io/address/0x2037a5Eb67aa9B2FBF50042B724D8c4dB80F23b4)

*Why*: The CR feed is the oracle input to Morpho's PT-apxUSD market oracle. Target admin delay is 0 and no function roles are set, so every selector falls through to role 0 (ADMIN) with zero delay — a 4/6 ADMIN tx can replace this impl in one transaction and reprice the collateral.

```bash
# Target admin delay on the capped CR feed
cast call 0xe167330E2Eac88666de253e9607C6d9ae0cA2824 'getTargetAdminDelay(address)(uint32)' 0x2037a5Eb67aa9B2FBF50042B724D8c4dB80F23b4 --rpc-url $RPC
# → expect: 0 (INSTANT)
# Confirm ADMIN Safe can upgrade the CR feed with zero delay
cast call 0xe167330E2Eac88666de253e9607C6d9ae0cA2824 'canCall(address,address,bytes4)(bool,uint32)' 0xabdd8c8ee69e5f5180eb9352aeffc5ceead65e96 0x2037a5Eb67aa9B2FBF50042B724D8c4dB80F23b4 0x4f1ef286 --rpc-url $RPC
# → expect: (true, 0)
# Check feed staleness — read updatedAt
cast call 0x2037a5Eb67aa9B2FBF50042B724D8c4dB80F23b4 'latestRoundData()(uint80,int256,uint256,uint256,uint80)' --rpc-url $RPC
# → expect: updatedAt ≈ 1774192391 (~30 days stale at the time of writing)
```

**Next:** Step 9 (Apyx Raw CR oracle (feeds the capped oracle))

### Step 9 — Apyx Raw CR oracle (feeds the capped oracle)

Address: [`0x823210Eb6390B88e2b8ad7152DF5D8F30B8FD305`](https://etherscan.io/address/0x823210Eb6390B88e2b8ad7152DF5D8F30B8FD305)

*Why*: Upstream of step 8. Same AccessManager, same zero target admin delay — same 4/6 ADMIN instant-upgrade hazard. A compromise here propagates into the capped feed and then into Morpho's oracle.

```bash
# Target admin delay on the raw CR feed
cast call 0xe167330E2Eac88666de253e9607C6d9ae0cA2824 'getTargetAdminDelay(address)(uint32)' 0x823210Eb6390B88e2b8ad7152DF5D8F30B8FD305 --rpc-url $RPC
# → expect: 0 (INSTANT)
# updatedAt on raw CR feed
cast call 0x823210Eb6390B88e2b8ad7152DF5D8F30B8FD305 'latestRoundData()(uint80,int256,uint256,uint256,uint80)' --rpc-url $RPC
# → expect: updatedAt ≈ 1774192391 — same stale window
```

**End of branch.**

## Per-criterion scores

| Criterion | Weight | Score | Confidence |
|---|---:|---:|---:|
| Governance & Security | 30% | 3.0 | 0.88 |
| Asset Controls | 25% | 6.0 | 0.85 |
| Cross-Chain Surface | 15% | 8.0 | 0.85 |
| Code Quality | 10% | 7.0 | 0.65 |
| Controversy | 10% | 5.0 | 0.75 |
| Team Transparency | 5% | 8.0 | 0.75 |
| Liquidity Depth | 5% | 5.0 | 0.85 |

## Detailed findings

### Governance & Security  (score 3, confidence 0.88)

- <span class="sev-badge sev-critical">[CRITICAL]</span> **4-of-6 ADMIN Safe can swap CR oracle implementation instantly (no timelock)**
  Both CR feeds are UUPS proxies managed by the AccessManager with `getTargetAdminDelay = 0` and no function-role mappings, so every selector defaults to role 0 (ADMIN) with 0-second execution delay. A hostile 4-of-6 quorum on ADMIN can `upgradeToAndCall` either feed in a single transaction, letting them inflate or zero the apxUSD price feed before Hexagate monitors or the Fira liquidator bot can react. This is the red-flag anchor — everything else below is contributing context.

  **Verify on-chain:**

  ```bash
  # ADMIN Safe can instantly upgrade capped CR feed
  cast call 0xe167330E2Eac88666de253e9607C6d9ae0cA2824 'canCall(address,address,bytes4)(bool,uint32)' 0xabdd8c8ee69e5f5180eb9352aeffc5ceead65e96 0x2037a5Eb67aa9B2FBF50042B724D8c4dB80F23b4 0x4f1ef286 --rpc-url $RPC
  # → expect: (true, 0)  # bool=true, delay=0
  # Same for raw CR feed
  cast call 0xe167330E2Eac88666de253e9607C6d9ae0cA2824 'canCall(address,address,bytes4)(bool,uint32)' 0xabdd8c8ee69e5f5180eb9352aeffc5ceead65e96 0x823210Eb6390B88e2b8ad7152DF5D8F30B8FD305 0x4f1ef286 --rpc-url $RPC
  # → expect: (true, 0)
  # Confirm admin delay is zero on both
  cast call 0xe167330E2Eac88666de253e9607C6d9ae0cA2824 'getTargetAdminDelay(address)(uint32)' 0x2037a5Eb67aa9B2FBF50042B724D8c4dB80F23b4 --rpc-url $RPC
  # → expect: 0
  # No function-role mappings ever set (0 events)
  cast rpc eth_getLogs '[{"address":"0xe167330E2Eac88666de253e9607C6d9ae0cA2824","topics":["0x9ea6790c...",null,null,"0000000000000000000000002037a5eb67aa9b2fbf50042b724d8c4db80f23b4"]}]' --rpc-url $RPC | jq length
  # → expect: 0
  ```

  **Key addresses:**

  - AccessManager — [`0xe167330E2Eac88666de253e9607C6d9ae0cA2824`](https://etherscan.io/address/0xe167330E2Eac88666de253e9607C6d9ae0cA2824)
  - ADMIN Safe (4/6) — [`0xabdd8c8ee69e5f5180eb9352aeffc5ceead65e96`](https://etherscan.io/address/0xabdd8c8ee69e5f5180eb9352aeffc5ceead65e96)
  - CR capped (UUPS proxy) — [`0x2037a5Eb67aa9B2FBF50042B724D8c4dB80F23b4`](https://etherscan.io/address/0x2037a5Eb67aa9B2FBF50042B724D8c4dB80F23b4)
  - CR raw (UUPS proxy) — [`0x823210Eb6390B88e2b8ad7152DF5D8F30B8FD305`](https://etherscan.io/address/0x823210Eb6390B88e2b8ad7152DF5D8F30B8FD305)
  - Morpho oracle (consumer) — [`0x4DFceF82eaEE9eA817bEb1279336F7D0Ebf2b685`](https://etherscan.io/address/0x4DFceF82eaEE9eA817bEb1279336F7D0Ebf2b685)

- <span class="sev-badge sev-critical">[CRITICAL]</span> **CR oracle feeds stale ~30 days — no on-chain heartbeat, no oracle-operator role**
  Both CR feeds have `updatedAt` ~29.7 days old at the assessment block. No dedicated updater role has ever been bound (TargetFunctionRoleUpdated count = 0 on both targets), so the 4-of-6 ADMIN is the only entity with write authority — there is no running heartbeat bot. `MorphoChainlinkOracleV2` does not enforce `updatedAt` staleness checks, so downstream consumers silently use whatever value is latched.

  **Verify on-chain:**

  ```bash
  # Capped CR feed latestRoundData
  cast call 0x2037a5Eb67aa9B2FBF50042B724D8c4dB80F23b4 'latestRoundData()(uint80,int256,uint256,uint256,uint80)' --rpc-url $RPC
  # → expect: updatedAt ~ 1774192391 (~2026-03-22); compare to block.timestamp
  # Raw CR feed latestRoundData
  cast call 0x823210Eb6390B88e2b8ad7152DF5D8F30B8FD305 'latestRoundData()(uint80,int256,uint256,uint256,uint80)' --rpc-url $RPC
  # → expect: updatedAt ~ 1774192391
  # Age in seconds
  echo $(( $(cast block latest --field timestamp --rpc-url $RPC) - 1774192391 ))
  # → expect: ~2,500,000+ s (29+ days)
  ```

  **Key addresses:**

  - CR capped — [`0x2037a5Eb67aa9B2FBF50042B724D8c4dB80F23b4`](https://etherscan.io/address/0x2037a5Eb67aa9B2FBF50042B724D8c4dB80F23b4)
  - CR raw — [`0x823210Eb6390B88e2b8ad7152DF5D8F30B8FD305`](https://etherscan.io/address/0x823210Eb6390B88e2b8ad7152DF5D8F30B8FD305)

- <span class="sev-badge sev-high">[HIGH]</span> **ADMIN Safe is only 4-of-6; below Fira's 5/9+ policy for fund-critical surfaces**
  ADMIN Safe has zero-delay upgrade power over both CR feeds AND zero-delay authority to reconfigure AccessManager itself. No Safe Guard, no Safe Modules. Effective trust: any 4 of 6 signers cannot be compromised or collude. Fira policy requires 5/9+ on comparable surfaces.

  **Verify on-chain:**

  ```bash
  # Threshold check
  cast call 0xabdd8c8ee69e5f5180eb9352aeffc5ceead65e96 'getThreshold()(uint256)' --rpc-url $RPC
  # → expect: 4
  # Owners (count + identities)
  cast call 0xabdd8c8ee69e5f5180eb9352aeffc5ceead65e96 'getOwners()(address[])' --rpc-url $RPC
  # → expect: 6 EOAs
  # No custom modules
  cast call 0xabdd8c8ee69e5f5180eb9352aeffc5ceead65e96 'getModulesPaginated(address,uint256)(address[],address)' 0x0000000000000000000000000000000000000001 100 --rpc-url $RPC
  # → expect: ([], 0x0000…0001)
  # No guard (storage slot 0x4a204f62…)
  cast storage 0xabdd8c8ee69e5f5180eb9352aeffc5ceead65e96 0x4a204f62c4808f4b5ce0aa2a1fcc9b7e3dd1dc4d9e62a7e47b27f5e3c4c3d92e --rpc-url $RPC
  # → expect: 0x0000…0000
  ```

  **Key addresses:**

  - ADMIN Safe — [`0xabdd8c8ee69e5f5180eb9352aeffc5ceead65e96`](https://etherscan.io/address/0xabdd8c8ee69e5f5180eb9352aeffc5ceead65e96)

- <span class="sev-badge sev-high">[HIGH]</span> **No effective separation of duties between ADMIN and MAINTAINER Safes**
  ADMIN (4/6) and MAINTAINER-LONG (3/6) share 5 of 6 signers. Apyx blog claims an upcoming split to a "separate master multi-sig" but on-chain the owner sets overlap. A single group of 4 compromised keys reaches either path (ADMIN needs 4, MAINTAINER needs 3).

  **Verify on-chain:**

  ```bash
  # Owners of ADMIN vs MAINTAINER
  cast call 0xabdd8c8ee69e5f5180eb9352aeffc5ceead65e96 'getOwners()(address[])' --rpc-url $RPC
  # → expect: [0xb51F…, 0xD6bB…, 0xcFCF…, 0xB98c…, 0x5db4…, 0xd66a…]
  cast call 0xf9862efc1704ac05e687f66e5cd8c130e5663ce2 'getOwners()(address[])' --rpc-url $RPC
  # → expect: 5 of 6 overlap with ADMIN
  cast call 0xf9862efc1704ac05e687f66e5cd8c130e5663ce2 'getThreshold()(uint256)' --rpc-url $RPC
  # → expect: 3
  ```

  **Key addresses:**

  - ADMIN Safe (4/6) — [`0xabdd8c8ee69e5f5180eb9352aeffc5ceead65e96`](https://etherscan.io/address/0xabdd8c8ee69e5f5180eb9352aeffc5ceead65e96)
  - MAINTAINER-LONG Safe (3/6) — [`0xf9862efc1704ac05e687f66e5cd8c130e5663ce2`](https://etherscan.io/address/0xf9862efc1704ac05e687f66e5cd8c130e5663ce2)
  - Apyx blog claim

- <span class="sev-badge sev-medium">[MEDIUM]</span> **apxUSD `upgradeToAndCall` gated by 3/6 MAINTAINER-LONG + 3-day exec delay**
  apxUSD proxy upgrade requires role 24 (MAINTAINER_LONG, held by 3/6 Safe) and waits 259 200 s (3 days). 3-day window is on the short side for an upgradeable stablecoin but is enforced (unlike the CR feeds). Fira liquidators must monitor AccessManager `OperationScheduled` events and be ready to unwind within the 3-day window.

  **Verify on-chain:**

  ```bash
  cast call 0xe167330E2Eac88666de253e9607C6d9ae0cA2824 'canCall(address,address,bytes4)(bool,uint32)' 0xf9862efc1704ac05e687f66e5cd8c130e5663ce2 0x98A878b1Cd98131B271883B390f68D2c90674665 0x4f1ef286 --rpc-url $RPC
  # → expect: (false, 259200)  # must schedule, 3-day delay
  cast call 0xe167330E2Eac88666de253e9607C6d9ae0cA2824 'getTargetAdminDelay(address)(uint32)' 0x98A878b1Cd98131B271883B390f68D2c90674665 --rpc-url $RPC
  # → expect: 259200
  cast call 0xe167330E2Eac88666de253e9607C6d9ae0cA2824 'getTargetFunctionRole(address,bytes4)(uint64)' 0x98A878b1Cd98131B271883B390f68D2c90674665 0x4f1ef286 --rpc-url $RPC
  # → expect: 24  # ROLE_MAINTAINER_LONG
  ```

  **Key addresses:**

  - AccessManager — [`0xe167330E2Eac88666de253e9607C6d9ae0cA2824`](https://etherscan.io/address/0xe167330E2Eac88666de253e9607C6d9ae0cA2824)
  - apxUSD proxy — [`0x98A878b1Cd98131B271883B390f68D2c90674665`](https://etherscan.io/address/0x98A878b1Cd98131B271883B390f68D2c90674665)
  - apxUSD impl — [`0xDd71Fd677fde2ed2579a3c45204f41a11016ccB4`](https://etherscan.io/address/0xDd71Fd677fde2ed2579a3c45204f41a11016ccB4)
  - MAINTAINER-LONG (3/6) — [`0xf9862efc1704ac05e687f66e5cd8c130e5663ce2`](https://etherscan.io/address/0xf9862efc1704ac05e687f66e5cd8c130e5663ce2)

- <span class="sev-badge sev-medium">[MEDIUM]</span> **Role 31 (GUARDIAN) has grantDelay = 0 and 7 EOA members co-extensive with ADMIN**
  GUARDIAN can cancel scheduled operations of supervised roles (including role 24 upgrades). `getRoleGrantDelay(31) = 0` means ADMIN can add/remove guardians instantly. Members include the 6 ADMIN Safe owners + 1 additional EOA — no independent stop on ADMIN.

  **Verify on-chain:**

  ```bash
  cast call 0xe167330E2Eac88666de253e9607C6d9ae0cA2824 'getRoleGrantDelay(uint64)(uint32)' 31 --rpc-url $RPC
  # → expect: 0
  # Enumerate RoleGranted for roleId=31
  cast logs --address 0xe167330E2Eac88666de253e9607C6d9ae0cA2824 'RoleGranted(uint64,address,uint32,uint48,bool)' --topic2 0x000000000000000000000000000000000000000000000000000000000000001f --rpc-url $RPC
  # → expect: 7 distinct addresses
  ```

  **Key addresses:**

  - AccessManager — [`0xe167330E2Eac88666de253e9607C6d9ae0cA2824`](https://etherscan.io/address/0xe167330E2Eac88666de253e9607C6d9ae0cA2824)

- <span class="sev-badge sev-medium">[MEDIUM]</span> **apxUSD `pause()` is instant (role 21, 3/6 with 0 delay) — DoS vector on Fira liquidations**
  Any 3 of 6 MAINTAINER signers can freeze apxUSD transfers instantly. Good for emergency response but creates a censorship / DoS lever: a pause blocks liquidator conversion of seized apxUSD back to USDC, and blocks borrower repayments close to maturity.

  **Verify on-chain:**

  ```bash
  cast call 0xe167330E2Eac88666de253e9607C6d9ae0cA2824 'getTargetFunctionRole(address,bytes4)(uint64)' 0x98A878b1Cd98131B271883B390f68D2c90674665 0x8456cb59 --rpc-url $RPC
  # → expect: 21  # MAINTAINER_INSTANT
  cast call 0xe167330E2Eac88666de253e9607C6d9ae0cA2824 'canCall(address,address,bytes4)(bool,uint32)' 0xf9862efc1704ac05e687f66e5cd8c130e5663ce2 0x98A878b1Cd98131B271883B390f68D2c90674665 0x8456cb59 --rpc-url $RPC
  # → expect: (true, 0)
  ```

  **Key addresses:**

  - apxUSD proxy — [`0x98A878b1Cd98131B271883B390f68D2c90674665`](https://etherscan.io/address/0x98A878b1Cd98131B271883B390f68D2c90674665)
  - MAINTAINER-INSTANT Safe (3/6) — [`0xf9862efc1704ac05e687f66e5cd8c130e5663ce2`](https://etherscan.io/address/0xf9862efc1704ac05e687f66e5cd8c130e5663ce2)

- <span class="sev-badge sev-medium">[MEDIUM]</span> **AccessManager self-admin delay = 0 — manager reconfigurable in single tx**
  ADMIN can re-route function → role mappings on any target with target-admin-delay = 0 (i.e. both CR feeds) without waiting. Only hard backstop is the 7-day grant delay on role 0 itself. Any future misconfig that forgets to set a non-zero delay is exploitable instantly by ADMIN.

  **Verify on-chain:**

  ```bash
  cast call 0xe167330E2Eac88666de253e9607C6d9ae0cA2824 'getTargetAdminDelay(address)(uint32)' 0xe167330E2Eac88666de253e9607C6d9ae0cA2824 --rpc-url $RPC
  # → expect: 0
  cast call 0xe167330E2Eac88666de253e9607C6d9ae0cA2824 'getRoleAdmin(uint64)(uint64)' 0 --rpc-url $RPC
  # → expect: 0  # role 0 admins itself
  cast call 0xe167330E2Eac88666de253e9607C6d9ae0cA2824 'minSetback()(uint32)' --rpc-url $RPC
  # → expect: 432000  # 5d (only applies when *reducing* a non-zero delay)
  cast call 0xe167330E2Eac88666de253e9607C6d9ae0cA2824 'getRoleGrantDelay(uint64)(uint32)' 0 --rpc-url $RPC
  # → expect: 604800  # 7d — only real backstop
  ```

  **Key addresses:**

  - AccessManager (self) — [`0xe167330E2Eac88666de253e9607C6d9ae0cA2824`](https://etherscan.io/address/0xe167330E2Eac88666de253e9607C6d9ae0cA2824)

- <span class="sev-badge sev-low">[LOW]</span> **No Safe Modules and no Safe Guards on either Safe**
  Positive: no suspicious module surface (empty `getModulesPaginated`, zero guard storage slot on both Safes). Negative: no automated policy enforcement layer — any valid N-of-M execution goes through unconditionally.

  **Verify on-chain:**

  ```bash
  cast call 0xabdd8c8ee69e5f5180eb9352aeffc5ceead65e96 'getModulesPaginated(address,uint256)(address[],address)' 0x0000000000000000000000000000000000000001 100 --rpc-url $RPC
  # → expect: ([], 0x0000…0001)
  cast call 0xf9862efc1704ac05e687f66e5cd8c130e5663ce2 'getModulesPaginated(address,uint256)(address[],address)' 0x0000000000000000000000000000000000000001 100 --rpc-url $RPC
  # → expect: ([], 0x0000…0001)
  ```

  **Key addresses:**

  - ADMIN Safe — [`0xabdd8c8ee69e5f5180eb9352aeffc5ceead65e96`](https://etherscan.io/address/0xabdd8c8ee69e5f5180eb9352aeffc5ceead65e96)
  - MAINTAINER Safe — [`0xf9862efc1704ac05e687f66e5cd8c130e5663ce2`](https://etherscan.io/address/0xf9862efc1704ac05e687f66e5cd8c130e5663ce2)

- <span class="sev-badge sev-info">[INFO]</span> **Multisig & privileged role inventory (mandatory table)**

All role assignments and delays verified on-chain via AccessManager 0xe167330E2Eac88666de253e9607C6d9ae0cA2824 (hasRole, getAccess, getTargetFunctionRole, getTargetAdminDelay). Threshold/owners pulled directly from each Safe via getThreshold()/getOwners(). "Exec delay" is the per-member executionDelay from AccessManager.getAccess; "target admin delay" is the delay enforced on setTargetFunctionRole / setTargetAdminDelay against that target. For a scheduled-then-executed operation the effective wait is max(execDelay, targetAdminDelay).

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

Effective-control summary: an attacker with 4 of 6 ADMIN signers can (a) instantly upgrade either CR feed implementation, (b) mint unlimited apxUSD, (c) reconfigure AccessManager itself (self-admin delay 0). An attacker with 3 of 6 MAINTAINER signers can (a) pause apxUSD instantly (denial-of-service to Fira liquidators), (b) schedule apxUSD upgrade with 3-day warning, (c) unpause with 4h delay. The two Safes share 5 of 6 owners (0xb51F, 0xD6bB, 0xcFCF, 0xB98c, 0x5db4, 0xd66a overlap; maintainer differs only in the 0x0442... addition visible in role 31 grants), so "separation of duties" is nominal.


  *Evidence:* AccessManager 0xe167330E2Eac88666de253e9607C6d9ae0cA2824 — hasRole/getAccess/getTargetFunctionRole/getTargetAdminDelay; Safe 0xabdd8c8ee69e5f5180eb9352aeffc5ceead65e96 getThreshold=4, getOwners=[0xb51F...,0xD6bB...,0xcFCF...,0xB98c...,0x5db4...,0xd66a...]; Safe 0xf9862efc1704ac05e687f66e5cd8c130e5663ce2 getThreshold=3, getOwners overlap 5/6; apxUSD proxy 0x98A878b1Cd98131B271883B390f68D2c90674665 impl=0xDd71Fd67...; CR capped 0x2037a5Eb..., CR raw 0x8232... both AccessManaged

- <span class="sev-badge sev-info">[INFO]</span> **Role labels + delay posture (reference)**
  Roles by ID (from RoleLabel events): 0=ADMIN, 1=ROLE_MINT_STRAT (no holders), 2=MINTER_CONTRACT_4HR, 3=ROLE_MINT_GUARD, 4=MINTER_CONTRACT_4HR, 6=ROLE_YIELD_DISTRIBUTOR, 7=YIELD_OPERATOR, 8=ROLE_REDEEMER, 21=MAINTAINER_INSTANT, 22=MAINTAINER_SHORT, 23=MAINTAINER_MEDIUM, 24=MAINTAINER_LONG, 25=MAINTAINER_MAXIMUM, 31=GUARDIAN. Grant delays: role 0=7d, roles 1/2/4/8=3d, roles 6/7=1d, roles 21-25=7d, role 31=0. Target admin delays: apxUSD=3d, CR feeds=0d, AccessManager=0d. minSetback=5d.

  **Key addresses:**

  - AccessManager — [`0xe167330E2Eac88666de253e9607C6d9ae0cA2824`](https://etherscan.io/address/0xe167330E2Eac88666de253e9607C6d9ae0cA2824)

- <span class="sev-badge sev-info">[INFO]</span> **Docs → on-chain drift on 'separate master multisig'**
  Apyx blog post `blog.apyx.fi/minting-controls/` claims configuration authority will be transferred to a "separate master multi-sig". On-chain the two admin Safes share 5 of 6 owners, so the separation is nominal at best. docs.apyx.fi does not publish specific multisig addresses, thresholds, or timelock durations.


### Asset Controls  (score 6, confidence 0.85)

- <span class="sev-badge sev-medium">[MEDIUM]</span> **apxUSD.mint gated by MinterV0 contract (role 4) with 10M/day rate limit, 4h exec delay, and signed orders**
  apxUSD.mint(address,uint256,uint256) selector 0x156e29f6 is gated by role 4 (verified via raw call getTargetFunctionRole @ 0x6d5115bd). Role 4 is held solely by the MinterV0 mint-strategy contract at 0x2c36e1adFaA80ee0324B04cC814F5207Bb7Ba76e with a 14400s (4h) execution delay. Role 4 grant delay is 259200s (3 days). MinterV0 enforces: max 10,000,000 apxUSD per tx, rate limit 10,000,000 apxUSD per 86,400s (1 day), supply cap 300,000,000 apxUSD (live read supplyCap() = 3e26). Current totalSupply() = 1.8e26 (~180M). MinterV0 requires EIP-712 signed orders; requestMint (selector 0xeecd570d) and executeMint (0x14d39415) on MinterV0 are gated by role 2 (MINTER_CONTRACT), held by the 3-of-6 Safe 0xf9862EfC1704aC05e687f66E5cD8c130E5663cE2 with 0 exec delay. Effective minting bar: 3 of 6 Safe signers sign an EIP-712 order -> MinterV0 validates + enforces 10M/day + 10M/tx + cap -> tokens minted after 4h role-4 execution delay. Layered and capped, but the human bar is 3/6 (50%) which is at the low end for a dollar-stable with $180M live supply.
  *Evidence:* MinterV0 0x2c36e1adFaA80ee0324B04cC814F5207Bb7Ba76e (Etherscan verified 'MinterV0') | role 4 RoleGranted tx 0x75e353f8a1e894fbfc2cd4361f1e16997c48c3f3810b48b51410030308f4f5b5 block 24849935 (delay 14400) | role 2 RoleGranted tx 0x00f7dd292e9b611709879d357bceabede5c1bed180431911520eea47d508f185 block 24734715 (delay 0) | supplyCap() = 3e26, totalSupply() = 1.8e26

- <span class="sev-badge sev-medium">[MEDIUM]</span> **UUPS upgradeToAndCall held by 3-of-6 Safe with only 3-day delay**
  apxUSD is a UUPS upgradeable proxy. Selector 0x4f1ef286 (upgradeToAndCall(address,bytes)) is gated by role 24, held by Safe 0xf9862EfC1704aC05e687f66E5cD8c130E5663cE2 (3/6) with 259200s (3 day) execution delay. A 3/6 Safe (50% of signers) can push any new implementation after a 3-day wait, effectively bypassing mint caps, rate limits, deny list, or pause state. 3 days is the industry floor for defensible upgrade delay and the signer bar (3/6 = 50%) is below the typical 4/7 (57%) bar for a stablecoin with $180M live supply. ADMIN (4/6 Safe) can at any moment (0 delay) revoke or re-assign role 24, but an already-scheduled upgrade would still execute per OZ AccessManager semantics unless explicitly canceled.
  *Evidence:* TargetFunctionRoleUpdated(target=apxUSD, selector=0x4f1ef286, role=24) tx 0x79ff2a3aaf7c1eba6a18eb96b0aa2d3aed541a4cd408704bdd2c951e3560db02 block 24828844 logIndex 242 | RoleGranted(24, 0xf9862..., delay=0x3f480=259200) tx 0x01ff58d25be1119379d42ebc2d72e1039e4d374d7ad3ee823340589afbf31990 block 24792767

- <span class="sev-badge sev-medium">[MEDIUM]</span> **DenyList (blacklist) and supplyCap gated by 3-of-6 Safe with 1-day delay**
  setDenyList(address) selector 0x0de2731d and setSupplyCap(uint256) selector 0xb6a3f59a are both gated by role 23, held by Safe 0xf9862EfC1704aC05e687f66E5cD8c130E5663cE2 (3/6) with 86400s (1 day) execution delay. apxUSD IS a blacklist token: individual addresses can be denied sends/receives. For Fira as a collateral holder this matters indirectly — the vault/market could in principle be placed on the deny list, blocking apxUSD flows. 3/6 + 1-day is weak for blacklist power: 3 colluding signers can blacklist the Fira market or LPs with 24h notice. supplyCap increase is similarly gated (could raise from 300M to unlimited with 24h notice, though MinterV0's 10M/day drip still caps velocity). Fira holds PT-apxUSD not apxUSD at rest, so direct exposure is limited, but the Apyx CR feed path and Pendle TWAP both rely on an un-censored apxUSD spot market.
  *Evidence:* TargetFunctionRoleUpdated logIndex 240 (setSupplyCap -> role 0x17=23) and logIndex 241 (setDenyList -> role 0x17=23) tx 0x79ff2a3aaf7c1eba6a18eb96b0aa2d3aed541a4cd408704bdd2c951e3560db02 block 24828844 | RoleGranted(23, 0xf9862, delay=0x15180=86400) tx 0x01ff58d25be1119379d42ebc2d72e1039e4d374d7ad3ee823340589afbf31990 block 24792767

- <span class="sev-badge sev-low">[LOW]</span> **Pause held by 3-of-6 Safe with ZERO execution delay; unpause 4h delay**
  pause() selector 0x8456cb59 is gated by role 21, held by Safe 0xf9862... (3/6) with 0 execution delay — 3 signers can freeze all apxUSD transfers immediately. unpause() selector 0x3f4ba83a is gated by role 22 (same 3/6 Safe) with 14400s (4h) execution delay. During a paused window, any Fira flow requiring apxUSD movement reverts. Fira does not hold apxUSD directly (holds PT-apxUSD) but arbitrage and Pendle TWAP updates depend on apxUSD being transferable. Pause-with-no-delay is standard for stablecoin incident response but also provides a censorship vector.
  *Evidence:* TargetFunctionRoleUpdated(apxUSD, 0x8456cb59, 21) block 24828844 logIndex 238 | TargetFunctionRoleUpdated(apxUSD, 0x3f4ba83a, 22) logIndex 239 | RoleGranted(21, 0xf9862, delay=0) and RoleGranted(22, 0xf9862, delay=14400) tx 0x01ff58d25be1119379d42ebc2d72e1039e4d374d7ad3ee823340589afbf31990

- <span class="sev-badge sev-low">[LOW]</span> **setCCIPAdmin and setAuthority gated by 3-of-6 Safe with 7-day delay**
  setCCIPAdmin(address) selector 0xa8fa343c and setAuthority(address) selector 0x7a9e5e4b are both gated by role 25, held by Safe 0xf9862... (3/6) with 604800s (7 day) execution delay. setAuthority is the most sensitive function — it can replace the entire AccessManager; 7-day delay is appropriate. setCCIPAdmin controls the CCIP token admin (Chainlink cross-chain adapter) — 7-day delay also reasonable. Signer threshold is still 3/6 across all operational roles.
  *Evidence:* TargetFunctionRoleUpdated(apxUSD, 0xa8fa343c, 25) and (apxUSD, 0x7a9e5e4b, 25) block 24828844 logIndex 243/244 | RoleGranted(25, 0xf9862, delay=604800) block 24792767

- <span class="sev-badge sev-info">[INFO]</span> **AccessManager ADMIN_ROLE (role 0) currently held by 4-of-6 Safe, not an EOA**
  Verified live via hasRole(0, 0xabdd8c8ee69e5f5180eb9352aeffc5ceead65e96) => (true, 0). The Safe at 0xabdd8c8ee69e5f5180eb9352aeffc5ceead65e96 has threshold 4 and 6 signers (verified via getThreshold()/getOwners()). ADMIN was transferred from the genesis deployer EOA 0x0442cC5BBfBc4B7Dc3A14F9766c21C82b45f0024 (confirmed hasRole(0, EOA) => (false, 0)) and also from the 3/6 ops Safe 0xf9862EfC1704aC05e687f66E5cD8c130E5663cE2 (confirmed hasRole(0, f9862) => (false, 0)). Admin ownership move to the 4/6 Safe occurred at block 24721241 (timestamp 1772908091 ~ 2026-03-04). ADMIN has 0 execution delay but role 0 grant delay is 7 days, so adding a new admin takes 7 days.
  *Evidence:* AccessManager 0xe167330E2Eac88666de253e9607C6d9ae0cA2824 | Safe 0xabdd8c8ee69e5f5180eb9352aeffc5ceead65e96 (4/6) | grant tx 0x8b6b1a3a2e7900bd0b5f1d49a1d6fe840cedb4b2af26da7147eb52ca3e5af417 block 24721241

- <span class="sev-badge sev-info">[INFO]</span> **Role taxonomy: labeled vs unlabeled roles**
  AccessManager RoleLabel events emitted at deployment (block 24481041-24481052) cover: role 1=ROLE_MINT_STRAT, role 2=ROLE_MINTER (MINTER_CONTRACT), role 3=ROLE_MINT_GUARD, role 6=ROLE_YIELD_DISTRIBUTOR, role 7=ROLE_YIELD_OPERATOR, role 8=ROLE_REDEEMER. Roles 4, 21-25 that currently gate apxUSD's critical functions were NOT emitted with RoleLabel events — they were introduced in later setTargetFunctionRole batches (block 24734715 for MinterV0 wiring, 24828844 for apxUSD ops, 24849935 for the mint-role swap from role 1 to role 4). Unlabeled roles are a documentation gap: UIs, monitoring, and third-party risk systems that rely on role labels will miss the real gating. Role 31 was also assigned to MinterV0.cancelMint in a later batch.
  *Evidence:* RoleLabel events (topic 0x1256f5b5ecb89caec12db449738f2fbcd1ba5806cf38f35413f4e5c15bf6a450) block 24481041-24481052 on AccessManager 0xe167330E2Eac88666de253e9607C6d9ae0cA2824

- <span class="sev-badge sev-info">[INFO]</span> **Both Safes share the same 6 owner keys — effective bar is 3-of-6 for all ops**
  The 4/6 ADMIN Safe 0xabdd8c8ee69e5f5180eb9352aeffc5ceead65e96 and the 3/6 ops Safe 0xf9862EfC1704aC05e687f66E5cD8c130E5663cE2 share IDENTICAL owner sets: [0xb51F89DEA7Df709cEbb4809B40c6431361e61d0d, 0x5db416BcFc1a8b5b921f55C1E078d1F39194e99F, 0xD6bB3f9718D4f30ed2851c713275dEf7529D1411, 0xcFCF3C9Ed3d97DB54c99BDd197E59952a0973f6e, 0xB98cD8C868cf00cEA934977dBE4AC090E808fb87, 0xd66a0Fc924fAb7476D35aFe5941856ef76BA0839]. Effective governance redundancy is the LOWER threshold (3/6), not the higher one — 3 colluding keys can: (a) trigger mints via MinterV0 (subject to 10M/day cap), (b) pause immediately, (c) deny-list or raise supplyCap with 1-day notice, (d) push an upgrade in 3 days. The 4/6 ADMIN only controls role management (grant/revoke/target wiring). Key-concentration risk: compromise of 3 of these 6 keys (phishing, device compromise, coercion) enables malicious upgrade in 3 days.
  *Evidence:* getOwners() on 0xabdd... and 0xf9862... both return same 6-address array | getThreshold() returns 4 and 3 respectively

- <span class="sev-badge sev-info">[INFO]</span> **Fira exposure is indirect — PT-apxUSD not apxUSD**
  Fira's collateral is PT-apxUSD (Pendle Principal Token expiring 2026-06-18), not apxUSD at rest. PT redeems 1:1 to apxUSD at expiry. Mint authority + pause/deny list primarily affect apxUSD holders (Fira does not hold apxUSD directly). Two indirect exposures: (1) the Apyx CR capped feed 0x2037a5eb67aa9b2fbf50042b724d8c4db80f23b4 feeds the Morpho oracle 0x4DFceF82eaEE9eA817bEb1279336F7D0Ebf2b685 that drives Fira liquidations — its authority is the same AccessManager 0xe167330E2Eac88666de253e9607C6d9ae0cA2824, so the 3/6 Safe's upgrade path also threatens the CR feed (needs a separate verification of which role gates the CR feed's upgrade, not covered in this pass); (2) Pendle TWAP oracle depends on PT trading, which depends on apxUSD being usable. Fira should treat the 3/6-Safe upgrade path as the dominant governance risk vector, not the mint cap (which is reasonably constrained by MinterV0 + 10M/day + 4h exec delay + 300M hard cap).
  *Evidence:* docs/research/pt-apxusd-market.md | Morpho oracle 0x4DFceF82eaEE9eA817bEb1279336F7D0Ebf2b685 | Apyx CR capped feed 0x2037a5eb67aa9b2fbf50042b724d8c4db80f23b4 (authority 0xe167330E2Eac88666de253e9607C6d9ae0cA2824)


### Code Quality  (score 7, confidence 0.65)

- <span class="sev-badge sev-medium">[MEDIUM]</span> **No public bug bounty program**
  No Immunefi / HackerOne / security@ contact surfaced in docs or README. Moderate score reduction — live stablecoin infrastructure of this size typically runs an Immunefi program. Not a red flag.

- <span class="sev-badge sev-info">[INFO]</span> **All 5 Apyx core contracts verified on Etherscan (Exact Match)**
  apxUSD (0x98A8...4665), CR capped proxy (0x2037...f23b4) + impl (0xbcc4...d682 ApyxRedemptionOracle), CR raw proxy (0x8232...FD305) + impl (0x0e1e...c49c ApyxCollateralRatioOracle), AccessManager (0xe167...2824). Solc 0.8.30, optimizer 200, Prague EVM. No FLAG_UNVERIFIED_CORE_CONTRACT.
  *Evidence:* https://etherscan.io/address/0x98A878b1Cd98131B271883B390f68D2c90674665#code

- <span class="sev-badge sev-info">[INFO]</span> **Three audits listed at docs.apyx.fi/resources/audits — Quantstamp, Certora, Zellic**
  Quantstamp (Feb 2026), Certora (Mar 2026), Zellic (Mar 2026). All three are top-tier firms (Certora = formal verification). Meets the 2+ audit bar. Individual PDFs not publicly retrievable at assessment time — findings/remediation status cannot be independently validated, but the audits exist.
  *Evidence:* https://docs.apyx.fi/resources/audits

- <span class="sev-badge sev-info">[INFO]</span> **Active repo with Foundry + Slither + invariant tests**
  apyx-labs/evm-contracts: Foundry + Soldeer, Slither static analysis in CI, invariant/ test subdir (runs=256 depth=1024). OpenZeppelin Contracts v5.5.0 (current). Modern, standard patterns.
  *Evidence:* https://github.com/apyx-labs/evm-contracts

- <span class="sev-badge sev-info">[INFO]</span> **No known incidents**
  No exploits or advisories found via Immunefi, Rekt News, GitHub Security Advisories for Apyx.

- <span class="sev-badge sev-info">[INFO]</span> **Pendle PT layer uses standard Pendle V2 code**
  PT, SY, YT, Market contracts are standard Pendle V2 deployments (reused well-audited code). Engineering-risk concentration is on the apxUSD collateral layer.


### Cross-Chain Surface  (score 8, confidence 0.85)

- <span class="sev-badge sev-info">[INFO]</span> **apxUSD underlying token (0x98a878b1cd98131b271883b390f68d2c90674665 on Ethereum) is curren…**

- <span class="sev-badge sev-info">[INFO]</span> **PT-apxUSD itself (0x92a6a01b07984de46c24e8eba248449beb8b1dcb) is a Pendle PT and lives on …**

- <span class="sev-badge sev-info">[INFO]</span> **Cross-chain bridging is done via Chainlink CCIP (not LayerZero, Wormhole, or a custom brid…**

- <span class="sev-badge sev-info">[INFO]</span> **CCIP has RMN (Risk Management Network) enabled by default on all lanes — RMN is a secondar…**

- <span class="sev-badge sev-info">[INFO]</span> **No LayerZero OFT deployment, no custom multisig-admin bridge, no Wormhole, no Axelar — onl…**

- <span class="sev-badge sev-info">[INFO]</span> **Solana expansion publicly announced as 'coming soon' (not yet live)…**

- <span class="sev-badge sev-info">[INFO]</span> **No deployments on Polygon, Arbitrum, Optimism, Avalanche, or any other EVM chain outside E…**

- <span class="sev-badge sev-info">[INFO]</span> **Base-side apxUSD token pool + CCIP token admin registry configuration not inspected on-cha…**

- <span class="sev-badge sev-info">[INFO]</span> **Rubric placement: 2 chains via canonical bridge with RMN sits between '10' (single chain) …**


### Team Transparency  (score 8, confidence 0.75)

- <span class="sev-badge sev-info">[INFO]</span> **Team is fully doxxed — 4 named leaders, all with verifiable LinkedIn + press trail**
  Joseph Onorati (CEO; ex-Kraken CSO 2016-2024; CEO of NASDAQ DFDV), Dan Kang (ex-Kraken Head of Strategy; CSO DFDV), Dawson Reid (9y Kraken SWE), Pete Humiston (ex-Jefferies; CMO DFDV). Cross-verified via globenewswire, Nasdaq, Blockworks, and DFDV S-3 filings. No pseudonymous core-team members.
  *Evidence:* https://blockworks.com/speaker/joseph-onorati

- <span class="sev-badge sev-info">[INFO]</span> **Primary backer = NASDAQ-listed DFDV (first institutional capital, 2026-02-26)**
  No tier-1 crypto VC (a16z, Paradigm, Pantera, Polychain, Multicoin) identified in public sources. Funding base is narrow but reputable rather than obscure. "First institutional capital" phrasing leaves room for undisclosed smaller investors.
  *Evidence:* https://www.globenewswire.com/news-release/2026/02/26/3245596/0/en/DeFi-Development-Corp-Announces-Investment-in-Apyx.html

- <span class="sev-badge sev-info">[INFO]</span> **Onorati was interim CEO of CaVirtEx during its 2015 hack and wind-down**
  Canada's first Bitcoin exchange; suffered a material breach Feb 2015; assets acquired by Coinsetter (~$2M), later rolled into Kraken. Public sources frame this as a standard wind-down — no allegation of personal misconduct — but reviewers should note the prior-exchange-hack association.
  *Evidence:* https://bitcoinmagazine.com/business/coinsetter-sets-sights-canadian-exchange-cavirtex-1428617314

- <span class="sev-badge sev-info">[INFO]</span> **No rugpulls, scams, insider drama, or sanctioned-jurisdiction ties for any named member**

- <span class="sev-badge sev-info">[INFO]</span> **'Apyx Labs' corporate entity not publicly disclosed; likely Delaware (unverified)**
  docs.apyx.fi does not publish a legal-entity page. Searches for "Apyx" return Apyx Medical Corporation (unrelated NASDAQ medical-device company). Team is US-based (DFDV HQ Boca Raton, FL); no Cayman / BVI / Panama footprint observed.

- <span class="sev-badge sev-info">[INFO]</span> **GitHub org apyx-labs has no public members; engineering attribution relies on bios, not commits**
  Minor opacity — typical for stealth-launch crypto orgs but worth noting given the team is otherwise doxxed.

- <span class="sev-badge sev-info">[INFO]</span> **Multi-sig signer identities not publicly disclosed**
  Apyx blog describes manual minting with multi-sig + hard limits, but does not name the signers. Cannot independently confirm signers == the 4 public leaders — mild concern, not a red flag.
  *Evidence:* https://blog.apyx.fi/minting-controls/

- <span class="sev-badge sev-info">[INFO]</span> **FLAG_ANON_TEAM_WITH_PRIVILEGE not triggered — team is public, not pseudonymous**


### Liquidity Depth  (score 5, confidence 0.85)

- <span class="sev-badge sev-info">[INFO]</span> **On-chain discovery: PT 0x92a6a01b07984de46c24e8eba248449beb8b1dcb -> SY 0x4f116eE5BCD227d1…**

- <span class="sev-badge sev-info">[INFO]</span> **apxUSD total supply 180M (18 dec)…**

- <span class="sev-badge sev-info">[INFO]</span> **Only two meaningful apxUSD/USDC pools on mainnet: Curve StableSwap-NG 0xe1b96555bbeca40e58…**

- <span class="sev-badge sev-info">[INFO]</span> **Curve slippage ladder apxUSD -> USDC (verified via get_dy on-chain): $100k -> 0…**

- <span class="sev-badge sev-info">[INFO]</span> **Uniswap V4 slippage ladder (verified via V4 Quoter 0x52f0e24d1c21c8a0cb1e5a5dd6198556bd9e1…**

- <span class="sev-badge sev-info">[INFO]</span> **Aggregator routing (Paraswap, Odos): BOTH route 100% through Curve for all sizes tested ($…**

- <span class="sev-badge sev-info">[INFO]</span> **COMBINED practical depth (router using V4 + Curve manually split): at 2% slippage, approxi…**

- <span class="sev-badge sev-info">[INFO]</span> **PT-apxUSD -> USDC routing: aggregators DO NOT support PT-apxUSD as input…**

- <span class="sev-badge sev-info">[INFO]</span> **Pendle AMM state (via routerstatic + on-chain): PT balance in market 2…**

- <span class="sev-badge sev-info">[INFO]</span> **Post-expiry path (2026-06-18+): PT redeems 1:1 via YT/PT burn through YieldContractFactory…**

- <span class="sev-badge sev-info">[INFO]</span> **Liquidity concentration risk: two pools totaling ~$34M TVL, both on single chain, apxUSD i…**

- <span class="sev-badge sev-info">[INFO]</span> **Fira-specific liquidation sizing: at 88% LLTV and $1-3M position cap, a full liquidation o…**

- <span class="sev-badge sev-info">[INFO]</span> **Scoring: $6M at 2% single-pool (Curve) + $3M at ~0% single-pool (V4) + aggregator routing …**


### Controversy  (score 5, confidence 0.75)

- <span class="sev-badge sev-high">[HIGH]</span> **Structural similarity to Nov 2025 xUSD/Stream Finance collapse**
  apxUSD occupies the same structural niche as Stream Finance's xUSD (collapsed Nov 4 2025): yield-backed stablecoin pushed as Pendle-PT'd collateral into Morpho-curated looped borrow strategies. Stream lost $93M on an 'external fund manager'; xUSD depegged 87-93% and cascaded to deUSD (-98%) with ~$285M+ bad debt across Morpho/Euler/Gearbox/Silo. Treated as a score-influencing pattern concern, not a red flag. Key differences vs Stream: Apyx custody is BitGo (qualified custodian) with PCAOB-registered monthly attestations, and backing is publicly-listed equity dividends rather than an off-chain fund-manager strategy. Mitigants exist, but the composability pattern (stablecoin → Pendle PT → Morpho loop) has demonstrably failed recently under stress.
  *Evidence:* https://blockeden.xyz/blog/2025/11/08/m-defi-contagion/

- <span class="sev-badge sev-medium">[MEDIUM]</span> **CR oracle feed stale 25-30 days; no on-chain heartbeat**
  Both CR feeds (capped 0x2037... and raw 0x8232...) show updatedAt ~25-30 days old. Apyx response (2026-04-16): 'updated as needed atm, will be daily in the future' — not enforced on-chain, no heartbeat, no fallback. Score-affecting concern; only escalates to red-flag severity in combination with governance-security's finding that the same feeds can be instantly re-implemented.
  *Evidence:* https://etherscan.io/address/0x2037a5eb67aa9b2fbf50042b724d8c4db80f23b4#readProxyContract

- <span class="sev-badge sev-info">[INFO]</span> **Where does yield come from?**
  apxUSD is the first 'Dividend-Backed Stablecoin' — backed by preferred equity of BTC treasury companies: STRC (Strategy / MSTR, ~11.5% annual dividend) and SATA (Strive / ASST, ~12.75-13%). Yield flow: dividend cash from issuers → BitGo qualified custody → Apyx operator keys → MinterV0 contract mints apxUSD/ApyUSD → on-chain CR oracle reflects NAV. Reserve attestations are offchain, monthly, PCAOB-registered (not real-time). Commentators have drawn Terra-Luna parallels on STRC's reflexivity (BTC crash → STRC dividend up → Strategy raises more debt / sells BTC → BTC down). **Informational only.** Economic viability of the yield source is Markov Labs' responsibility and is not scored in this assessment.
  *Evidence:* https://docs.apyx.fi/product-overview/apxusd-overview ; https://cryptobriefing.com/apyx-strc-acquisition-largest-holding/

- <span class="sev-badge sev-info">[INFO]</span> **DFDV sponsor is the former Janover Inc. — $300M valuation on $3M raise**
  Apyx's lead institutional backer is DeFi Development Corp (NASDAQ: DFDV), the former Janover Inc. which pivoted to Solana treasury in April 2025 after Blake Janover sold control for $4M. DFDV is <12 months into its crypto identity. Reported $300M valuation on $3M raise comes from this insider network rather than tier-1 crypto VCs. Noted for transparency; no score impact.
  *Evidence:* https://www.globenewswire.com/news-release/2026/02/26/3245596/0/en/DeFi-Development-Corp-Announces-Investment-in-Apyx.html

- <span class="sev-badge sev-info">[INFO]</span> **Legitimate team, no tainted flow, no regulatory action**
  Founder Joseph Onorati (ex-Kraken CSO 8y, CEO DFDV) and broader leadership have verifiable histories. No rugpull patterns, sanctioned-jurisdiction connections, or on-chain tainted flow surfaced. No SEC/CFTC/FinCEN/OFAC actions.

- <span class="sev-badge sev-info">[INFO]</span> **No recent unrecovered exploit on Apyx or direct dependencies**
  FLAG_RECENT_UNRECOVERED_EXPLOIT not triggered. Pendle core unaffected by 2024 Penpie incident. Chainlink feeds clean. No Apyx-side incidents.


## Inputs used for this assessment

- **RPC chain:** unspecified (URL redacted)
- **Docs:** https://apyx.fi/, https://docs.apyx.fi/, https://app.pendle.finance/trade/markets/0x50DCE085af29CABa28f7308beA57C4043757b491, https://app.morpho.org/ethereum/market/0xed05fcc2893b78b3fa468d21b6e4d2925e7f2c64eb1f16279757c43f87502a99/pt-apxusd-18jun2026-usdc
- **Repos:** https://github.com/apyx-labs
- **Controversy seeds:** "(none)"
- **Asset address:** `0x92a6a01b07984de46c24e8eba248449beb8b1dcb`
- **Market type:** fixed
- **Assessment date:** 2026-04-21
