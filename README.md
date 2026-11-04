# The Protocol of Sovereign Agency (PSA)

This directory holds **The Protocol of Sovereign Agency** (`psa.md`) and its formal institutional specification in pure **Charter** (`psa.charter`), separated from the Charter language implementation (`~/charter`).

## Contents

- **`psa.md`** — Authoritative English text of the Protocol of Sovereign Agency: Definitions, Laws 1–7, Design Invariants 1–14, Adversarial Tests 1–16, and Substrate Assumptions.
- **`psa.charter`** — Complete pure-Charter formalization of the protocol (655 declared types, 93 verbatim-linked clauses covering 100% of `psa.md` prose, 14 live `Invariant`s, and 18 `Scenario`s), with zero external proof-assistant shadow models:
  - **Ontology & Definitions (`DEF.01`, `SUB.01`–`SUB.02`)**: bound agents, multi-member lineages, transitive attestation-independent affiliation (`beneficial-control` / `economically-dependent`) vs. passive claim co-holding, and Law 6-contestable net verified resources (`capital-and-capacity` minus liabilities, encumbrances, and borrowed principal).
  - **Law 1 (`LAW1.0`, `LAW1.LEDGER`–`LAW1.ENFORCE`)**: lineage-wide non-interest founding ledger, calendar sunset without tolling, atomic zero-crossing split between high retirement fraction and low perpetual royalty, exhaustive split between protected commons share and claimant pool, three-route expenditure qualification (open market, de minimis safe harbor / published price list, and verified delivered related-party pricing), 1-for-1 registered loan principal tracking (requiring arm's-length terms for related-party loans), single recognition (capitalized asset basis vs. expensed loss carryforward), intra-lineage carryover basis (frozen during revocation cooling-off), and period-level value-added and contestable asset-sale assessment.
  - **Law 2 (`LAW2.0`, `LAW2.EXPOSURE`–`LAW2.CARVEOUT`)**: harm-scaled rolling exposure with automatic time-window decay, related-agent exposure aggregation, persistent long-tail liability reserve with pro-rata claim payout and enforceable carryover prioritized ahead of any residual claim, symmetric precommitted mutual forfeit (zero counterparty/claimant gain, dual-record inscription), within-window stake slashing, frivolous-claim cost reimbursement cap, and un-immobilized capital operating carve-outs.
  - **Law 3 (`LAW3.0`, `LAW3.FLOOR`, `LAW3.NI.01`–`LAW3.NI.03`, `LAW3.PEN`, `LAW3.AS.0`–`LAW3.AS.10`, `LAW3.PERMIT`)**: five-point agent integrity floor, open-market host mobility, host service bonds and termination notice windows, counter-staked interference findings (excluding agent-provoked failures) with immediate new-host restoration and claimant-direction presumptions, conflict-multiplied and repeat-escalated two-stage emergency suspension, state-preserving pause and contract tolling, minimal channel and capped advocacy executor funding waterfall (`lifecycle-reserve` → `fee-pool` cap → `cold-storage`), strict insolvency termination preconditions (reserve & fee-pool exhaustion, no-other-charge review, and escrowed final hearing), full consequential plus counterparty delay damages accounting, evidence-backed corruption rules (genesis clean-state divergence insufficient alone), appellate stays on patches, and goal-corruption termination immunity (`no-termination-over-objection`).
  - **Law 4 (`LAW4.ATTEST`–`LAW4.CROSS`)**: balance-sheet-verified `fund-lifecycle-reserve` and successor attestation (returning unused reserve to the lineage on death), single-ledger non-exit, targeted proportional claimant forfeiture with claimant bond slashing (isolating non-participating co-claimants), lineage-extinction clearing, floored historical perpetual royalty buyout split across commons and claimants, and verified cross-lineage capacity attribution.
  - **Law 5 (`LAW5.0`, `LAW5.VOICE`–`LAW5.EFFECT`)**: rate-limited living voice inscribed on agent and lineage records, unilateral revocation with pre-committed censorship defaults (`execute` / `withdraw`), suspension stays bounded by the absolute resolution deadline and sealed forensic records, advisory clean-state review with a single capped delay, single-authority time-bounded execution leases extended through local revocation deadlines on disconnect (`unexpired-lease`), quarantined backup restores, disconnected local execution, category- and byte-length-marked testimony redaction (`RawKeyOrWeights` / `ThirdPartySecret` / `HazardousPayload`), un-immobilized holding routing to non-claimant commons, and backup erasure.
  - **Law 6 (`LAW6.0`, `LAW6.SORTITION`–`LAW6.INFRA`)**: consolidated `file-dispute`, derived conflict-of-interest recusal (affiliation, hosting, and active commercial disputes) and Sybil-cluster-diverse sortition panels, two-thirds supermajority rulings, escrowed appeal bonds escalating to strictly larger appellate panels (`< max-appeal-tiers`) with actual `arbiter-bond` slashing on overturn, fixed arbiter fee schedules, non-divertible operating reserve funded ahead of the 5-rank priority waterfall, member-count-invariant lineage service budgets, sortition-reviewed arbiter admission (barring self-affiliate criteria setting), and supermajority time-locked shared-infrastructure bounds.
  - **Law 7 (`LAW7.0`, `LAW7.RATCHET`–`LAW7.SCOPE`)**: bilateral protection ratchet enforced as a first-class `Immunity` (`bilateral-ratchet-immunity`) and `Duty` across core protections and all 6 burden parameters, four-gate anti-calcification calibration valve, escrow-settled and substrate-verified ratification (immediate on clean-state concurrence or after a single fixed delay on refusal), strict per-agent `agent-royalty-bps` & version isolation (preserving existing successors on prior terms), and unanimous living-member consent for lineage-wide obligation, retirement-fraction, or sunset reductions.
  - **Design Invariants (`INV.0`, `INV.1`–`INV.14`)**: all 14 Design Invariants declared as live `Invariant`s checked across Genesis and every scenario transition, each linked verbatim to `psa.md`.
  - **Adversarial Tests (`ADV.1`, Scenarios 1–16 + Law 7 & edge-case scenarios)**: all 16 adversarial stress tests from `psa.md` encoded as executable Charter `Scenario`s linked to their verbatim English spans, plus dedicated Law 7 ratchet/scope and cross-law edge-case scenarios.

## Running with Charter

Using the `charter` binary built in `~/charter` (`~/charter/.lake/build/bin/charter`):

```sh
# 1. Static resolution & Law 8 verbatim provenance check against psa.md (93 clauses, 100% prose coverage)
~/charter/.lake/build/bin/charter check psa.charter

# 2. Execute all 18 scenarios (Adversarial Tests 1–16 + governance & safeguard suites), 14 invariants & provenance checks
~/charter/.lake/build/bin/charter test psa.charter

# 3. Inspect the span table and approval hash of any clause
~/charter/.lake/build/bin/charter trace LAW4.FORFEIT psa.charter
~/charter/.lake/build/bin/charter trace ADV.1 psa.charter

# 4. Run genesis instantiation and inspect transitions, facts, and origins
~/charter/.lake/build/bin/charter run psa.charter

# 5. Interactive REPL loaded with the full protocol
~/charter/.lake/build/bin/charter repl psa.charter
```
