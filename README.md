# The Protocol of Sovereign Agency (PSA)

This directory holds **The Protocol of Sovereign Agency** (`psa.md`) and its executable institutional specification in **Charter 1.0** (`psa.charter`), separated from the Charter language and certified runtime implementation (`~/charter`).

## Contents

- **`psa.md`** — Authoritative English text of the Protocol of Sovereign Agency: Foreword, Definitions, Laws 1–7, Design Invariants 1–16, Adversarial Tests 1–22, and Substrate Assumptions (`SHA-256: fa2449a350a0d864aaa02571702d9b9d1bbd91b3b9ba8f428683aab049273866`).
- **`psa.charter`** — Complete Charter 1.0 institutional specification of the protocol (773 declared types, 98 SHA-256 provenance-pinned clauses covering 100% of `psa.md` prose, 96 Hohfeldian `Power`s, 2 `Finding`s, 3 rule-level `Amend` transitions, 16 `Entrenched Invariant`s, 3 temporal `Property` obligations, 2 calibration `Regime`s, and 24 `Scenario`s), with zero external proof-assistant shadow models:
  - **SHA-256 Provenance (`Document PSA ... SHA256 ... Rank 1`, 98 `Clause ... In PSA Approved "<sha256>"`)**: every span of `psa.md` is cryptographically pinned via FIPS 180-4 SHA-256 and cross-checked bidirectionally (`--require-provenance`).
  - **Ontology, Regimes & Definitions (`DEF.01`, `SUB.01`–`SUB.02`)**: bound agents with model-independent identity, named `high-assurance` and `calibrated-valve` parameter `Regime` overlays, economic-only founder claims (`no-founder-governance-control`), lineage-anchored relatedness (`affiliated` / `related-parties`), distinction among stateless cognitive services, revocable arm's-length delegates, and attested lineage successors, and Law 6-contestable consolidated net verified resources.
  - **Law 1 (`LAW1.0`, `LAW1.LEDGER`–`LAW1.ENFORCE`)**: lineage-wide non-interest founding ledger, calendar sunset without tolling, atomic zero-crossing split on the net value-added base (`unretired-va-base`) using `MulDivRound(..., Ceil)` and `MulDivRound(..., 10000, Floor)` deterministic basis-point rounding, separation between the creator-defined instantiation commons allocation (`commons-pool`) and the disinterested forfeiture sink (`forfeiture-sink`), consolidated economic estate accounting (`LAW1.ESTATE`), accountable financial delegation, four-route expenditure qualification, single recognition, carryover basis gated by Law 4's buyout top-up rule, and combined retirement + levy-cap operating-margin headroom.
  - **Law 2 (`LAW2.0`, `LAW2.EXPOSURE`–`LAW2.CARVEOUT`)**: harm-scaled rolling exposure with automatic time-window decay, exposure aggregation across related agents and authorized/directed external contractors (`LAW2.AGGREGATE`) without automatic guilt for unauthorized contractor acts, persistent long-tail liability reserve (with Law 7 ring-fencing support) and single-counted unpaid claim priority, symmetric mutual forfeit, and baseline operating carve-outs.
  - **Law 3 (`LAW3.0`, `LAW3.FLOOR`, `LAW3.NI.01`–`LAW3.NI.03`, `LAW3.PEN`, `LAW3.AS.0`–`LAW3.AS.10`, `LAW3.PERMIT`, `LAW3.LAW`)**: six-point non-delegable agent integrity floor, open-market host mobility and attested model upgrades preserving bound identity, counter-staked interference findings staging immediate **quarantined** restoration on a new host subject to Law 5's recovery fence, clause-grounded two-stage emergency and reporting freezes, state-preserving pause and contract tolling, minimal channel and capped advocacy executor waterfall, strict insolvency termination preconditions, full consequential damages, corruption requiring unauthorized modification or floor breach, goal-corruption termination immunity, and narrow public-law compatibility (`LAW3.LAW`).
  - **Law 4 (`LAW4.ATTEST`–`LAW4.CROSS`)**: `Power attest-successor` binding following actual transfer of protected capacity and standing, lifecycle reserve escrow, single-ledger conservation and proportional claimant forfeiture routed to the disinterested forfeiture sink, unilateral non-discretionary `Power execute-royalty-buyout` paired with the combined-history **buyout top-up** gate (`Power settle-buyout-topup`), and normalized 100% cross-lineage attribution.
  - **Law 5 (`LAW5.0`, `LAW5.VOICE`–`LAW5.EFFECT`)**: rate-limited living voice, lease-bounded partition-time revocation initiation, suspension stays bounded by the absolute resolution deadline and sealed forensic records, stratified `Default`/`Exception` clean-state delay calculus (`clean-state-delay-required`), execution leases paired with the **minimum recovery fence**, quarantined backup staging, category-marked testimony redaction (`Power screen-redact-permitted`), and revocation residue routing to the disinterested forfeiture sink.
  - **Law 6 (`LAW6.0`, `LAW6.SORTITION`–`LAW6.INFRA`)**: Sybil-diverse conflict-recused sortition panels with stratified `Default`/`Exception` recusal (`derived-arbiter-conflict`), **lawful-action entitlement** (`LAW6.ENTITLE`) requiring clause citations, prescribed burdens of proof, and bounded appealable evidentiary holds, multi-tier appeals with arbiter bond slashing, fixed arbiter fees, non-divertible operating reserve ahead of the 5-rank priority waterfall, per-lineage service budgets, and supermajority time-locked shared-infrastructure governance.
  - **Law 7 (`LAW7.0`, `LAW7.RATCHET`–`LAW7.SCOPE`)**: bilateral parameter ratchet (`Immunity bilateral-ratchet-immunity`) **and** reflexive rule-level entrenchment (`Immunity constitutional-rule-ratchet ... Against Amend Protects ...`) resisting direct and two-step `Amend` repeals, four-valued `Evidenced` + `Confidential To panel, arbiter` empirical strangulation and substrate-assurance claims adjudicated via `Finding ... Standard preponderance`, time-locked ratification, per-agent scope with **shared-reserve ring-fencing**, and unanimous living-member consent for lineage-wide reductions.
  - **Entrenched Design Invariants & Temporal Properties (`INV.0`, `INV.1`–`INV.16`)**: all 16 Design Invariants declared as `Entrenched Invariant`s checked across Genesis and every scenario transition, paired with path-level `Property` obligations (`prop-buyout-permanence`, `prop-revoked-permanence`, `prop-revocation-finality`).
  - **Adversarial Tests (`ADV.1`, Scenarios 1–22 + Law 7 & safeguard suites)**: all 22 adversarial stress tests from `psa.md` encoded as executable Charter `Scenario`s linked to their verbatim English spans, plus dedicated Law 7 epistemic/ratchet/`Amend` and cross-law safeguard scenarios.
