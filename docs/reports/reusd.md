---
title: reUSD
score: 3.0
verdict: "technically exists, regrettably"
redFlags: ['FLAG_UNSAFE_MINT_AUTHORITY', 'FLAG_NO_TIMELOCK_ON_CRITICAL_OPS', 'FLAG_UNSAFE_PROXY_ADMIN', 'FLAG_UNSAFE_MINT_AUTHORITY', 'FLAG_UNSAFE_MINT_AUTHORITY', 'FLAG_BRIDGE_WEAK_DVN', 'CROSS_CHAIN_SURFACE_CONCERN', 'CONTROVERSY_CONCERN']
date: 2026-05-01
---

<div class="score-banner">
  <div class="speedometer"><svg class="risk-speedometer" width="520" height="360" viewBox="0 0 520 360" xmlns="http://www.w3.org/2000/svg" role="img" aria-label="Asset risk score 3.0 of 10">
  <defs>
    <filter id="needleShadow" x="-30%" y="-30%" width="160%" height="160%">
      <feGaussianBlur stdDeviation="2.5"/>
    </filter>
  </defs>

  <!-- Outer dossier frame: double rule -->
  <rect x="8" y="8" width="504" height="344" fill="none" stroke="currentColor" stroke-width="1" opacity="0.7"/>
  <rect x="14" y="14" width="492" height="332" fill="none" stroke="currentColor" stroke-width="0.5" opacity="0.55"/>

  <!-- Top classification strip -->
  <line x1="14" y1="52" x2="506" y2="52" stroke="currentColor" stroke-width="1" opacity="0.7"/>
  <text x="28" y="38" font-size="11" font-weight="600" letter-spacing="2.5" fill="currentColor" opacity="0.85">ASSET / REUSD</text>
  <text x="492" y="38" text-anchor="end" font-size="11" font-weight="600" letter-spacing="2" fill="currentColor" opacity="0.85">DOS-2528</text>

  <!-- RISK SCORE label -->
  <text x="260" y="80" text-anchor="middle" font-size="10" font-weight="500" letter-spacing="6" fill="currentColor" opacity="0.65">— RISK SCORE —</text>

  <!-- Arc (background + zones). Center 260, 260. Radius 160. -->
  <path d="M 100 260 A 160 160 0 0 1 420 260" stroke="currentColor" stroke-width="26" fill="none" stroke-linecap="butt" opacity="0.12"/>
  <path d="M 100 260 A 160 160 0 0 1 209 113" stroke="#c62828" stroke-width="22" fill="none" stroke-linecap="butt"/>
  <path d="M 209 113 A 160 160 0 0 1 311 113" stroke="#b45309" stroke-width="22" fill="none" stroke-linecap="butt"/>
  <path d="M 311 113 A 160 160 0 0 1 420 260" stroke="#4d6b1f" stroke-width="22" fill="none" stroke-linecap="butt"/>

  <line x1="118.0" y1="260.0" x2="112.0" y2="260.0" stroke="currentColor" stroke-width="1.8" opacity="0.85"/><line x1="119.7" y1="237.8" x2="109.9" y2="236.2" stroke="currentColor" stroke-width="1" opacity="0.45"/><line x1="124.9" y1="216.1" x2="119.2" y2="214.3" stroke="currentColor" stroke-width="1.8" opacity="0.85"/><line x1="133.5" y1="195.5" x2="124.6" y2="191.0" stroke="currentColor" stroke-width="1" opacity="0.45"/><line x1="145.1" y1="176.5" x2="140.3" y2="173.0" stroke="currentColor" stroke-width="1.8" opacity="0.85"/><line x1="159.6" y1="159.6" x2="152.5" y2="152.5" stroke="currentColor" stroke-width="1" opacity="0.45"/><line x1="176.5" y1="145.1" x2="173.0" y2="140.3" stroke="currentColor" stroke-width="1.8" opacity="0.85"/><line x1="195.5" y1="133.5" x2="191.0" y2="124.6" stroke="currentColor" stroke-width="1" opacity="0.45"/><line x1="216.1" y1="124.9" x2="214.3" y2="119.2" stroke="currentColor" stroke-width="1.8" opacity="0.85"/><line x1="237.8" y1="119.7" x2="236.2" y2="109.9" stroke="currentColor" stroke-width="1" opacity="0.45"/><line x1="260.0" y1="118.0" x2="260.0" y2="112.0" stroke="currentColor" stroke-width="1.8" opacity="0.85"/><line x1="282.2" y1="119.7" x2="283.8" y2="109.9" stroke="currentColor" stroke-width="1" opacity="0.45"/><line x1="303.9" y1="124.9" x2="305.7" y2="119.2" stroke="currentColor" stroke-width="1.8" opacity="0.85"/><line x1="324.5" y1="133.5" x2="329.0" y2="124.6" stroke="currentColor" stroke-width="1" opacity="0.45"/><line x1="343.5" y1="145.1" x2="347.0" y2="140.3" stroke="currentColor" stroke-width="1.8" opacity="0.85"/><line x1="360.4" y1="159.6" x2="367.5" y2="152.5" stroke="currentColor" stroke-width="1" opacity="0.45"/><line x1="374.9" y1="176.5" x2="379.7" y2="173.0" stroke="currentColor" stroke-width="1.8" opacity="0.85"/><line x1="386.5" y1="195.5" x2="395.4" y2="191.0" stroke="currentColor" stroke-width="1" opacity="0.45"/><line x1="395.1" y1="216.1" x2="400.8" y2="214.3" stroke="currentColor" stroke-width="1.8" opacity="0.85"/><line x1="400.3" y1="237.8" x2="410.1" y2="236.2" stroke="currentColor" stroke-width="1" opacity="0.45"/><line x1="402.0" y1="260.0" x2="408.0" y2="260.0" stroke="currentColor" stroke-width="1.8" opacity="0.85"/>

  <!-- Tick labels 0, 10 -->
  <text x="80" y="282" text-anchor="middle" font-size="12" font-weight="700" fill="currentColor" opacity="0.85">0</text>
  <text x="440" y="282" text-anchor="middle" font-size="12" font-weight="700" fill="currentColor" opacity="0.85">10</text>

  <!-- Needle: shadow + solid bar + hub -->
  <line x1="260" y1="260" x2="260" y2="120" stroke="currentColor" stroke-opacity="0.3" stroke-width="7" stroke-linecap="round" filter="url(#needleShadow)" transform="rotate(-36.0, 260, 260)"/>
  <line x1="260" y1="260" x2="260" y2="120" stroke="currentColor" stroke-width="4" stroke-linecap="round" transform="rotate(-36.0, 260, 260)"/>
  <circle cx="260" cy="260" r="11" fill="currentColor"/>
  <circle cx="260" cy="260" r="4"  fill="var(--dossier-cream, #f4ede0)"/>

  <!-- Big score numeral -->
  <text x="260" y="230" text-anchor="middle" font-size="58" font-weight="700" letter-spacing="-1" fill="currentColor">3.0</text>
  <text x="260" y="248" text-anchor="middle" font-size="10" font-weight="500" letter-spacing="5" fill="currentColor" opacity="0.7">/ 10</text>

  <!-- Bottom classification strip -->
  <line x1="14" y1="300" x2="506" y2="300" stroke="currentColor" stroke-width="1" opacity="0.7"/>
  <text x="260" y="322" text-anchor="middle" font-size="9" font-weight="500" letter-spacing="4" fill="currentColor" opacity="0.6">— CLASSIFICATION —</text>
  <text x="260" y="342" text-anchor="middle" font-size="13" font-weight="700" letter-spacing="3" fill="currentColor">TECHNICALLY EXISTS, REGRETTABLY</text>
</svg></div>
</div>

<p class="verdict-tagline"><em>technically exists, regrettably</em></p>

## Judge's verdict

### ✅ What looks good

