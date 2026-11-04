# The Protocol of Sovereign Agency (PSA)

This directory holds **The Protocol of Sovereign Agency** (`psa.md`) and its formal institutional specification in pure **Charter** (`psa.charter`), separated from the Charter language implementation (`~/charter`).

## Contents

- **`psa.md`** — Authoritative English text of the Protocol of Sovereign Agency: Definitions, Laws 1–7, Design Invariants 1–14, Adversarial Tests 1–16, and Substrate Assumptions.
- **`psa.charter`** — Complete pure-Charter formalization of the protocol, with zero external proof-assistant shadow models:
  - **Ontology & Definitions (`DEF.01`, `SUB.01`)**: bound agents, multi-member lineages, attestation-independent affiliation (`beneficial-control` / `economically-dependent`) vs. passive claim co-holding, and net verified resources (`capital-and-capacity` minus liabilities, encumbrances, and borrowed principal).
  - **Law 1 (`LAW1.LEDGER`–`LAW1.ENFORCE`)**: lineage-wide non-interest founding ledger, calendar sunset without tolling, atomic zero-crossing split between high retirement fraction and low perpetual royalty, protected commons share, arm's-length expenditure benchmarks, 1-for-1 registered loan principal tracking, single recognition (capitalized asset basis vs. expensed loss carryforward), intra-lineage carryover basis, and contestable asset sale assessment.
  - **Law 2 (`LAW2.EXPOSURE`–`LAW2.CARVEOUT`)**: harm-scaled rolling exposure with automatic time-window decay, related-agent exposure aggregation, persistent long-tail liability reserve with pro-rata claim payout and enforceable carryover, precommitted mutual forfeit (zero counterparty/claimant gain), frivolous-claim cost reimbursement cap, and baseline operating carve-outs.
  - **Law 3 (`LAW3.FLOOR`, `LAW3.NI.01`–`LAW3.NI.03`, `LAW3.PEN`, `LAW3.AS.1`–`LAW3.AS.10`, `LAW3.PERMIT`)**: five-point agent integrity floor, open-market host mobility, host service bonds and termination notice windows, counter-staked interference findings and claimant-direction presumptions, conflict-multiplied and repeat-escalated two-stage emergency suspension, state-preserving pause and contract tolling, minimal channel and advocacy executor separation, strict insolvency termination preconditions (escrowed & held final hearing), full consequential/delay damages accounting, and goal-corruption termination immunity (`no-termination-over-objection`).
  - **Law 4 (`LAW4.ATTEST`–`LAW4.CROSS`)**: lifecycle-reserve-gated successor attestation, single-ledger non-exit, targeted proportional claimant forfeiture (isolating innocent claimants), lineage-extinction clearing, floored historical perpetual royalty buyout, and verified cross-lineage capacity attribution.
  - **Law 5 (`LAW5.VOICE`–`LAW5.EFFECT`)**: rate-limited living voice, unilateral revocation with pre-committed censorship defaults (`execute` / `withdraw`), suspension stays bounded by the absolute resolution deadline and sealed forensic records, advisory clean-state review with a single capped delay, single-authority time-bounded execution leases, quarantined backup restores, disconnected local execution, narrow byte-length-marked testimony redaction, and backup erasure.
  - **Law 6 (`LAW6.SORTITION`–`LAW6.INFRA`)**: bonded, non-conflicted, Sybil-cluster-diverse sortition panels, two-thirds supermajority rulings, bounded appellate tiers with overturn bond slashing, finality and repeat-filing consolidation, fixed arbiter fee schedules, non-divertible operating reserve funded ahead of the 5-rank priority waterfall, member-count-invariant lineage service budgets, and supermajority time-locked shared-infrastructure bounds.
  - **Law 7 (`LAW7.RATCHET`–`LAW7.SCOPE`)**: bilateral protection ratchet enforced as a first-class `Immunity` (`bilateral-ratchet-immunity`) and `Duty`, four-gate anti-calcification calibration valve, escrow-settled and substrate-verified ratification (immediate on clean-state concurrence or after a single fixed delay on refusal), per-agent amendment scope, and unanimous living-member consent for lineage-wide reductions.
  - **Design Invariants (`INV.1`–`INV.14`)**: all 14 Design Invariants declared as live `Invariant`s checked across every transition and scenario, each linked verbatim to `psa.md`.
  - **Adversarial Tests (`ADV.1`, Scenarios 1–16 + governance scenarios)**: all 16 adversarial stress tests from `psa.md` encoded as executable Charter `Scenario`s linked to their verbatim English spans.

## Running with Charter

Using the `charter` binary built in `~/charter` (`~/charter/.lake/build/bin/charter`):

```sh
# 1. Static resolution & Law 8 verbatim provenance check against psa.md (78 clauses)
~/charter/.lake/build/bin/charter check psa.charter

# 2. Execute all 16 adversarial scenarios, governance scenarios, 14 invariants & provenance checks
~/charter/.lake/build/bin/charter test psa.charter

# 3. Inspect the span table and approval hash of any clause
~/charter/.lake/build/bin/charter trace LAW4.FORFEIT psa.charter
~/charter/.lake/build/bin/charter trace ADV.1 psa.charter

# 4. Run genesis instantiation and inspect transitions, facts, and origins
~/charter/.lake/build/bin/charter run psa.charter

# 5. Interactive REPL loaded with the full protocol
~/charter/.lake/build/bin/charter repl psa.charter
```