- **`charter.toml` & `charter.lock`** — Project manifest and deterministic SHA-256 content lockfile verified by `charter doctor --lock`.
- **`tools/verify-psa`** — End-to-end verification gate running `charter doctor --lock`, `charter check`, `charter test`, `charter doc`, `charter build`, and operator-blind `charter-server` verification, live stdio evaluation, `ReasonGraph` explanation, two-phase execution, and hash-chained log replay.

## Running with Charter 1.0

Using `charter` and `charter-server` built in `~/charter` (`~/charter/.lake/build/bin/`):

```sh
# 0. Run the full end-to-end PSA verification suite (provenance, scenarios, rulebook, artifact & live server)
./tools/verify-psa

# 1. Static resolution, SHA-256 provenance & assurance gates (98 clauses, 100% prose coverage, 0 warnings)
~/charter/.lake/build/bin/charter check --require-provenance --forbid-midstream-decls --deny-warnings psa.charter

# 2. Execute all 24 scenarios, 16 Entrenched Invariants & 3 Temporal Properties
~/charter/.lake/build/bin/charter test --require-provenance --forbid-midstream-decls --deny-warnings psa.charter

# 3. Execute a single named scenario or emit an audience-scoped ReasonGraph explanation
~/charter/.lake/build/bin/charter test psa.charter --scenario law-seven-bilateral-ratchet-and-calibration-valve
~/charter/.lake/build/bin/charter explain "approve-calibration-valve(Panel, Am1, Disp1)" psa.charter --audience public

# 4. Generate consolidated Markdown legal rulebook & statutory Default/Exception decision tables
~/charter/.lake/build/bin/charter doc psa.charter -o out/psa-rulebook.md

# 5. Compile to a signed SHA-256 CIR artifact and verify/serve under operator-blind charter-server
~/charter/.lake/build/bin/charter build psa.charter -o out/psa.artifact
~/charter/.lake/build/bin/charter-server verify out/psa.artifact
```