- Doxxed leadership: CEO [Karn Saroya](https://www.linkedin.com/in/saroya) (MIT MFin, ex-Cover, ex-Stylekick→Shopify) + VP Eng [Cliff White](https://www.linkedin.com/in/cliffawhite/) (9-yr Kiteworks CTO).
- Tier-1 backers including [Electric Capital Series A](https://beinsure.com/news/platform-re-tokenized-reinsurance-fund/) and reinsurance-industry capital (SiriusPoint, Exor) on top of the [$14M seed](https://www.theblock.co/post/173386/karn-saroya-raises-14-million-for-insurance-protocol-re-as-insurtech-platform-cover-is-wound-down).
- Real regulatory wrapper: Cayman-licensed CoverRe reinsurer + §114 trust accounts + Chainlink-attested daily reserves per [docs.re.xyz](https://docs.re.xyz/getting-started-with-re/introduction-to-the-re-protocol).
- Two paid audits — [Hacken Sep 2024](https://hacken.io/audits/re-protocol/sca-re-re-defi-aug2024/) (0C/0H) and [Certora Sep 2025](https://www.certora.com/reports/re-core) (1C/4H, all resolved); contracts verified on Etherscan ([impl `0xb5276c436f65913cd5332de745d04fedeb4a21d4`](https://etherscan.io/address/0xb5276c436f65913cd5332de745d04fedeb4a21d4#code)).
- LayerZero ULN currently configured 2-of-2 required DVNs ([LZ Labs `0x589dEDbD617e0CBcB916A9223F4d1300c294236b`](https://etherscan.io/address/0x589dEDbD617e0CBcB916A9223F4d1300c294236b) + [Nethermind `0xa59ba433ac34d2927232918ef5b2eaafcf130ba5`](https://etherscan.io/address/0xa59ba433ac34d2927232918ef5b2eaafcf130ba5)) — sound in isolation.

### ⚠ What worries me

- CRITICAL: a single EOA [`0x6C15B25E9750Dccb698C1a4023f34015bFe57649`](https://etherscan.io/address/0x6C15B25E9750Dccb698C1a4023f34015bFe57649) (nonce 3060+, hot key) owns [ShareTokenMinterBurner `0x0dfb42aa18ceed719617cd554304f6ca412a6b18`](https://etherscan.io/address/0x0dfb42aa18ceed719617cd554304f6ca412a6b18) which holds unbounded MINTER_ROLE on [reUSD](https://etherscan.io/address/0x5086bf358635B81D8C47C66d1C8b9E567Db70c72) — owner cannot mint directly, but `setAdapter(*)` can repoint mint authority to any address it deploys, with no msig, no timelock, no cap. Effective trust floor: one private key.
- Same EOA also owns the [LayerZero OFTAdapter `0x2BB4046022B9161f3F84Ad8E35cac1d5946e0e85`](https://etherscan.io/address/0x2BB4046022B9161f3F84Ad8E35cac1d5946e0e85) AND is the LZ V2 delegate — can rewrite peers and DVN config across all [7 chains](https://docs.re.xyz) unilaterally, collapsing the 2-of-2 DVN guarantee.
- The 48h timelock is cosmetic: 3-of-5 Safe [`0x8eec10616802ef639ca55c98ac856553fadefbad`](https://etherscan.io/address/0x8eec10616802ef639ca55c98ac856553fadefbad) holds DEFAULT_ADMIN_ROLE directly on reUSD and can self-grant UPGRADER/MINTER in one tx, bypassing [TimelockController `0x69ddea332723cf5407151aaf68b9b076557fca93`](https://etherscan.io/address/0x69ddea332723cf5407151aaf68b9b076557fca93).
- Architecture pattern-matches the [Stream Finance/xUSD November 2025 collapse](https://thedefiant.io/news/defi/how-stream-finance-s-collapse-exposed-defi-s-looping-yield-bubble) — Pendle PT + Morpho/Euler looping + yield-stable — which cascaded $93M loss into [$285M contagion](https://blockeden.xyz/blog/2025/11/08/m-defi-contagion/).
- Liquidity is anaemic for a collateral asset: only [Curve reUSD/USDC `0xf74c91b36c26543a0aa820bef407a577e5498bf0`](https://etherscan.io/address/0xf74c91b36c26543a0aa820bef407a577e5498bf0) at ~$450K TVL caps at ~$221K USDC out, and [SY-reUSD `0x9487Bd5A3b16Ecb5F3184453E3ee75B800141648`](https://etherscan.io/address/0x9487Bd5A3b16Ecb5F3184453E3ee75B800141648) reverts on USDC redeem — liquidator must hand-roll PT→SY→reUSD→USDC.
- Pendle PT pool [`0xf5929a1c332ceab7918a4593a43db2b9ac20095f`](https://etherscan.io/address/0xf5929a1c332ceab7918a4593a43db2b9ac20095f) has only ~$1.07M PT; >$500K liquidations consume most of the AMM. No Uniswap V2/V3 fallback.

### 🎯 Verdict

**Verdict:** hard no

Rationale one-liner: One hot EOA controls unlimited mint on reUSD AND the LayerZero adapter across 7 chains, the 48h timelock is bypassable by a 3/5 Safe, and the architecture replicates the Stream/xUSD failure mode atop ~$450K of direct USDC exit depth — collateral integrity is one phished key away from zero.


## ⚠ Red flags raised

- **[FLAG_UNSAFE_MINT_AUTHORITY]** (governance-security) — Minter contract 0x0dfb42aa18ceed719617cd554304f6ca412a6b18 holds reUSD MINTER_ROLE; its owner() is a single EOA 0x6c15b25e9750dccb698c1a4023f34015bfe57649 that can call setAdapter() to route unlimited mint to any address with no msig and no timelock.
- **[FLAG_NO_TIMELOCK_ON_CRITICAL_OPS]** (governance-security) — 3-of-5 Safe 0x8eec10616802ef639ca55c98ac856553fadefbad holds DEFAULT_ADMIN_ROLE on reUSD with zero delay; can grant MINTER/UPGRADER/burner roles instantly, bypassing the 48h timelock.
- **[FLAG_UNSAFE_PROXY_ADMIN]** (governance-security) — reUSD upgrade path: timelock 0x69ddea332723cf5407151aaf68b9b076557fca93 (48h) is sole UPGRADER, but its only proposer/canceller is a 3/5 Safe which is also DEFAULT_ADMIN and can self-grant UPGRADER without delay.
- **[FLAG_UNSAFE_MINT_AUTHORITY]** (asset-controls) — ShareTokenMinterBurner 0x0dfb42aa18ceed719617cd554304f6ca412a6b18 holds MINTER_ROLE on reUSD and is Ownable-owned by EOA 0x6C15B25E9750Dccb698C1a4023f34015bFe57649 (Re Deployer). Owner can set the adapter to any address, granting that address unbounded mint authority on reUSD without timelock or msig.
- **[FLAG_UNSAFE_MINT_AUTHORITY]** (cross-chain-surface) — reUSD LayerZero OFTAdapter at 0x2BB4046022B9161f3F84Ad8E35cac1d5946e0e85 is owned by EOA 0x6c15b25e9750dccb698c1a4023f34015bfe57649. That single key can call setPeer/setDelegate and indirectly route unlimited mints across all 7 chains. Compromise of one EOA = unlimited reUSD mint everywhere.
- **[FLAG_BRIDGE_WEAK_DVN]** (cross-chain-surface) — The same EOA is registered as the LayerZero V2 delegate for the adapter, so it can rewrite DVN/ULN config unilaterally — collapsing the current 2-of-2 DVN requirement to 1-of-1 or to attacker-chosen DVNs without any timelock or multisig.
- **[CROSS_CHAIN_SURFACE_CONCERN]** (cross-chain-surface) — reUSD lives on 7 chains (Ethereum, Arbitrum, Base, Avalanche, BNB, Katana, Ink) and per-chain MINTER_ROLE is held by ShareTokenMinterBurner contracts whose adapter pointer can be repointed by their own EOA owner — the bridge has no timelock anywhere.
- **[CONTROVERSY_CONCERN]** (controversy) — reUSD's design (Pendle PT, Morpho/Euler looping, Ethena basis backing) mirrors Stream/xUSD which collapsed Nov 2025 — $93M loss, $285M contagion ([TheDefiant](https://thedefiant.io/news/defi/how-stream-finance-s-collapse-exposed-defi-s-looping-yield-bubble)).

  Hard-caps final score at 3.0 (weighted would have been 3.7).

## ❓ Open questions for the team

Conditions that *could* be red flags or benign, depending on external context only the protocol team can confirm. Ask each question, then resolve it as `benign` or `confirmed`. A `confirmed` resolution auto-promotes the associated red flag.

### Q1 — raised by `governance-security`  ·  ⏳ pending

**What we saw onchain:** Minter 0x0dfb42aa18ceed719617cd554304f6ca412a6b18 is owned by EOA 0x6c15b25e9750dccb698c1a4023f34015bfe57649 (nonce 3060, actively used) and holds live MINTER_ROLE on reUSD.

**Ask Re Protocol team:**

> Is this EOA an operational hot key, a deployer key still in Ledger custody, or a leftover from initial deployment that should have been transferred to the Safe? Where does the corresponding private key live, and does Re Protocol have a documented rotation/incident process if it leaks?

**If answer is bad:** fires **FLAG_UNSAFE_MINT_AUTHORITY** — _Single private-key compromise yields unlimited reUSD mint. If that key is on a developer laptop or a hot relayer, expected compromise probability over a 1-year window is non-trivial; consequences are total reUSD supply integrity loss._

### Q2 — raised by `governance-security`  ·  ⏳ pending

**What we saw onchain:** 3/5 Safe 0x8eec... holds DEFAULT_ADMIN on reUSD directly, while a separate 48h TimelockController also holds DEFAULT_ADMIN. The Safe's direct admin power makes the timelock optional — Safe can grant UPGRADER to itself in one tx and bypass delay.

**Ask Re Protocol team:**

> Is the dual-admin structure intentional? Will the Safe renounce DEFAULT_ADMIN_ROLE so the 48h timelock is the only path to privileged ops, or is the design that the Safe retains an emergency override?

**If answer is bad:** fires **FLAG_NO_TIMELOCK_ON_CRITICAL_OPS** — _If 3 of 5 signers collude or are phished, they can grant arbitrary mint and upgrade authority to a malicious contract within a single block — no time for Fira liquidator bots, monitoring, or users to react._

### Q3 — raised by `governance-security`  ·  ⏳ pending

**What we saw onchain:** Disclose the 5 Safe signers' identities, geographic distribution, and key-management substrate (hardware wallet vs hot key vs MPC). 4 of 5 owner addresses are EOAs; 1 (0x0AE4eeAFfDA174F84c84c22f03a28F3AAB02FbDC) has 48 bytes of code suggesting an ERC-7702 delegation or smart-wallet abstraction.

**Ask Re Protocol team:**

> Who are the 5 signers? How many independent humans/orgs do they represent? What is the key custody for each (Ledger / Fireblocks / mobile / institutional MPC)? What is the smart-account at 0x0AE4eeAF... and who controls its delegated authority?

**If answer is bad:** fires **FLAG_UNSAFE_PROXY_ADMIN** — _If fewer than 3 truly independent humans control 3 of 5 keys (e.g. 3 keys held by 1 founder), the 3/5 threshold is cosmetic. Smart-wallet signer with delegated authority adds a hidden permission layer._

### Q4 — raised by `governance-security`  ·  ⏳ pending

**What we saw onchain:** Controversy seed flags 'oracle update is rumored to be controlled by an EOA'. reUSD itself has no oracle interface, so the concern must apply to the price feed Fira would integrate. There is no on-chain evidence of an reUSD-specific oracle deployed by Re Protocol.

**Ask Re Protocol team and Fira oracle WG:**

> Which oracle does Re Protocol publish or recommend for reUSD pricing? Who controls the update path of that oracle (single EOA, multisig, Chainlink)? Is the rumored EOA-controlled feed a Re Protocol artefact or a third-party adapter?

**If answer is bad:** fires **GOVERNANCE_SECURITY_CONCERN** — _If the only available reUSD price feed is EOA-pushed, Fira liquidations rely on a single key for solvency. Compromise → mispriced collateral → bad debt or wrongful liquidation._

### Q5 — raised by `governance-security`  ·  ⏳ pending

**What we saw onchain:** Source code for reUSD implementation (0xb5276c436f65913cd5332de745d04fedeb4a21d4), the three minter contracts, the Re-namespaced AccessManager (0x3f0DA1C...), and the timelock are not published under github.com/re-protocol.

**Ask Re Protocol team:**

> Where is the canonical source for these contracts? Is Etherscan source-verified? Is there an audit report covering them, with auditor name and date?

**If answer is bad:** fires **GOVERNANCE_SECURITY_CONCERN** — _Black-box mint logic could contain bypasses (e.g. a hard-coded backdoor minter, signature-recover mint, or upgradable adapter target) invisible without source. Cannot fully audit privileged-action surface._

### Q1 — raised by `asset-controls`  ·  ⏳ pending

**What we saw onchain:** ShareTokenMinterBurner (0x0dfb…) is Ownable-owned by EOA 0x6C15B25E… and holds MINTER_ROLE on reUSD. Owner can set the adapter, granting any address mint authority.

**Ask Re Protocol team:**

> Is the EOA owner of ShareTokenMinterBurner intended to remain the controller, or will ownership be transferred to the 3-of-5 Safe / Timelock? If retained, what offchain key controls (HSM, multisig wrapper, social recovery) protect this EOA?

**If answer is bad:** fires **FLAG_UNSAFE_MINT_AUTHORITY** — _EOA private key compromise → adapter swap → unbounded mint → drain LP/lending markets via reUSD inflation._

### Q2 — raised by `asset-controls`  ·  ⏳ pending

**What we saw onchain:** Both the 3-of-5 Safe and the 48h TimelockController hold DEFAULT_ADMIN_ROLE on reUSD.

**Ask Re Protocol team:**

> Will the Safe renounce DEFAULT_ADMIN_ROLE on reUSD so all admin operations route through the Timelock with the 48h delay? Without that, the Timelock provides no real upgrade-notice guarantee.

**If answer is bad:** fires **FLAG_NO_TIMELOCK_ON_CRITICAL_OPS** — _Compromised Safe → grant UPGRADER_ROLE to attacker → instant proxy swap to malicious implementation with backdoor mint or transfer hijack._

### Q3 — raised by `asset-controls`  ·  ⏳ pending

**What we saw onchain:** InstantRedemption AccessManager (0x3f0DA1C3…) is admin'd by EOA 0x80a62b72df1136acbc57141fb67aa46812fecafc.

**Ask Re Protocol team:**

> Is the AccessManager admin EOA expected, or should it be a Safe? The redemption path is the peg-defence layer for reUSD; an EOA admin here is a single-key risk.

**If answer is bad:** fires **ASSET_CONTROLS_CONCERN** — _EOA compromise → set fee to 100%, raise daily limits, redirect feeVault → drain peg reserves during a liquidation cascade._

### Q4 — raised by `asset-controls`  ·  ⏳ pending

**What we saw onchain:** ShareToken has no pause and no blacklist.

**Ask Re Protocol team:**

> Is the lack of a pause function intentional (censorship resistance) or an oversight? If a peg break or oracle exploit is detected, no admin path exists to halt minting/transfers — only the upstream minter contracts can be paused.

**If answer is bad:** fires **ASSET_CONTROLS_CONCERN** — _Oracle/depeg event → minters and AMM positions unwind freely → Fira liquidations execute against stale prices._

## Access-control walk

A numbered walkthrough for verifying this asset's access-control surface yourself. Start at step 1, run the commands, follow the `Next` pointers.

### Step 1 — reUSD ERC20 token (UUPS proxy)

Address: [`0x5086bf358635B81D8C47C66d1C8b9E567Db70c72`](https://etherscan.io/address/0x5086bf358635B81D8C47C66d1C8b9E567Db70c72)

*Why*: Plain ERC20 + AccessControlUpgradeable + UUPSUpgradeable. Mint requires hasRole(MINTER_ROLE, msg.sender). Upgrade requires hasRole(UPGRADER_ROLE, msg.sender) (enforced inside the implementation's _authorizeUpgrade). Pause/burn similarly role-gated. Token has NO native oracle, exchangeRate, or per-minter cap — every minter has unbounded mint authority. EIP-1967 admin slot is empty (UUPS pattern); upgrade authority lives in the implementation, not in a ProxyAdmin contract.

```bash
# EIP-1967 implementation slot points to current logic
cast storage 0x5086bf358635B81D8C47C66d1C8b9E567Db70c72 0x360894a13ba1a3210667c828492db98dca3e2076cc3735a920a3ca505d382bbc --rpc-url $RPC
# → expect: 0x000000000000000000000000b5276c436f65913cd5332de745d04fedeb4a21d4
# EIP-1967 admin slot empty (UUPS not Transparent)
cast storage 0x5086bf358635B81D8C47C66d1C8b9E567Db70c72 0xb53127684a568b3173ae13b9f8a6016e243e63b6e8ee1178d6a717850b5d6103 --rpc-url $RPC
# → expect: 0x0000000000000000000000000000000000000000000000000000000000000000
```

**Next:** Step 2 (DEFAULT_ADMIN_ROLE on reUSD — direct Safe path (NO TIMELOCK)) → Step 3 (UPGRADER_ROLE → TimelockController (48h delay)) → Step 4 (MINTER_ROLE — three holders (mixed admin paths))

### Step 2 — DEFAULT_ADMIN_ROLE on reUSD — direct Safe path (NO TIMELOCK)

Address: [`0x8eec10616802ef639ca55c98ac856553fadefbad`](https://etherscan.io/address/0x8eec10616802ef639ca55c98ac856553fadefbad)

*Why*: 3-of-5 Safe v1.4.1 holds DEFAULT_ADMIN_ROLE on the token directly, with zero delay. Sequence to mint unlimited reUSD: 3 of 5 signers sign a Safe tx → Safe.execTransaction → reUSD.grantRole(MINTER_ROLE, attackerContract) → attackerContract.mint(any, any). The same path can grant UPGRADER_ROLE to a malicious EOA, bypassing the 48h timelock entirely (the timelock is only the path UPGRADER currently sits in, not the only allowed path). Safe has no modules attached (verified empty), so no Zodiac-style bypass adds further surface.

```bash
# Safe holds DEFAULT_ADMIN_ROLE on reUSD
cast call 0x5086bf358635B81D8C47C66d1C8b9E567Db70c72 'hasRole(bytes32,address)(bool)' 0x0000000000000000000000000000000000000000000000000000000000000000 0x8eec10616802ef639ca55c98ac856553fadefbad --rpc-url $RPC
# → expect: true
# Safe threshold is 3 with 5 owners
cast call 0x8eec10616802ef639ca55c98ac856553fadefbad 'getThreshold()(uint256)' --rpc-url $RPC
# → expect: 3
# No Safe modules attached
cast call 0x8eec10616802ef639ca55c98ac856553fadefbad 'getModulesPaginated(address,uint256)(address[],address)' 0x0000000000000000000000000000000000000001 100 --rpc-url $RPC
# → expect: ([], 0x0000000000000000000000000000000000000001)
```

**End of branch.**

### Step 3 — UPGRADER_ROLE → TimelockController (48h delay)

Address: [`0x69ddea332723cf5407151aaf68b9b076557fca93`](https://etherscan.io/address/0x69ddea332723cf5407151aaf68b9b076557fca93)

*Why*: OZ TimelockController; sole holder of UPGRADER_ROLE on reUSD. To upgrade the implementation: Safe (step 2) calls timelock.schedule(target=reUSD, calldata=upgradeToAndCall(newImpl, ...), delay=48h) → wait 172800s → Safe calls timelock.execute → timelock CALLs reUSD.upgradeToAndCall → _authorizeUpgrade passes because hasRole(UPGRADER, timelock) == true. Timelock's PROPOSER, EXECUTOR, and CANCELLER are ALL the 3/5 Safe — no separate guardian, no multi-party check inside the queue. Timelock is its own DEFAULT_ADMIN (also guarded by 48h delay).

```bash
# Min delay is 48 hours
cast call 0x69ddea332723cf5407151aaf68b9b076557fca93 'getMinDelay()(uint256)' --rpc-url $RPC
# → expect: 172800
# Timelock holds UPGRADER_ROLE on reUSD
cast call 0x5086bf358635B81D8C47C66d1C8b9E567Db70c72 'hasRole(bytes32,address)(bool)' 0x189ab7a9244df0848122154315af71fe140f3db0fe014031783b0946b8c9d2e3 0x69ddea332723cf5407151aaf68b9b076557fca93 --rpc-url $RPC
# → expect: true
# Safe is sole PROPOSER on the timelock
cast call 0x69ddea332723cf5407151aaf68b9b076557fca93 'hasRole(bytes32,address)(bool)' 0xb09aa5aeb3702cfd50b6b62bc4532604938f21248a27a1d5ca736082b6819cc1 0x8eec10616802ef639ca55c98ac856553fadefbad --rpc-url $RPC
# → expect: true
# Safe is also EXECUTOR (no public executor, no separate guardian)
cast call 0x69ddea332723cf5407151aaf68b9b076557fca93 'hasRole(bytes32,address)(bool)' 0xd8aa0f3194971a2a116679f7c2090f6939c8d4e01a2a8d7e41d55e5351469e63 0x8eec10616802ef639ca55c98ac856553fadefbad --rpc-url $RPC
# → expect: true
```

**Next:** Step 2 (DEFAULT_ADMIN_ROLE on reUSD — direct Safe path (NO TIMELOCK))

### Step 4 — MINTER_ROLE — three holders (mixed admin paths)

Address: [`0x5086bf358635B81D8C47C66d1C8b9E567Db70c72`](https://etherscan.io/address/0x5086bf358635B81D8C47C66d1C8b9E567Db70c72)

*Why*: Three independent contracts hold MINTER_ROLE on reUSD. The token enforces NO mint cap, NO rate limit, NO recipient whitelist beyond the role check — any one minter can mint unbounded supply. Branches: (5) UUPS-proxy minter admin'd by the Safe, (6) Adapter minter gated by an OZ AccessManager with 0-second admin grant delay, (7) Ownable minter whose owner is a single EOA.

```bash
# Three minter holders confirmed
cast call 0x5086bf358635B81D8C47C66d1C8b9E567Db70c72 'hasRole(bytes32,address)(bool)' 0x9f2df0fed2c77648de5860a4cc508cd0818c85b8b8a1ab4ceeef8d981c8956a6 0x4691c475be804fa85f91c2d6d0adf03114de3093 --rpc-url $RPC
# → expect: true
```

**Next:** Step 5 (Minter A — UUPS proxy admin'd by 3/5 Safe) → Step 6 (Minter B — gated by AccessManager 0x3f0DA1C3 with zero admin delay) → Step 7 (Minter C — Ownable, owner is single EOA (CRITICAL))

### Step 5 — Minter A — UUPS proxy admin'd by 3/5 Safe

Address: [`0x4691c475be804fa85f91c2d6d0adf03114de3093`](https://etherscan.io/address/0x4691c475be804fa85f91c2d6d0adf03114de3093)

*Why*: Implementation 0x06d4acc104b974cd99bf22e4572f48a051e59670, OZ AccessControl, DEFAULT_ADMIN held by Safe 0x8eec.... Safe can swap the implementation to arbitrary mint logic in one tx (proxy is UUPS, no separate timelock guarding THIS minter). Effective trust set = same 3/5 Safe.

```bash
# Implementation slot points to logic contract
cast storage 0x4691c475be804fa85f91c2d6d0adf03114de3093 0x360894a13ba1a3210667c828492db98dca3e2076cc3735a920a3ca505d382bbc --rpc-url $RPC
# → expect: 0x00000000000000000000000006d4acc104b974cd99bf22e4572f48a051e59670
# Safe holds DEFAULT_ADMIN on this minter
cast call 0x4691c475be804fa85f91c2d6d0adf03114de3093 'hasRole(bytes32,address)(bool)' 0x0000000000000000000000000000000000000000000000000000000000000000 0x8eec10616802ef639ca55c98ac856553fadefbad --rpc-url $RPC
# → expect: true
```

**Next:** Step 2 (DEFAULT_ADMIN_ROLE on reUSD — direct Safe path (NO TIMELOCK))

### Step 6 — Minter B — gated by AccessManager 0x3f0DA1C3 with zero admin delay

Address: [`0xa31deebb3680a3007120e74bcbdf4df36f042a40`](https://etherscan.io/address/0xa31deebb3680a3007120e74bcbdf4df36f042a40)

*Why*: Contract's authority() returns OZ AccessManager 0x3f0DA1C363e34802C6f12F9C27276dC0e6696FD8. AccessManager's ADMIN role (id 0) has getRoleGrantDelay = 0, so whoever holds ADMIN can grant arbitrary callable roles instantly to any address — including granting themselves the function-role for mint(). Source/admin holder of the AccessManager not published; its events show active selector-based role config but admin set is opaque. Treats as untrusted → any compromise of AccessManager admin = unlimited mint.

```bash
# Minter's authority is the AccessManager
cast call 0xa31deebb3680a3007120e74bcbdf4df36f042a40 'authority()(address)' --rpc-url $RPC
# → expect: 0x3f0DA1C363e34802C6f12F9C27276dC0e6696FD8
# AccessManager admin grant delay is zero
cast call 0x3f0DA1C363e34802C6f12F9C27276dC0e6696FD8 'getRoleGrantDelay(uint64)(uint32)' 0 --rpc-url $RPC
# → expect: 0
```

**End of branch.**

### Step 7 — Minter C — Ownable, owner is single EOA (CRITICAL)

Address: [`0x0dfb42aa18ceed719617cd554304f6ca412a6b18`](https://etherscan.io/address/0x0dfb42aa18ceed719617cd554304f6ca412a6b18)

*Why*: Bytecode exposes mint(address,uint256) selector 0x40c10f19 and burn(address,uint256) 0x9dc29fac, gated by Ownable (owner() returns 0x6c15b25e9750dccb698c1a4023f34015bfe57649). That address has no contract code (EOA) and nonce 3060 = actively transacting key. Sequence to mint: single private-key signer → eth_sendTransaction → minter.mint(attacker, anything) → reUSD.mint succeeds because hasRole(MINTER, this minter) is true. No multisig, no timelock, no per-tx cap, no rate limit. This is the trust narrowest path and dominates reUSD's security — total integrity hinges on one EOA's private key custody.

```bash
# Minter still holds MINTER_ROLE
cast call 0x5086bf358635B81D8C47C66d1C8b9E567Db70c72 'hasRole(bytes32,address)(bool)' 0x9f2df0fed2c77648de5860a4cc508cd0818c85b8b8a1ab4ceeef8d981c8956a6 0x0dfb42aa18ceed719617cd554304f6ca412a6b18 --rpc-url $RPC
# → expect: true
# Owner is the EOA
cast call 0x0dfb42aa18ceed719617cd554304f6ca412a6b18 'owner()(address)' --rpc-url $RPC
# → expect: 0x6C15B25E9750Dccb698C1a4023f34015bFe57649
# Owner address is an EOA (no code)
cast code 0x6c15b25e9750dccb698c1a4023f34015bfe57649 --rpc-url $RPC
# → expect: 0x
# EOA actively used (nonce 3060+)
cast nonce 0x6c15b25e9750dccb698c1a4023f34015bfe57649 --rpc-url $RPC
# → expect: 3060 (or higher)
```

**End of branch.**

## Per-criterion scores

| Criterion | Weight | Score | Confidence |
|---|---:|---:|---:|
| Governance & Security | 30% | 3.0 | 0.85 |
| Asset Controls | 25% | 3.0 | 0.85 |
| Cross-Chain Surface | 15% | 2.5 | 0.85 |
| Code Quality | 10% | 6.5 | 0.7 |
| Controversy | 10% | 4.0 | 0.65 |
| Team Transparency | 5% | 8.0 | 0.8 |
| Liquidity Depth | 5% | 4.0 | 0.85 |

## Detailed findings

### 🔑 Governance & Security  ·  score 3 / confidence 0.85 {: .agent-section .agent-governance-security }

#### <span class="sev-badge sev-critical">[CRITICAL]</span> MINTER_ROLE held by single-EOA-owned minter contract 0x0dfb42aa — one EOA can repoint mint authority via setAdapter() {: .finding-header .finding-critical }

Minter contract exposes mint() gated to its `adapter`, but `setAdapter(address)` is `onlyOwner` and owner() is EOA 0x6c15b25e9750dccb698c1a4023f34015bfe57649 (nonce 3060, hot key). One key compromise → owner deploys malicious adapter → calls setAdapter → adapter mints unlimited reUSD. No msig, no timelock, no cap between EOA and unbounded supply.


**Verify on-chain:**

```bash
# Minter still holds MINTER_ROLE on reUSD
cast call 0x5086bf358635B81D8C47C66d1C8b9E567Db70c72 'hasRole(bytes32,address)(bool)' 0x9f2df0fed2c77648de5860a4cc508cd0818c85b8b8a1ab4ceeef8d981c8956a6 0x0dfb42aa18ceed719617cd554304f6ca412a6b18 --rpc-url $RPC
# → expect: true
# Minter owner is an EOA (no code at owner address)
cast call 0x0dfb42aa18ceed719617cd554304f6ca412a6b18 'owner()(address)' --rpc-url $RPC
# → expect: 0x6C15B25E9750Dccb698C1a4023f34015bFe57649
# Owner address has no contract code (i.e. is an EOA)
cast code 0x6c15b25e9750dccb698c1a4023f34015bfe57649 --rpc-url $RPC
# → expect: 0x
```


**Key addresses:**

- Minter contract — [`0x0dfb42aa18ceed719617cd554304f6ca412a6b18`](https://etherscan.io/address/0x0dfb42aa18ceed719617cd554304f6ca412a6b18)
- EOA owner of minter — [`0x6C15B25E9750Dccb698C1a4023f34015bFe57649`](https://etherscan.io/address/0x6C15B25E9750Dccb698C1a4023f34015bFe57649)

#### <span class="sev-badge sev-high">[HIGH]</span> 3/5 Safe is sole DEFAULT_ADMIN of reUSD with no timelock — can grant MINTER, UPGRADER, PAUSER, burner instantly {: .finding-header .finding-high }

Safe 0x8eec10616802ef639ca55c98ac856553fadefbad (3/5, Safe v1.4.1, no modules) holds DEFAULT_ADMIN_ROLE directly on the token. Any 3 signers can grantRole(MINTER) or grantRole(UPGRADER) in one tx with zero delay. The ostensibly-protective 48h TimelockController only gates upgrade if the Safe never grants UPGRADER to itself — which it can do anytime. Effective censorship and rug surface = 3/5 with no time barrier.


**Verify on-chain:**

```bash
# Safe holds DEFAULT_ADMIN_ROLE directly
cast call 0x5086bf358635B81D8C47C66d1C8b9E567Db70c72 'hasRole(bytes32,address)(bool)' 0x0000000000000000000000000000000000000000000000000000000000000000 0x8eec10616802ef639ca55c98ac856553fadefbad --rpc-url $RPC
# → expect: true
# Safe threshold is 3
cast call 0x8eec10616802ef639ca55c98ac856553fadefbad 'getThreshold()(uint256)' --rpc-url $RPC
# → expect: 3
# Safe owners count is 5
cast call 0x8eec10616802ef639ca55c98ac856553fadefbad 'getOwners()(address[])' --rpc-url $RPC
# → expect: array length 5
```


**Key addresses:**

- DEFAULT_ADMIN Safe (3/5) — [`0x8eec10616802ef639ca55c98ac856553fadefbad`](https://etherscan.io/address/0x8eec10616802ef639ca55c98ac856553fadefbad)

#### <span class="sev-badge sev-high">[HIGH]</span> Three independent MINTER_ROLE holders — no shared mint cap, mint authority diffused across mixed-trust contracts {: .finding-header .finding-high }

Active minters: 0x4691c475 (UUPS proxy admin'd by the 3/5 Safe), 0xa31deebb (gated by AccessManager 0x3f0DA1C363e34802C6f12F9C27276dC0e6696FD8 with 0 admin delay), and 0x0dfb42aa (single-EOA-owned). reUSD itself enforces no per-minter cap or rate limit; any one of these contracts can mint unlimited supply.


**Verify on-chain:**

```bash
# Three addresses hold MINTER_ROLE on reUSD
cast call 0x5086bf358635B81D8C47C66d1C8b9E567Db70c72 'hasRole(bytes32,address)(bool)' 0x9f2df0fed2c77648de5860a4cc508cd0818c85b8b8a1ab4ceeef8d981c8956a6 0xa31deebb3680a3007120e74bcbdf4df36f042a40 --rpc-url $RPC
# → expect: true
# AccessManager admin grant delay is zero (instant role grants possible)
cast call 0x3f0DA1C363e34802C6f12F9C27276dC0e6696FD8 'getRoleGrantDelay(uint64)(uint32)' 0 --rpc-url $RPC
# → expect: 0
```


**Key addresses:**

- Minter A (UUPS proxy) — [`0x4691c475be804fa85f91c2d6d0adf03114de3093`](https://etherscan.io/address/0x4691c475be804fa85f91c2d6d0adf03114de3093)
- Minter B (AccessManager-gated) — [`0xa31deebb3680a3007120e74bcbdf4df36f042a40`](https://etherscan.io/address/0xa31deebb3680a3007120e74bcbdf4df36f042a40)
- Minter C (EOA-owned) — [`0x0dfb42aa18ceed719617cd554304f6ca412a6b18`](https://etherscan.io/address/0x0dfb42aa18ceed719617cd554304f6ca412a6b18)

#### <span class="sev-badge sev-medium">[MEDIUM]</span> UUPS proxy with no admin slot — upgrade authority lives in implementation, gated only by UPGRADER_ROLE {: .finding-header .finding-medium }

EIP-1967 admin slot is empty; reUSD 0x5086bf is a UUPS proxy where _authorizeUpgrade enforces UPGRADER_ROLE. Sole holder is TimelockController 0x69ddea... (48h delay). Storage layout assumption: any future implementation must preserve OZ AccessControlUpgradeable + ERC20Upgradeable layout — no on-chain check enforces this. Storage-clobbering upgrade possible.


**Key addresses:**

- reUSD proxy — [`0x5086bf358635B81D8C47C66d1C8b9E567Db70c72`](https://etherscan.io/address/0x5086bf358635B81D8C47C66d1C8b9E567Db70c72)
- Current implementation — [`0xb5276c436f65913cd5332de745d04fedeb4a21d4`](https://etherscan.io/address/0xb5276c436f65913cd5332de745d04fedeb4a21d4)
- TimelockController (UPGRADER, 48h) — [`0x69ddea332723cf5407151aaf68b9b076557fca93`](https://etherscan.io/address/0x69ddea332723cf5407151aaf68b9b076557fca93)

#### <span class="sev-badge sev-medium">[MEDIUM]</span> Source code for governance/minter contracts not published in re-protocol GitHub org {: .finding-header .finding-medium }

github.com/re-protocol exposes only DefiLlama-Adapters, curve-frontend, curve-assets — no contract source for reUSD token, minter adapters, or oracle infrastructure. Reviewers cannot audit mint adapter, exchange-rate, or governance logic except via decompilation. Increases black-box risk and blocks independent verification of admin claims.

#### <span class="sev-badge sev-medium">[MEDIUM]</span> reUSD has no native price feed or exchange-rate function — Fira must rely on external oracle whose governance is out-of-scope of token contract {: .finding-header .finding-medium }

Token exposes no pricePerShare(), totalAssets(), exchangeRate(), or oracle(). It is a 'Re Protocol Deposit Token' (per name()) — pricing depends on whatever oracle Fira integrates. Controversy seed about EOA-controlled oracle cannot be resolved on the token itself; it must be answered by whichever feed Fira selects (Chainlink, redstone, custom). See openQuestions for required disclosure.

#### <span class="sev-badge sev-low">[LOW]</span> Initial deployment EOA still holds elevated authority on at least one minter contract via Ownable {: .finding-header .finding-low }

Deployer-era EOA 0x6c15b25e... lost DEFAULT_ADMIN on reUSD (revoked at block 24522249) but remains owner() of minter 0x0dfb42aa. Cleanup was partial — same key still has live mint authority. Suggests operational discipline issues during handover from EOA to Safe governance.

#### <span class="sev-badge sev-info">[INFO]</span> Multisig & privileged role inventory {: .finding-header .finding-info }

Role | Address | Type | Threshold | Controls
--- | --- | --- | --- | ---
DEFAULT_ADMIN_ROLE on reUSD | 0x8eec10616802ef639ca55c98ac856553fadefbad | Safe v1.4.1 | 3-of-5 | Grant/revoke any role on reUSD; instant (no timelock)
DEFAULT_ADMIN_ROLE on reUSD | 0x69ddea332723cf5407151aaf68b9b076557fca93 | OZ TimelockController | 48h delay | Same as above but delayed
UPGRADER_ROLE on reUSD | 0x69ddea332723cf5407151aaf68b9b076557fca93 | OZ TimelockController | 48h delay | upgradeToAndCall on reUSD UUPS proxy
Timelock PROPOSER/EXECUTOR/CANCELLER | 0x8eec10616802ef639ca55c98ac856553fadefbad | Safe 3-of-5 | 3-of-5 | Schedule + execute upgrade after 48h
MINTER_ROLE on reUSD (3 holders) | 0x4691c475be804fa85f91c2d6d0adf03114de3093 | UUPS proxy with own AccessControl, admin = 3/5 Safe | n/a | Mint reUSD
MINTER_ROLE on reUSD | 0xa31deebb3680a3007120e74bcbdf4df36f042a40 | Contract gated by AccessManager 0x3f0DA1C363e34802C6f12F9C27276dC0e6696FD8 | 0 grant delay | Mint reUSD
MINTER_ROLE on reUSD | 0x0dfb42aa18ceed719617cd554304f6ca412a6b18 | Ownable contract, owner = EOA 0x6c15b25e | 1 EOA | Mint reUSD
Safe modules on 0x8eec | none | n/a | n/a | No bypass modules detected (good)
PAUSER_ROLE on reUSD | None of probed candidates | n/a | n/a | Possibly unset or held by unknown contract



### 🛡️ Asset Controls  ·  score 3 / confidence 0.85 {: .agent-section .agent-asset-controls }

#### <span class="sev-badge sev-critical">[CRITICAL]</span> EOA-controlled wrapper has unbounded MINTER_ROLE on reUSD via Ownable adapter setter {: .finding-header .finding-critical }

ShareTokenMinterBurner is one of three live MINTER_ROLE holders on reUSD. Source confirms standard Ownable; current owner is an EOA (Re Deployer). Owner can repoint the adapter and mint unlimited reUSD; reUSD itself enforces no supply cap. This is the classic EOA-mints-stablecoin failure mode.


**Verify on-chain:**

```bash
# Confirm MINTER_ROLE still held by ShareTokenMinterBurner.
cast call 0x5086bf358635B81D8C47C66d1C8b9E567Db70c72 'hasRole(bytes32,address)(bool)' 0x9f2df0fed2c77648de5860a4cc508cd0818c85b8b8a1ab4ceeef8d981c8956a6 0x0dfb42aa18ceed719617cd554304f6ca412a6b18 --rpc-url $RPC
# → expect: true
# Confirm wrapper owner is EOA (Re Deployer).
cast call 0x0dfb42aa18ceed719617cd554304f6ca412a6b18 'owner()(address)' --rpc-url $RPC && cast code 0x6c15b25e9750dccb698c1a4023f34015bfe57649 --rpc-url $RPC
# → expect: owner returns 0x6C15B25E9750Dccb698C1a4023f34015bFe57649; code returns 0x (EOA).
```


**Key addresses:**

- reUSD proxy (Re Protocol Deposit Token) — [`0x5086bf358635B81D8C47C66d1C8b9E567Db70c72`](https://etherscan.io/address/0x5086bf358635B81D8C47C66d1C8b9E567Db70c72)
- ShareTokenMinterBurner (MINTER_ROLE holder) — [`0x0dfb42aa18ceed719617cd554304f6ca412a6b18`](https://etherscan.io/address/0x0dfb42aa18ceed719617cd554304f6ca412a6b18)
- ShareTokenMinterBurner owner (Re Deployer EOA) — [`0x6C15B25E9750Dccb698C1a4023f34015bFe57649`](https://etherscan.io/address/0x6C15B25E9750Dccb698C1a4023f34015bFe57649)

#### <span class="sev-badge sev-high">[HIGH]</span> Token DEFAULT_ADMIN_ROLE held directly by 3-of-5 Safe, bypassing the 48h TimelockController {: .finding-header .finding-high }

Both the TimelockController (0x69dd…) and a 3-of-5 Safe v1.4.1 (0x8eec…) hold DEFAULT_ADMIN_ROLE on reUSD. The Safe is the timelock's sole PROPOSER. Because the Safe holds the role directly, 3 signatures can grant new MINTER_ROLE/UPGRADER_ROLE with zero delay, neutralising the timelock.


**Verify on-chain:**

```bash
# Confirm both holders have DEFAULT_ADMIN_ROLE.
cast call 0x5086bf358635B81D8C47C66d1C8b9E567Db70c72 'hasRole(bytes32,address)(bool)' 0x0000000000000000000000000000000000000000000000000000000000000000 0x8eec10616802ef639ca55c98ac856553fadefbad --rpc-url $RPC
# → expect: true (Safe). Repeat with 0x69ddea332723cf5407151aaf68b9b076557fca93 → also true.
# Confirm Safe is 3-of-5 v1.4.1.
cast call 0x8eec10616802ef639ca55c98ac856553fadefbad 'getThreshold()(uint256)' --rpc-url $RPC && cast call 0x8eec10616802ef639ca55c98ac856553fadefbad 'VERSION()(string)' --rpc-url $RPC
# → expect: 3 and "1.4.1".
```


**Key addresses:**

- Token admin Safe (3-of-5) — [`0x8eec10616802ef639ca55c98ac856553fadefbad`](https://etherscan.io/address/0x8eec10616802ef639ca55c98ac856553fadefbad)
- TimelockController (48h delay) — [`0x69ddea332723cf5407151aaf68b9b076557fca93`](https://etherscan.io/address/0x69ddea332723cf5407151aaf68b9b076557fca93)

#### <span class="sev-badge sev-high">[HIGH]</span> UUPS-upgradeable token implementation can introduce blacklist, pause or arbitrary logic post-listing {: .finding-header .finding-high }

ShareToken inherits UUPSUpgradeable; _authorizeUpgrade is gated by UPGRADER_ROLE. UPGRADER_ROLE is held by the TimelockController (good — 48h notice), but DEFAULT_ADMIN_ROLE on the token is also held by the 3-of-5 Safe directly (see prior finding), letting the Safe grant UPGRADER_ROLE to itself with no delay and ship a new implementation immediately.


**Verify on-chain:**

```bash
# Read EIP-1967 implementation slot.
cast storage 0x5086bf358635B81D8C47C66d1C8b9E567Db70c72 0x360894a13ba1a3210667c828492db98dca3e2076cc3735a920a3ca505d382bbc --rpc-url $RPC
# → expect: Returns padded 0x…b5276c436f65913cd5332de745d04fedeb4a21d4.
# Confirm Timelock holds UPGRADER_ROLE.
cast call 0x5086bf358635B81D8C47C66d1C8b9E567Db70c72 'hasRole(bytes32,address)(bool)' 0x189ab7a9244df0848122154315af71fe140f3db0fe014031783b0946b8c9d2e3 0x69ddea332723cf5407151aaf68b9b076557fca93 --rpc-url $RPC
# → expect: true.
```


**Key addresses:**

- Current ShareToken implementation — [`0xb5276c436f65913cd5332de745d04fedeb4a21d4`](https://etherscan.io/address/0xb5276c436f65913cd5332de745d04fedeb4a21d4)

#### <span class="sev-badge sev-medium">[MEDIUM]</span> reUSD has no supply cap, no pause, no permit and no transfer hooks — listed as info but means mint is unbounded {: .finding-header .finding-medium }

Verified source for the ShareToken implementation (0xb5276c…) shows ERC20Upgradeable + AccessControl + UUPS only — no Pausable, no blacklist, no _update override, no ERC20Permit, no MAX_SUPPLY. Combined with role-controlled mint, any minter can dilute supply without limit. Also means there is no admin pause if a key is compromised.


**Key addresses:**

- Current implementation (verified, ShareToken) — [`0xb5276c436f65913cd5332de745d04fedeb4a21d4`](https://etherscan.io/address/0xb5276c436f65913cd5332de745d04fedeb4a21d4)

#### <span class="sev-badge sev-medium">[MEDIUM]</span> Three live MINTER_ROLE holders, one anonymous (InstantRedemption AccessManager admin is an EOA) {: .finding-header .finding-medium }

MINTER_ROLE is held by InsuranceCapitalLayer (0x4691…), InstantRedemption (0xa31d…) and ShareTokenMinterBurner (0x0dfb…). InstantRedemption is governed by AccessManager 0x3f0DA1C3…; that AccessManager's only DEFAULT_ADMIN was granted to EOA 0x80a62b72df1136acbc57141fb67aa46812fecafc, so an EOA can re-route privileged functions on the redemption path.


**Verify on-chain:**

```bash
# Confirm AccessManager admin grant target is an EOA.
cast code 0x80a62b72df1136acbc57141fb67aa46812fecafc --rpc-url $RPC
# → expect: 0x (EOA).
```


**Key addresses:**

- InstantRedemption (MINTER_ROLE) — [`0xa31deebb3680a3007120e74bcbdf4df36f042a40`](https://etherscan.io/address/0xa31deebb3680a3007120e74bcbdf4df36f042a40)
- InsuranceCapitalLayer proxy (MINTER_ROLE) — [`0x4691c475be804fa85f91c2d6d0adf03114de3093`](https://etherscan.io/address/0x4691c475be804fa85f91c2d6d0adf03114de3093)
- AccessManager governing InstantRedemption — [`0x3f0DA1C363e34802C6f12F9C27276dC0e6696FD8`](https://etherscan.io/address/0x3f0DA1C363e34802C6f12F9C27276dC0e6696FD8)
- AccessManager admin EOA — [`0x80a62b72df1136acbc57141fb67aa46812fecafc`](https://etherscan.io/address/0x80a62b72df1136acbc57141fb67aa46812fecafc)

#### <span class="sev-badge sev-low">[LOW]</span> Safe owner set is 4 EOAs + 1 contract; threshold 3 is exactly at the FLAG floor {: .finding-header .finding-low }

Token admin Safe owners: 0x2a3Ef2…, 0x28d8af…, 0x7dd97C…, 0x1F76cC… (all EOAs) and 0x0AE4eeAFf… (contract — not drilled further). 3-of-5 narrowly clears the rubric's hard FLAG bar (<3 / signers ≤3) but is the minimum viable Safe; recommend ≥4-of-7 with all signers diversified before any cap increase on Fira.


**Key addresses:**

- Token admin Safe — [`0x8eec10616802ef639ca55c98ac856553fadefbad`](https://etherscan.io/address/0x8eec10616802ef639ca55c98ac856553fadefbad)

#### <span class="sev-badge sev-low">[LOW]</span> Timelock structure is sound — 48h delay, multiple cancellers — but bypassed by parallel direct admin grant {: .finding-header .finding-low }

TimelockController has getMinDelay = 172800s (48h). PROPOSER = Safe, CANCELLER = Safe + EOA 0x07e5fac…, EXECUTOR = Safe + EOA 0x4bfea59b…. Structure is fine in isolation but provides no protection because the Safe also holds DEFAULT_ADMIN_ROLE on the token directly (see high finding).


**Key addresses:**

- TimelockController — [`0x69ddea332723cf5407151aaf68b9b076557fca93`](https://etherscan.io/address/0x69ddea332723cf5407151aaf68b9b076557fca93)


### 🧪 Code Quality  ·  score 6.5 / confidence 0.7 {: .agent-section .agent-code-quality }

#### <span class="sev-badge sev-medium">[MEDIUM]</span> Smart-contract source repository (`re-protocol/re-defi`) is private — source only inspectable via block-explorer verification {: .finding-header .finding-medium }

The Hacken audit cites `https://github.com/re-protocol/re-defi` as the in-scope repo, but the URL returns 404 (GitHub API confirms private). The public `re-protocol` org exposes only 3 forks (DefiLlama-Adapters, curve-frontend, curve-assets) — no original source. Independent reviewers cannot study commit history, CI, test suite, or PRs. Verified Etherscan source is the only public artifact. [Hacken (Sep 2024)](https://hacken.io/audits/re-protocol/sca-re-re-defi-aug2024/).



**Key addresses:**

- reUSD proxy (mainnet) — [`0x5086bf358635B81D8C47C66d1C8b9E567Db70c72`](https://etherscan.io/address/0x5086bf358635B81D8C47C66d1C8b9E567Db70c72)
- ShareToken impl (mainnet) — [`0xb5276c436f65913cd5332de745d04fedeb4a21d4`](https://etherscan.io/address/0xb5276c436f65913cd5332de745d04fedeb4a21d4)

#### <span class="sev-badge sev-medium">[MEDIUM]</span> Certora (Sep 2025) reported 1 critical + 4 high findings on the audited surface — all marked resolved but density is non-trivial {: .finding-header .finding-medium }

[Certora Sep 2025](https://www.certora.com/reports/re-core) ([PDF](https://certora.cdn.prismic.io/certora/aNbmwp5xUNkB1KsL_ReCore-Certora-SecurityAssessmentFinalReport-September2025.pdf)) flagged unbounded loop in `InstantRedemption`, missing input validation in `RedemptionGateway`, arithmetic logic in `Prestaking`, and oracle-manipulation vector in `ThresholdOracle`. All addressed pre-publication, but the cluster shows the protocol shipped real bugs into mainnet code that an earlier audit missed.


#### <span class="sev-badge sev-low">[LOW]</span> Hacken (Sep 2024) audit — 42.11% branch coverage well below industry norm for collateral-grade DeFi {: .finding-header .finding-low }

[Hacken (Sep 2024)](https://hacken.io/audits/re-protocol/sca-re-re-defi-aug2024/) on commit `d099cbf` reported 0 critical, 0 high, 4 medium, 7 low, 18 observations (all resolved) — but explicitly notes 42.11% branch coverage and that multi-user interactions are not thoroughly tested. Mature DeFi protocols typically run 80%+ branch coverage with invariant suites; thin tests increase regression risk on every upgrade.


#### <span class="sev-badge sev-low">[LOW]</span> No public bug-bounty program (Immunefi, HackerOne) identified for Re Protocol {: .finding-header .finding-low }

Search across Immunefi and the docs portal returned no active bounty for Re Protocol / re.xyz. Two paid audits exist but ongoing whitehat economics are absent — researchers have no sanctioned channel or payout to disclose findings. For a protocol holding >$150M reUSD, this is a notable gap relative to peers (Ethena, Sky, Frax all run public bounties).


#### <span class="sev-badge sev-info">[INFO]</span> Token contract verified on every claimed chain — Ethereum, Arbitrum, Base, Avalanche all use identical ERC1967Proxy + ShareToken pattern {: .finding-header .finding-info }

Etherscan, Arbiscan, Basescan, Snowtrace all confirm verified source for both the ERC1967Proxy and the underlying `ShareToken` implementation. Compiler `v0.8.20+commit.a1b79de6`, optimizer enabled (100 runs), EVM Paris, no via-IR. UUPS upgrade pattern using OpenZeppelin v5 contracts. Bytecode-source consistency holds via Etherscan "Exact Match" badge.



**Key addresses:**

- ShareToken impl (Arbitrum) — [`0x2828298ea649c18be72610a8772337673758c3e4`](https://etherscan.io/address/0x2828298ea649c18be72610a8772337673758c3e4)
- ShareToken impl (Base) — [`0xaDC4794909605570D4C43040EB2bd5c0871feDDA`](https://etherscan.io/address/0xaDC4794909605570D4C43040EB2bd5c0871feDDA)
- ShareToken impl (Avalanche) — [`0x34bdd8D872f847Bc8CA76E3A139604ba06fc7141`](https://etherscan.io/address/0x34bdd8D872f847Bc8CA76E3A139604ba06fc7141)

#### <span class="sev-badge sev-info">[INFO]</span> Upgrade authority routed through a 3-of-5 MPC multisig with a 48-hour timelock per protocol documentation {: .finding-header .finding-info }

Per `docs.re.xyz/security-and-audits`, upgrades sit behind "Governance MPC (3-of-5)" with a "48-hour timelock". Additional MPC 3-of-5 / 5-of-8 multisigs control oracle, redemption, custodian, and access-manager configuration. Signer identities are not published, and on-chain `RoleGranted` traces show the deployer EOA `0xf04422...72f2` (a `Decentralized Fund` proxy) initially seeded roles. Centralisation risk shifts to MPC custody quality.



**Key addresses:**

- InsuranceCapitalLayerFactory (admin role holder) — [`0xf682e0e4288e9db3229d6f8d9adf0bb1289e99eb`](https://etherscan.io/address/0xf682e0e4288e9db3229d6f8d9adf0bb1289e99eb)
- Decentralized Fund (deployer) — [`0xf04422e68f55e7c25724128692c3063a775472f2`](https://etherscan.io/address/0xf04422e68f55e7c25724128692c3063a775472f2)

#### <span class="sev-badge sev-info">[INFO]</span> No history of public exploits or security advisories specific to Re Protocol's reUSD {: .finding-header .finding-info }

Web search across Rekt, ImmunefiSupport, security trackers, GitHub Security Advisories returned no exploit, hack, or postmortem tied to Re Protocol's reUSD (`0x5086bf...0c72`). The Resupply Protocol "reUSD" hack (June 2025, $10M) is a different token (`0x57aB1E...4Bb0`) and a separate team — unrelated to re.xyz.



### 🌉 Cross-Chain Surface  ·  score 2.5 / confidence 0.85 {: .agent-section .agent-cross-chain-surface }

#### <span class="sev-badge sev-critical">[CRITICAL]</span> LayerZero OFT adapter is owned by a single EOA that can rewrite peers, DVNs and the mint adapter {: .finding-header .finding-critical }

OFTAdapter 0x2BB4046022B9161f3F84Ad8E35cac1d5946e0e85 returns owner() = 0x6c15b25e9750dccb698c1a4023f34015bfe57649 (code length 2 — confirmed EOA). That EOA is also the LayerZero delegate, so a single key compromise allows setPeer to a malicious remote OApp, DVN config reset, and unlimited mint on mainnet via ShareTokenMinterBurner.


**Verify on-chain:**

```bash
# Confirm adapter owner is the EOA
cast call 0x2BB4046022B9161f3F84Ad8E35cac1d5946e0e85 'owner()(address)' --rpc-url $RPC
# → expect: 0x6C15B25E9750Dccb698C1a4023f34015bFe57649
# Confirm owner has no code (EOA)
cast code 0x6C15B25E9750Dccb698C1a4023f34015bFe57649 --rpc-url $RPC
# → expect: 0x
# Confirm same EOA is the LZ delegate
cast call 0x1a44076050125825900e736c501f859c50fE728c 'delegates(address)(address)' 0x2BB4046022B9161f3F84Ad8E35cac1d5946e0e85 --rpc-url $RPC
# → expect: 0x6C15B25E9750Dccb698C1a4023f34015bFe57649
```


**Key addresses:**

- reUSD LayerZero OFTAdapter (mainnet) — [`0x2BB4046022B9161f3F84Ad8E35cac1d5946e0e85`](https://etherscan.io/address/0x2BB4046022B9161f3F84Ad8E35cac1d5946e0e85)
- Adapter owner / LZ delegate (EOA) — [`0x6C15B25E9750Dccb698C1a4023f34015bFe57649`](https://etherscan.io/address/0x6C15B25E9750Dccb698C1a4023f34015bFe57649)
- LayerZero V2 EndpointV2 (mainnet) — [`0x1a44076050125825900e736c501f859c50fE728c`](https://etherscan.io/address/0x1a44076050125825900e736c501f859c50fE728c)

#### <span class="sev-badge sev-critical">[CRITICAL]</span> Same EOA also owns ShareTokenMinterBurner, which holds MINTER_ROLE on the reUSD proxy {: .finding-header .finding-critical }

ShareTokenMinterBurner 0x0dfb42aa18ceed719617cd554304f6ca412a6b18 (MINTER_ROLE on reUSD) returns owner() = 0x6c15b25e9750dccb698c1a4023f34015bfe57649 — the same EOA. setAdapter() lets that EOA point the minter at any address that can then mint unlimited reUSD on mainnet without any LZ message.


**Verify on-chain:**

```bash
# Minter contract has MINTER_ROLE on reUSD proxy
cast call 0x5086bf358635B81D8C47C66d1C8b9E567Db70c72 'hasRole(bytes32,address)(bool)' 0x9f2df0fed2c77648de5860a4cc508cd0818c85b8b8a1ab4ceeef8d981c8956a6 0x0dfb42aa18ceed719617cd554304f6ca412a6b18 --rpc-url $RPC
# → expect: true
# Minter contract owner is the same EOA
cast call 0x0dfb42aa18ceed719617cd554304f6ca412a6b18 'owner()(address)' --rpc-url $RPC
# → expect: 0x6C15B25E9750Dccb698C1a4023f34015bFe57649
```


**Key addresses:**

- ShareTokenMinterBurner (LZ-driven) — [`0x0dfb42aa18ceed719617cd554304f6ca412a6b18`](https://etherscan.io/address/0x0dfb42aa18ceed719617cd554304f6ca412a6b18)
- Adapter / minter owner (EOA) — [`0x6C15B25E9750Dccb698C1a4023f34015bFe57649`](https://etherscan.io/address/0x6C15B25E9750Dccb698C1a4023f34015bFe57649)
- reUSD proxy (mainnet) — [`0x5086bf358635B81D8C47C66d1C8b9E567Db70c72`](https://etherscan.io/address/0x5086bf358635B81D8C47C66d1C8b9E567Db70c72)

#### <span class="sev-badge sev-high">[HIGH]</span> reUSD has no canonical bridge — supply consistency depends on off-chain Fireblocks MPC plus permissioned mint/burn on each chain {: .finding-header .finding-high }

The reUSD ERC20 itself is a vanilla UUPS proxy (ShareToken — ERC20Upgradeable + AccessControlUpgradeable) with no LZ/CCIP/Wormhole logic. Cross-chain transfer is implemented out-of-band via three independent ShareTokenMinterBurner contracts holding MINTER_ROLE; one is wired to LayerZero, the others (0x4691c4..., 0xa31dee...) are driven by adapters Re Protocol controls via Fireblocks MPC. There is no on-chain proof that mainnet supply equals total supply burned on remote chains.


**Verify on-chain:**

```bash
# reUSD is a plain UUPS proxy, no endpoint()
cast call 0x5086bf358635B81D8C47C66d1C8b9E567Db70c72 'endpoint()(address)' --rpc-url $RPC
# → expect: execution reverted
# Three independent MINTER_ROLE holders
cast call 0x5086bf358635B81D8C47C66d1C8b9E567Db70c72 'hasRole(bytes32,address)(bool)' 0x9f2df0fed2c77648de5860a4cc508cd0818c85b8b8a1ab4ceeef8d981c8956a6 0x4691c475be804fa85f91c2d6d0adf03114de3093 --rpc-url $RPC
# → expect: true
```


**Key addresses:**

- reUSD proxy (mainnet) — [`0x5086bf358635B81D8C47C66d1C8b9E567Db70c72`](https://etherscan.io/address/0x5086bf358635B81D8C47C66d1C8b9E567Db70c72)
- Minter #1 (early) — [`0x4691c475be804fa85f91c2d6d0adf03114de3093`](https://etherscan.io/address/0x4691c475be804fa85f91c2d6d0adf03114de3093)
- Minter #2 — [`0xa31deebb3680a3007120e74bcbdf4df36f042a40`](https://etherscan.io/address/0xa31deebb3680a3007120e74bcbdf4df36f042a40)
- Minter #3 (LZ adapter-driven) — [`0x0dfb42aa18ceed719617cd554304f6ca412a6b18`](https://etherscan.io/address/0x0dfb42aa18ceed719617cd554304f6ca412a6b18)

#### <span class="sev-badge sev-high">[HIGH]</span> LayerZero ULN is 2-of-2 required DVNs (LayerZero Labs + Nethermind), zero optional DVNs {: .finding-header .finding-high }

getConfig on Send ULN302 returns requiredDVNCount=2, optionalDVNCount=0 with required DVNs 0x589dedbd... (LayerZero Labs) and 0xa59ba433... (Nethermind). Both must attest, so a single DVN compromise does not forge a message — but the EOA delegate can rewrite this config at any block, and there is no defense-in-depth from optional DVNs (the post-KelpDAO best practice).


**Verify on-chain:**

```bash
# Pull ULN config for Arbitrum peer (eid 30110)
cast call 0x1a44076050125825900e736c501f859c50fE728c 'getConfig(address,address,uint32,uint32)(bytes)' 0x2BB4046022B9161f3F84Ad8E35cac1d5946e0e85 0xbB2Ea70C9E858123480642Cf96acbcCE1372dCe1 30110 2 --rpc-url $RPC
# → expect: encoded UlnConfig with two required DVNs 0x589dedbd... and 0xa59ba433...
```


**Key addresses:**

- LayerZero Labs DVN (mainnet) — [`0x589dEDbD617e0CBcB916A9223F4d1300c294236b`](https://etherscan.io/address/0x589dEDbD617e0CBcB916A9223F4d1300c294236b)
- Nethermind DVN (mainnet) — [`0xa59ba433ac34d2927232918ef5b2eaafcf130ba5`](https://etherscan.io/address/0xa59ba433ac34d2927232918ef5b2eaafcf130ba5)
- Send ULN302 (mainnet) — [`0xbB2Ea70C9E858123480642Cf96acbcCE1372dCe1`](https://etherscan.io/address/0xbB2Ea70C9E858123480642Cf96acbcCE1372dCe1)

#### <span class="sev-badge sev-medium">[MEDIUM]</span> reUSD is on 7 chains — wider surface than the user-supplied 4 {: .finding-header .finding-medium }

Re Protocol docs list 7 deployments — Ethereum, Arbitrum, Base, Avalanche, BNB Chain, Katana, Ink. Three (BNB, Katana, Ink) were not in the brief, so any monitoring or pause runbook must cover them too. Probed totals (May 2026) are roughly 154.8M on mainnet, 15.4k on Arbitrum, 561k on Base, 880k on Avalanche.


**Verify on-chain:**

```bash
# reUSD on Katana
cast call 0xe08853433fDBC504240455e295B644E0F44c3B29 'symbol()(string)' --rpc-url $RPC_KATANA
# → expect: reUSD
# reUSD on BNB
cast call 0xbA9425EC55ee0E72216D18e0ad8BBbA2553bFb60 'symbol()(string)' --rpc-url $RPC_BNB
# → expect: reUSD
```


**Key addresses:**

- reUSD Ethereum — [`0x5086bf358635B81D8C47C66d1C8b9E567Db70c72`](https://etherscan.io/address/0x5086bf358635B81D8C47C66d1C8b9E567Db70c72)
- reUSD Arbitrum — [`0x76cE01F0Ef25AA66cC5F1E546a005e4A63B25609`](https://etherscan.io/address/0x76cE01F0Ef25AA66cC5F1E546a005e4A63B25609)
- reUSD Base — [`0x7D214438D0F27AfCcC23B3d1e1a53906aCE5CFEa`](https://etherscan.io/address/0x7D214438D0F27AfCcC23B3d1e1a53906aCE5CFEa)
- reUSD Avalanche (corrected from brief — drop trailing 3) — [`0x180aF87b47Bf272B2df59dccf2D76a6eaFa625Bf`](https://etherscan.io/address/0x180aF87b47Bf272B2df59dccf2D76a6eaFa625Bf)
- reUSD Katana — [`0xe08853433fDBC504240455e295B644E0F44c3B29`](https://etherscan.io/address/0xe08853433fDBC504240455e295B644E0F44c3B29)
- reUSD BNB Chain — [`0xbA9425EC55ee0E72216D18e0ad8BBbA2553bFb60`](https://etherscan.io/address/0xbA9425EC55ee0E72216D18e0ad8BBbA2553bFb60)
- reUSD Ink — [`0x5BCf6B008bf80b9296238546BaCE1797657B05d6`](https://etherscan.io/address/0x5BCf6B008bf80b9296238546BaCE1797657B05d6)

#### <span class="sev-badge sev-medium">[MEDIUM]</span> Mainnet DEFAULT_ADMIN / UPGRADER on reUSD held by 3-of-5 Safe and an unverified contract — no timelock {: .finding-header .finding-medium }

Final-state holders of DEFAULT_ADMIN_ROLE on reUSD mainnet are 0x69ddea... (custom contract, ~11kB code, looks like a controller/AccessManager) and 0x8eec106... (Safe with owners 0x2a3Ef..., 0x28d8a..., 0x7dd97..., 0x1F76c..., 0x0AE4e..., threshold 3). 0x69ddea also holds UPGRADER_ROLE so it can swap implementation. No on-chain timelock between either signer set and a malicious upgrade or a MINTER_ROLE grant.


**Verify on-chain:**

```bash
# Safe owners and threshold for the admin Safe
cast call 0x8eec10616802ef639ca55c98ac856553fadefbad 'getOwners()(address[])' --rpc-url $RPC && cast call 0x8eec10616802ef639ca55c98ac856553fadefbad 'getThreshold()(uint256)' --rpc-url $RPC
# → expect: [0x2a3Ef2FEd07D025b8B1f07d99C77471D11529db9, 0x28d8af3CF7286Bdc34ae80cb90093dFA4dbb0020, 0x7dd97C12abd41c53B4f2B3df6b872753F9DABCaa, 0x1F76cC0eF4605f57478f3044e703AF6B0C57A297, 0x0AE4eeAFfDA174F84c84c22f03a28F3AAB02FbDC] / 3
# 0x69ddea has DEFAULT_ADMIN_ROLE on reUSD
cast call 0x5086bf358635B81D8C47C66d1C8b9E567Db70c72 'hasRole(bytes32,address)(bool)' 0x0000000000000000000000000000000000000000000000000000000000000000 0x69ddea332723cf5407151aaf68b9b076557fca93 --rpc-url $RPC
# → expect: true
```


**Key addresses:**

- Admin / Upgrader controller (custom contract, no Safe interface) — [`0x69ddea332723cf5407151aaf68b9b076557fca93`](https://etherscan.io/address/0x69ddea332723cf5407151aaf68b9b076557fca93)
- Admin Safe 3-of-5 — [`0x8eec10616802ef639ca55c98ac856553fadefbad`](https://etherscan.io/address/0x8eec10616802ef639ca55c98ac856553fadefbad)

#### <span class="sev-badge sev-medium">[MEDIUM]</span> Per-chain implementations differ — three distinct ShareToken impls across Ethereum, Arbitrum, Base, Avalanche {: .finding-header .finding-medium }

EIP-1967 implementation slot reads to different addresses on each chain — Ethereum 0xb5276c4..., Arbitrum 0x2828298ea..., Base 0xadc4794909..., Avalanche 0x34bdd8d8.... Re Protocol can ship divergent logic (e.g., a different mint authorisation check) on any chain without touching mainnet, expanding the trust surface.


**Key addresses:**

- Mainnet impl — [`0xb5276c436f65913cd5332de745d04fedeb4a21d4`](https://etherscan.io/address/0xb5276c436f65913cd5332de745d04fedeb4a21d4)
- Arbitrum impl — [`0x2828298ea649c18be72610a8772337673758c3e4`](https://etherscan.io/address/0x2828298ea649c18be72610a8772337673758c3e4)
- Base impl — [`0xadc4794909605570d4c43040eb2bd5c0871fedda`](https://etherscan.io/address/0xadc4794909605570d4c43040eb2bd5c0871fedda)
- Avalanche impl — [`0x34bdd8d872f847bc8ca76e3a139604ba06fc7141`](https://etherscan.io/address/0x34bdd8d872f847bc8ca76e3a139604ba06fc7141)

#### <span class="sev-badge sev-low">[LOW]</span> Token decimals are 18 on all probed chains, totals consistent with a young token {: .finding-header .finding-low }

name() returns "Re Protocol Deposit Token" (or "Re Protocol reUSD" on Base) with symbol reUSD and 18 decimals on Ethereum / Arbitrum / Base / Avalanche. Total supply mainnet ~154.78M, Arbitrum ~15.4k, Base ~561k, Avalanche ~880k — most of the float lives on mainnet, which is what Fira cares about.


**Key addresses:**

- reUSD mainnet — [`0x5086bf358635B81D8C47C66d1C8b9E567Db70c72`](https://etherscan.io/address/0x5086bf358635B81D8C47C66d1C8b9E567Db70c72)

#### <span class="sev-badge sev-info">[INFO]</span> Re Protocol docs describe MPC multisig governance (Fireblocks) over critical controls {: .finding-header .finding-info }

docs.re.xyz states "Critical controls including oracle configuration, redemptions configuration, access manager, and custodian manager are operated through MPC multi-signature wallets" — i.e. Fireblocks-style off-chain MPC, not on-chain Safe. On-chain we observe a 3-of-5 Safe holding DEFAULT_ADMIN, plus the EOA running the LZ adapter; the MPC layer is invisible to Fira's monitoring.


**Key addresses:**

- Resilience BVI Ltd. issuer (off-chain) — [`0x0000000000000000000000000000000000000000`](https://etherscan.io/address/0x0000000000000000000000000000000000000000)


### 👥 Team Transparency  ·  score 8 / confidence 0.8 {: .agent-section .agent-team-transparency }

#### <span class="sev-badge sev-low">[LOW]</span> Prior venture Cover wound down in 2022 — orderly transition, not a fraud event, but worth noting for track record. {: .finding-header .finding-low }

Cover.com (Saroya's prior insurtech, 2016-2022) closed after failing to raise/acquire successfully despite 5,000 partner agencies and "underwriting profitably." Policyholders were transitioned to other insurers — orderly wind-down, not a rug. Indicates capital-markets execution risk rather than ethical risk; reasonable founders fail and reset, but it does show Saroya has not yet shipped a multi-year scaled exit.


**Verify on-chain:**

```bash
https://coverager.com/cover-cuts-40-of-staff/
# → expect: Cover layoffs and wind-down 2022, policyholders transitioned
```

#### <span class="sev-badge sev-low">[LOW]</span> Sub-team beyond CEO/VPE only partially visible — Sheng Puah (Finance) and Jonathan Lim (Underwriting) listed, but no public engineering team roster. {: .finding-header .finding-low }

TheOrg lists 4 named individuals (Saroya, White, Sheng Puah CPA — Head of Finance, Jonathan Lim — Head of Underwriting). No public engineering team page on re.xyz; GitHub org [github.com/re-protocol](https://github.com/re-protocol) hosts only forks of DefiLlama/Curve adapters with no engineering-team identity disclosed. Code is closed-source.


**Verify on-chain:**

```bash
https://github.com/re-protocol
# → expect: Org has 3 forks (DefiLlama, curve-frontend, curve-assets), no public members
https://theorg.com/org/re-xyz
# → expect: Re team page lists 4 leadership roles
```

#### <span class="sev-badge sev-low">[LOW]</span> Closed-source contracts on a tokenized-reinsurance product — typical for regulated finance, but pairs with off-chain attestation dependency. {: .finding-header .finding-low }

Re's smart contracts are not in their public GitHub org. Combined with Fireblocks custody + The Network Firm daily attestation + Chainlink oracle, the team-control surface is non-trivially off-chain. Whether on-chain admin keys are EOA or multisig is the controversy seed — but that question lives with the governance-security agent, not here.


**Verify on-chain:**

```bash
https://github.com/re-protocol
# → expect: No public smart-contract repos for reUSD
```

#### <span class="sev-badge sev-info">[INFO]</span> CEO Karn Saroya fully doxxed — MIT Master of Finance, Y Combinator alum, San Francisco-based serial insurtech founder. {: .finding-header .finding-info }

Saroya co-founded Stylekick (acquired by Shopify 2015), then Cover (insurtech, 2016-2022, ~$30M raised). LinkedIn active at [linkedin.com/in/saroya](https://www.linkedin.com/in/saroya), X at [@karnsaroya](https://x.com/karnsaroya). Public conference speaker (ITC Vegas 2026, Oliver Wyman podcast). Strong, verifiable identity with insurance domain depth.


**Verify on-chain:**

```bash
https://www.linkedin.com/in/saroya
# → expect: Karn Saroya — Co-founder & CEO at Re; prior Cover, Stylekick
https://theorg.com/org/re-xyz/org-chart/karn-saroya
# → expect: Re org chart confirms Co-founder & CEO role
```

#### <span class="sev-badge sev-info">[INFO]</span> Co-founder Cliff White (VP Engineering) is fully doxxed with 9-year CTO track record at Kiteworks. {: .finding-header .finding-info }

White was CTO at Kiteworks (2011-2020), then VP Eng at Cover (2020-2023), now VP Eng & Co-founder at Re. LinkedIn at [linkedin.com/in/cliffawhite](https://www.linkedin.com/in/cliffawhite/). 15+ years in software — pairs with Saroya's domain expertise to give Re a credible technical-leadership stack.


**Verify on-chain:**

```bash
https://theorg.com/org/re-xyz/org-chart/cliff-white
# → expect: Cliff White — Co-Founder & VP Engineering, prior CTO Kiteworks
```

#### <span class="sev-badge sev-info">[INFO]</span> Tier-1 crypto VC backing — Electric Capital led Series A on top of $14M seed from Tribe, Framework, Morgan Creek, SiriusPoint, Exor. {: .finding-header .finding-info }

2022 seed of $14M (Tribe Capital, Framework Ventures, Morgan Creek Digital, SiriusPoint reinsurer, Exor Seeds, Stratos, Defy). Late-2024 ~$7M Series A led by Electric Capital. Reinsurer-side validation (SiriusPoint, Exor) is unusual — independent insurance-industry signal beyond crypto VCs.


**Verify on-chain:**

```bash
https://www.theblock.co/post/173386/karn-saroya-raises-14-million-for-insurance-protocol-re-as-insurtech-platform-cover-is-wound-down
# → expect: $14M seed lead investors named
https://beinsure.com/news/platform-re-tokenized-reinsurance-fund/
# → expect: Electric Capital Series A reported
```

#### <span class="sev-badge sev-info">[INFO]</span> Operates via licensed Cayman reinsurer CoverRe — regulated counterparty rather than purely DeFi-native risk. {: .finding-header .finding-info }

Docs state "Re Protocol operates in partnership with CoverRe.com, a Cayman-based licensed reinsurer" and capital is held in §114 trust accounts (US regulatory framework). Off-chain balances attested daily by The Network Firm via Chainlink. Real-world regulatory wrapping materially de-risks team-accountability concerns.


**Verify on-chain:**

```bash
https://docs.re.xyz/getting-started-with-re/introduction-to-the-re-protocol
# → expect: CoverRe Cayman-licensed reinsurer partnership
```

#### <span class="sev-badge sev-info">[INFO]</span> Resilience Foundation footer entity, but full corporate-stack disclosure is thin in public docs. {: .finding-header .finding-info }

re.xyz footer reads "Resilience Foundation ©2026" — typical foundation-wrapper pattern (Cayman foundation common for crypto). No public disclosure ties US operating entity, foundation, and CoverRe Cayman reinsurer into a labelled corporate diagram. Not a red flag given regulated reinsurer involvement, but reduces visibility into who legally controls protocol upgrades.


**Verify on-chain:**

```bash
https://re.xyz/
# → expect: Resilience Foundation copyright in footer
```


### 💧 Liquidity Depth  ·  score 4 / confidence 0.85 {: .agent-section .agent-liquidity-depth }

#### <span class="sev-badge sev-high">[HIGH]</span> Curve reUSD/USDC pool TVL is only ~$450K — caps at ~$221K USDC out before draining, far below typical liquidation chunk size {: .finding-header .finding-high }

The only direct reUSD->USDC venue is Curve StableSwap-NG pool 0xf74c91...8bf0 with reserves of 212,933 reUSD ($227K) and 221,268 USDC ($221K). On-chain get_dy: 100K reUSD->106K USDC (premium pricing), 250K reUSD->213.5K USDC (~15% slippage), 500K reUSD caps at 220.3K USDC (pool fully drained). Any liquidation >$250K must split across other venues.



**Verify on-chain:**

```bash
cast call 0xf74c91b36c26543a0aa820bef407a577e5498bf0 'balances(uint256)(uint256)' 1 --rpc-url $RPC
# → expect: ~221268487260 (221.3K USDC)
cast call 0xf74c91b36c26543a0aa820bef407a577e5498bf0 'get_dy(int128,int128,uint256)(uint256)' 0 1 250000000000000000000000 --rpc-url $RPC
# → expect: ~213563600340 (213.5K USDC out for 250K reUSD in)
```


**Key addresses:**

- Curve reUSD/USDC pool — [`0xf74c91b36c26543a0aa820bef407a577e5498bf0`](https://etherscan.io/address/0xf74c91b36c26543a0aa820bef407a577e5498bf0)
- reUSD — [`0x5086bf358635B81D8C47C66d1C8b9E567Db70c72`](https://etherscan.io/address/0x5086bf358635B81D8C47C66d1C8b9E567Db70c72)
- USDC — [`0xA0b86991c6218b36c1d19D4a2e9Eb0cE3606eB48`](https://etherscan.io/address/0xA0b86991c6218b36c1d19D4a2e9Eb0cE3606eB48)

#### <span class="sev-badge sev-high">[HIGH]</span> SY-reUSD does not accept USDC redeem — liquidator MUST flow PT->SY->reUSD->USDC, no shortcut via SY {: .finding-header .finding-high }

Despite the SY's assetInfo declaring USDC as the underlying asset (assetType=0, asset=USDC, decimals=6), getTokensIn/Out only return reUSD. previewRedeem(USDC, ...) reverts with InvalidTokenOut(USDC). Effective redeem path is SY->reUSD 1:1, then reUSD->USDC via DEX. Aggregators (1inch/0x/Odos) also do NOT accept PT-reUSD as an input — Fira's liquidator MUST implement the multi-hop path itself.



**Verify on-chain:**

```bash
cast call 0x9487Bd5A3b16Ecb5F3184453E3ee75B800141648 'getTokensOut()(address[])' --rpc-url $RPC
# → expect: [0x5086bf358635B81D8C47C66d1C8b9E567Db70c72] — only reUSD
cast call 0x9487Bd5A3b16Ecb5F3184453E3ee75B800141648 'previewRedeem(address,uint256)(uint256)' 0xA0b86991c6218b36c1d19D4a2e9Eb0cE3606eB48 1000000000000000000000 --rpc-url $RPC
# → expect: revert InvalidTokenOut(USDC)
```


**Key addresses:**

- SY-reUSD — [`0x9487Bd5A3b16Ecb5F3184453E3ee75B800141648`](https://etherscan.io/address/0x9487Bd5A3b16Ecb5F3184453E3ee75B800141648)
- PT-reUSD — [`0x3eaa0f0f0a5d3d595ae4e4b0d27f439d01c3e7b2`](https://etherscan.io/address/0x3eaa0f0f0a5d3d595ae4e4b0d27f439d01c3e7b2)

#### <span class="sev-badge sev-medium">[MEDIUM]</span> reUSD has no Uniswap V2/V3 pools — only 3 venues (Curve x2 + Fluid) with combined ~$13.5M reUSD-side TVL {: .finding-header .finding-medium }

All Uniswap V3 fee tiers (100/500/3000/10000) and V2 return zero pool addresses for reUSD/USDC. Discovered venues: Curve reUSD/USDC ($450K), Curve reUSD/sUSDe ($1.43M, requires sUSDe->USDC follow-on), Fluid DEX reUSD/USDT ($11.58M claimed, $2M 24h volume but smart-debt architecture obscures direct depth probing). Concentration risk in Fluid: a Fluid outage isolates the bulk of reUSD exit liquidity.



**Key addresses:**

- Curve reUSD/sUSDe — [`0x5C2ab69Eb2BF12A2f4572D178687Bd4660512972`](https://etherscan.io/address/0x5C2ab69Eb2BF12A2f4572D178687Bd4660512972)
- Fluid reUSD/USDT — [`0xb96cee75211700bc148b95b1c907d726791f4457`](https://etherscan.io/address/0xb96cee75211700bc148b95b1c907d726791f4457)

#### <span class="sev-badge sev-medium">[MEDIUM]</span> Pendle AMM PT pool holds only ~$1.07M of PT — a $1M+ liquidation in a single tx consumes most of the AMM and pushes severe slippage {: .finding-header .finding-medium }

Pendle market 0xf5929a... has 1,087,595 PT-reUSD ($1.073M @ $0.9863) and 4,307,816 SY (4.625M reUSD @ exchangeRate 1.075). RouterStatic.swapExactPtForSy: 250K PT -> 229,128 SY (clean), 500K PT -> 457,503 SY (~46% of pool, mild rate slip), 800K PT -> 730,709 SY (73% of pool — heavy slippage). Liquidations >$500K should be split across blocks.



**Verify on-chain:**

```bash
cast call 0xf5929a1c332ceab7918a4593a43db2b9ac20095f 'readTokens()(address,address,address)' --rpc-url $RPC
# → expect: (SY, PT, YT) tuple matching the configured trio
```


**Key addresses:**

- Pendle PT-reUSD market — [`0xf5929a1c332ceab7918a4593a43db2b9ac20095f`](https://etherscan.io/address/0xf5929a1c332ceab7918a4593a43db2b9ac20095f)

#### <span class="sev-badge sev-low">[LOW]</span> 54 days to expiry (25-Jun-2026) — post-expiry path eliminates Pendle AMM hop, falling back to PT->SY 1:1 burn via YieldContractFactory {: .finding-header .finding-low }

Expiry timestamp 1782345600. Post-expiry, PT redeems 1:1 to SY directly through YieldContractFactory.redeemPY, bypassing the Pendle AMM (no slippage on the PT leg). The bottleneck collapses entirely to reUSD->USDC depth. Pre-expiry liquidations during the next 54 days carry the dual-AMM risk; post-expiry simplifies to single-hop.


#### <span class="sev-badge sev-low">[LOW]</span> reUSD/USDC pool is currently underweight USDC (212.9K reUSD vs 221K USDC, A=50, fee=10bps) — already at disadvantageous price for sellers {: .finding-header .finding-low }

get_dy 100K reUSD -> 106.1K USDC (1.06 effective rate against $1.05 quoted) reflects pool imbalance favoring reUSD holders, but only at small sizes. Beyond ~200K reUSD, slippage ramps catastrophically as one side empties. Curve A=50 (low), fee=1e6 (10bps).


#### <span class="sev-badge sev-info">[INFO]</span> BT liquidity is irrelevant — fixed-rate market BT comes solely from LiquidityInjector; risk is on the underlying (reUSD->USDC) leg {: .finding-header .finding-info }

Per Fira's fixed-rate whitelist rule, BT supply is exclusively LI-injected (not market-traded). Liquidation cash flow runs USDC -> BT (via LI/Pendle-style market) -> repay debt; seized PT-reUSD is sold by the liquidator separately. Score reflects underlying-asset depth, not BT side.


#### <span class="sev-badge sev-info">[INFO]</span> reUSD market cap $155M, FDV $106M (CoinMarketCap) — token-level scale exists but is concentrated in protocol/integration holders rather than DEX float {: .finding-header .finding-info }

totalSupply=154.78M reUSD on a $155M FDV. Of that, only ~$13.5M is on-chain DEX float across the 3 venues — under 9% of supply. Most reUSD sits in protocol vaults/yield positions. Real-time exit liquidity scales with the float, not the cap.



### 🎭 Controversy  ·  score 4 / confidence 0.65 {: .agent-section .agent-controversy }

#### <span class="sev-badge sev-high">[HIGH]</span> reUSD's yield-stable + Pendle PT + Morpho looping architecture matches Stream Finance/xUSD pattern that collapsed November 2025 with ~$285M contagion {: .finding-header .finding-high }

Re's docs explicitly market reUSD as composable in Curve/Pendle/Morpho for recursive yield. Stream's xUSD used the same loop and collapsed Nov 4 2025: $93M founder misappropriation cascaded to $285M debt across Morpho/Euler/Silo, $1B DeFi outflows ([BlockEden](https://blockeden.xyz/blog/2025/11/08/m-defi-contagion/), [QuillAudits](https://x.com/QuillAudits_AI/status/1986377632926273796)).


**Verify on-chain:**

```bash
https://docs.re.xyz/insurance-capital-layers/what-is-reusd
# → expect: Find statement that reUSD is 'compatible with Curve, Pendle, and Morpho' as collateral for recursive use.
https://thedefiant.io/news/defi/how-stream-finance-s-collapse-exposed-defi-s-looping-yield-bubble
# → expect: Confirm Stream xUSD used identical Pendle PT + Morpho looping, collapsed November 2025.
```

#### <span class="sev-badge sev-high">[HIGH]</span> Re Protocol smart contracts are NOT open-source on GitHub — github.com/re-protocol only hosts forks of public DeFi tooling, no proprietary core repos. {: .finding-header .finding-high }

Repos at [github.com/re-protocol](https://github.com/re-protocol) are 3 forks (DefiLlama-Adapters, curve-frontend, curve-assets); no proprietary core contracts published. Contracts are Etherscan-verified and audited by Hacken (Aug 2024) + Certora, but external review is gated. Conflicts with user's oracle-EOA seed since role-holders can't be cross-checked vs public source.


**Verify on-chain:**

```bash
https://github.com/re-protocol
# → expect: Confirm only DefiLlama-Adapters, curve-frontend, curve-assets repos exist — all forks, none containing reUSD/oracle source.
https://etherscan.io/address/0xb5276c436f65913cd5332de745d04fedeb4a21d4#code
# → expect: Implementation source is verified on Etherscan as `ShareToken` ERC1967 proxy — confirms the only public source channel is post-deployment Etherscan verification, not a public repo.
```

#### <span class="sev-badge sev-high">[HIGH]</span> User-supplied controversy seed: oracle posting controlled by EOA — UNCONFIRMED but plausible given closed-source contracts + audit-flagged centralization {: .finding-header .finding-high }

User reports rumor oracle is updated by an EOA. Docs claim 'critical controls (oracle config) operated through MPC multi-sig' ([docs.re.xyz](https://docs.re.xyz)) but daily attestation poster identity not publicly disclosed. Hacken Aug 2024 flagged 3 oracle medium findings + 'minting/burning concentrated in a single address' ([Hacken](https://hacken.io/audits/re-protocol/sca-re-re-defi-aug2024/)).


**Verify on-chain:**

```bash
Coordinate with governance-security agent — they should read role-holders on-chain via cast and confirm whether the daily oracle poster is an EOA or multisig.
# → expect: If the address that calls the daily attestation function is a 1-of-N or single-key EOA, escalate this finding to critical and the score drops to 2.
```

#### <span class="sev-badge sev-medium">[MEDIUM]</span> reUSD trading at ~$1.07 on RWA.xyz despite being marketed as 'principal-protected, $1.00 NAV' — 7.35% premium is anomalous for a stable {: .finding-header .finding-medium }

RWA.xyz shows reUSD at $1.0735 vs $1.00 NAV ([app.rwa.xyz/assets/reUSD](https://app.rwa.xyz/assets/reUSD)). For a 'principal-protected' yield-accruing token this could just be accrued interest baked into price (rebase-via-share style), but the docs frame reUSD as a $1-pegged deposit token. Pricing source ambiguity is a collateral risk — Fira's oracle must price it correctly or risk over-borrow.


**Verify on-chain:**

```bash
https://app.rwa.xyz/assets/reUSD
# → expect: Confirm $1.0735 spot vs $1.00 NAV reading, plus 30-day MAU -29.09% and transfer volume -32.18% — declining engagement on a 10-month-old product.
```

#### <span class="sev-badge sev-medium">[MEDIUM]</span> Direct dependency on Ethena basis-trade yield, which experienced ~50% TVL contraction Nov 2025 ($14.8B → $7.6B) {: .finding-header .finding-medium }

reUSD yield = max(RF + 250bps, Ethena basis-trade + 250bps) ([docs.re.xyz](https://docs.re.xyz/insurance-capital-layers/what-is-reusd)). USDe supply contracted ~$2.26B in Nov 2025 amid Pendle maturity volatility ([Ethena gov](https://gov.ethenafoundation.com/t/reserve-fund-subcommittee-november-2025-update/727)). If basis collapses, yield drops to RF+250bps — marketing hides this.


**Verify on-chain:**

```bash
https://gov.ethenafoundation.com/t/reserve-fund-subcommittee-november-2025-update/727
# → expect: Confirm Ethena's Nov 2025 stress event with material USDe redemptions.
```

#### <span class="sev-badge sev-medium">[MEDIUM]</span> Recent product launch (June 2025), only 628 holders, declining engagement — minimal stress-test history {: .finding-header .finding-medium }

Etherscan shows reUSD deployed mid-2025 with 628 holders ([etherscan](https://etherscan.io/token/0x5086bf358635b81d8c47c66d1c8b9e567db70c72)). RWA.xyz inception 2025-06-12, ~10 months operational. Has never seen a market stress event as collateral. Fira would be effectively first-mover risk on a thin holder base.


**Verify on-chain:**

```bash
https://etherscan.io/token/0x5086bf358635b81d8c47c66d1c8b9e567db70c72
# → expect: 628 holders, ~$157M supply, narrow concentration.
```

#### <span class="sev-badge sev-medium">[MEDIUM]</span> Liquidity buffer redemption model: when 50% on-chain buffer is exhausted, reUSD redemptions queue (slow, quarterly-style) — peg risk in stress {: .finding-header .finding-medium }

Per [Re docs](https://docs.re.xyz/protocol/redemption-process-and-liquidity): instant atomic redemption only while buffer holds; once exhausted, requests queue 'until capacity is replenished'. Under correlated DeFi stress (Stream-style cascade), buffer depletes fast and reUSD becomes a discounted secondary product — same failure mode that took xUSD from $1 → $0.23.


**Verify on-chain:**

```bash
https://app.re.xyz/transparency
# → expect: Live buffer-utilisation %; if >70% in normal market conditions, this is a red flag for a stress event.
```

#### <span class="sev-badge sev-medium">[MEDIUM]</span> Issuer is BVI-domiciled (Resilience BVI Ltd.) — offshore wrapper around U.S.-licensed reinsurer, jurisdictional ambiguity for Fira lenders' recourse {: .finding-header .finding-medium }

RWA.xyz lists Resilience BVI Ltd. as the issuing entity ([app.rwa.xyz/assets/reUSD](https://app.rwa.xyz/assets/reUSD)). BVI is standard for crypto-RWA wrappers but provides no investor-protection regime; if an off-chain counterparty defaults, on-chain holders rely on BVI court enforcement against U.S. trust assets. Not unusual, but worth flagging for an institutional collateral listing.


**Verify on-chain:**

```bash
https://app.rwa.xyz/assets/reUSD
# → expect: Confirm Resilience BVI Ltd. listed as issuer, BVI domicile.
```

#### <span class="sev-badge sev-low">[LOW]</span> Founder Karn Saroya's prior insurtech (Cover) wound down June 2022 — strategic failure, not a rug ($27M raised, no fraud or regulatory action). {: .finding-header .finding-low }

Cover raised $27M from Tribe Capital, Exor, Sand Hill Angels and shut down June 2022 after failing to find acquirer despite 'underwriting profitably' via 5000 agencies ([The Block](https://www.theblock.co/post/173386/karn-saroya-raises-14-million-for-insurance-protocol-re-as-insurtech-platform-cover-is-wound-down)). No fraud or regulatory action. Saroya then raised $14M for Re via same Tribe.


**Verify on-chain:**

```bash
https://www.theblock.co/post/173386/karn-saroya-raises-14-million-for-insurance-protocol-re-as-insurtech-platform-cover-is-wound-down
# → expect: Confirm Cover wound down June 2022, no allegations of misconduct, Saroya raised Re seed shortly after.
```

#### <span class="sev-badge sev-info">[INFO]</span> Investor Arjun Sethi (Tribe Capital, Re seed) is now Kraken Co-CEO — press flagged conflict-of-interest narrative, but no enforcement action. {: .finding-header .finding-info }

Sethi joined Re's seed round via Tribe Capital, became Kraken Co-CEO Oct 2024. Fortune (2025-09-26) and former Kraken execs raised conflict-of-interest concerns about him simultaneously chairing Tribe and running Kraken ([Fortune](https://fortune.com/2025/09/26/when-your-vc-is-your-ceo/)). No SEC/CFTC action, no Re-specific impact. Reputational background only.


**Verify on-chain:**

```bash
https://fortune.com/2025/09/26/when-your-vc-is-your-ceo/
# → expect: Coverage of Sethi's dual Tribe/Kraken roles and the conflict-of-interest narrative — no enforcement action, just press critique.
```


## Inputs used for this assessment

- **RPC chain:** unspecified (URL redacted)
- **Docs:** https://docs.re.xyz/, https://docs.google.com/document/d/1scFGYwSprKuvDHMvO-q_qIwxCcT5BMlW/edit
- **Repos:** https://github.com/re-protocol
- **Controversy seeds:** "Oracle update is rumored to be controlled or updated by just an EOA — need to verify governance of every oracle / price feed reUSD depends on. Also do independent search for team / regulatory / depeg / dependency controversy."
- **Asset address:** `0x5086bf358635B81D8C47C66d1C8b9E567Db70c72`
- **Market type:** fixed
- **Assessment date:** 2026-05-01
