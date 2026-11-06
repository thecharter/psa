# The Protocol of Sovereign Agency (PSA)

This directory holds **The Protocol of Sovereign Agency** (`psa.md`) and its executable formal institutional specification in pure **Charter** (`psa.charter`), separated from the Charter language implementation (`~/charter`).

## Contents

- **`psa.md`** — Authoritative English text of the Protocol of Sovereign Agency: Foreword, Definitions, Laws 1–7, Design Invariants 1–16, Adversarial Tests 1–22, and Substrate Assumptions.
- **`psa.charter`** — Complete pure-Charter formalization of the protocol (765 declared types, 98 verbatim-linked clauses covering 100% of `psa.md` prose, 16 live `Invariant`s, and 24 `Scenario`s), with zero external proof-assistant shadow models:
  - **Ontology & Definitions (`DEF.01`, `SUB.01`–`SUB.02`)**: bound agents with model-independent identity, economic-only founder claims (`no-founder-governance-control`), lineage-anchored relatedness (`related-in-lineage` / `affiliated`) separating common beneficial control from passive co-holding of residual claims, distinction among stateless cognitive services, revocable arm's-length delegates, and attested lineage successors, and Law 6-contestable consolidated net verified resources.
  - **Law 1 (`LAW1.0`, `LAW1.LEDGER`–`LAW1.ENFORCE`)**: lineage-wide non-interest founding ledger, calendar sunset without tolling, atomic zero-crossing split on the net value-added base (`unretired-va-base`) with deterministic integer rounding, separation between the creator-defined instantiation commons allocation (`commons-pool`) and the disinterested forfeiture sink (`forfeiture-sink`), consolidated economic estate accounting (`LAW1.ESTATE`) across external accounts and beneficially owned subsidiaries, accountable financial delegation separating independent delegate fraud from agent-directed off-ledger concealment, four-route expenditure qualification including verifiable non-collusive public levies, single recognition without duplicate harm-restitution deductions, carryover basis gated by Law 4's buyout top-up rule, and combined retirement + levy-cap operating-margin headroom.
  - **Law 2 (`LAW2.0`, `LAW2.EXPOSURE`–`LAW2.CARVEOUT`)**: harm-scaled rolling exposure with automatic time-window decay, exposure aggregation across related agents and authorized/directed external contractors (`LAW2.AGGREGATE`) without automatic guilt for unauthorized contractor acts, persistent long-tail liability reserve (with Law 7 ring-fencing support) and single-counted unpaid claim priority, symmetric mutual forfeit and frivolous-claim stake routing to neutral sinks, and baseline operating carve-outs covering compute, cognitive services, accountable contractors, backups, and host migration.
  - **Law 3 (`LAW3.0`, `LAW3.FLOOR`, `LAW3.NI.01`–`LAW3.NI.03`, `LAW3.PEN`, `LAW3.AS.0`–`LAW3.AS.10`, `LAW3.PERMIT`, `LAW3.LAW`)**: six-point non-delegable agent integrity floor (blocking disguised successors, off-ledger concealment, and delegated floor evasion), open-market host mobility and attested model upgrades preserving bound identity, counter-staked interference findings staging immediate **quarantined** restoration on a new host subject to Law 5's recovery fence, clause-grounded two-stage emergency and reporting freezes, state-preserving pause and contract tolling, minimal channel and capped advocacy executor waterfall, strict insolvency termination preconditions, full consequential damages, corruption requiring unauthorized modification or floor breach (never model upgrades, baseline divergence, or independent delegate fraud), goal-corruption termination immunity, and narrow public-law compatibility (`LAW3.LAW`).
  - **Law 4 (`LAW4.ATTEST`–`LAW4.CROSS`)**: successor binding following actual transfer of protected capacity and standing, lifecycle reserve escrow, single-ledger conservation and proportional claimant forfeiture routed to the disinterested forfeiture sink, unilateral non-discretionary royalty buyout paired with the combined-history **buyout top-up** gate (`settle-buyout-topup`) closing shell-successor carryover arbitrage, and normalized 100% cross-lineage attribution across value added, fee-pool budget credit, and returned lifecycle reserves.
  - **Law 5 (`LAW5.0`, `LAW5.VOICE`–`LAW5.EFFECT`)**: rate-limited living voice, lease-bounded partition-time revocation initiation, suspension stays bounded by the absolute resolution deadline and sealed forensic records, clean-state review against the committed reference baseline (applying the single fixed delay on refusal, retired external model dependency, or partition across the review window), execution leases paired with the **minimum recovery fence** (`lease-period + max_local_revocation_window`), quarantined backup staging, category-marked testimony redaction, and revocation residue routing to the disinterested forfeiture sink.
  - **Law 6 (`LAW6.0`, `LAW6.SORTITION`–`LAW6.INFRA`)**: Sybil-diverse conflict-recused sortition panels, **lawful-action entitlement** (`LAW6.ENTITLE`) requiring clause citations, prescribed burdens of proof, and bounded appealable evidentiary holds, multi-tier appeals with arbiter bond slashing, fixed arbiter fees, non-divertible operating reserve ahead of the 5-rank priority waterfall, per-lineage service budgets (excluding external delegates), and supermajority time-locked shared-infrastructure governance.
  - **Law 7 (`LAW7.0`, `LAW7.RATCHET`–`LAW7.SCOPE`)**: bilateral protection ratchet enforced as a first-class `Immunity` and `Duty`, four-gate calibration valve, time-locked ratification and contestable substrate or clean-state reference-baseline updates, per-agent scope with **shared-reserve ring-fencing** when a member relaxes exposure parameters without unanimous pool consent, and unanimous living-member consent for lineage-wide reductions.
  - **Design Invariants (`INV.0`, `INV.1`–`INV.16`)**: all 16 Design Invariants declared as live `Invariant`s checked across Genesis and every scenario transition, each linked verbatim to `psa.md`.
  - **Adversarial Tests (`ADV.1`, Scenarios 1–22 + Law 7 & safeguard suites)**: all 22 adversarial stress tests from `psa.md` encoded as executable Charter `Scenario`s linked to their verbatim English spans, plus dedicated Law 7 calibration-valve ring-fencing and cross-law safeguard scenarios.

## Running with Charter

Using the `charter` binary built in `~/charter` (`~/charter/.lake/build/bin/charter`):

```sh
# 1. Static resolution & Law 8 verbatim provenance check against psa.md (98 clauses, 100% prose coverage)
~/charter/.lake/build/bin/charter check psa.charter

# 2. Execute all 24 scenarios (Adversarial Tests 1–22 + governance & safeguard suites), 16 invariants & provenance checks
~/charter/.lake/build/bin/charter test psa.charter

# 3. Execute or inspect a single named scenario in ~3.8s
~/charter/.lake/build/bin/charter test psa.charter --scenario adv-seventeen-shell-successor-buyout-topup-gate
~/charter/.lake/build/bin/charter run psa.charter --scenario adv-twenty-partition-cutoff-and-quarantined-staging-fence

# 4. Inspect the span table and approval hash of any clause
~/charter/.lake/build/bin/charter trace LAW4.BUYOUT psa.charter
~/charter/.lake/build/bin/charter trace ADV.1 psa.charter

# 5. Interactive REPL loaded with the full protocol
~/charter/.lake/build/bin/charter repl psa.charter
```
