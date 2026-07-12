# Changelog — Rifki2020 TDVRP BKS

All notable changes to the curated `Rifki2020` TDVRP best-known solutions (BKS) are recorded here. Objective: **Duration** (duration minimization — the depot departure time of each route is a decision variable). Costs are the authoritative output of the canonical checker (`mamut_routing_lib.td.check_td_solution`): exact IEEE-754 double arithmetic, no epsilon thresholds, routes in canonical order (sorted by first customer), total summed in that order — so any strict improvement is real. Reminder: vehicle attributes are Onyr's curated ones (see README.md); the TDVRP variant removes the time windows.

## 2026-07-12

**6 further BKS stamped proven optimal** by the weekend top-up of the exact re-certification campaign (2026-07-11/12, Grid'5000; time limit 1800 s per run). Protocol unchanged from the 2026-07-10/11 campaign: four independent exact solves (cold and warm starts crossed with the two labeling modes) agreeing on the value, an audited exact-pricing phase in every run, zero checker-infeasible priced columns, and canonical-checker re-validation at stamping time. New certificates: Rifki-3, Rifki-23 (n=10); Rifki-11, Rifki-19, Rifki-24, Rifki-30 (n=20). This family now carries 36 certified TDVRP BKS.

## 2026-07-11 (second entry)

1 further BKS stamped proven optimal (Rifki-3 n=10): certified by the exact value-jump solver path (mollifier-free), cold and warm solves agreeing, exact-pricing phase audited, where the standard path had timed out. The exact path was validated family-wide the same day: 77/77 agreement with existing certificates and a near-total elimination of checker-infeasible pricing events (1 in 720 runs against 68 before).

## 2026-07-11

**30 BKS stamped proven optimal** (`metadata.optimality`), the TDVRP twin's first certificates (all of n=10): optimality certificates return to this family after the 2026-07-08 retraction, under the four-run agreement protocol and a repaired prover. Each stamp certifies four independent exact solves (cold and warm starts x two labeling modes) agreeing on the value, an audited exact-pricing phase in every run, zero checker-infeasible priced columns, and canonical-checker re-validation at stamping time. Instances whose runs disagreed, timed out, or priced a checker-infeasible column carry NO stamp.

## 2026-07-08

**Optimality certificates retracted (all 56 stamped BKS of this family) and 14 further BKS improved.** The head-to-head campaign below produced checker-valid solutions strictly below 14 of the 2026-07-07 "proven optima" (margins 4 to 73 duration units, up to 0.51%) — those certificates are refuted by counterexample. The failure was reproduced deterministically on the TDVRPTW twin family: the prover's certified value depends on its warm start (three runs on one instance certified three different values as "optimal"), i.e. its pricing step is incomplete on this family's stepwise travel-time functions — the near-vertical segments used to continuize the step discontinuities for the solver's piecewise-linear machinery amplify its internal epsilon tolerances into route-level cost errors, so improving routes can be silently discarded and the dual bound is not sound. The canonical checker (exact arithmetic, no epsilons) remains authoritative and confirms every counterexample. All `metadata.optimality` stamps of this family are therefore retracted, including the 42 whose values were never contradicted (the campaign matched all 42 exactly without improving them, which supports the values but restores them to ordinary best-known status). The 14 counterexample solutions are now folded as regular BKS (mean -0.23%, largest -0.51%) through the standard improve-only, checker-authoritative pipeline. Re-certification will follow once the exact solver handles stepwise travel times exactly.

67 of 180 BKS improved (mean -0.44%, largest single improvement -1.64%) by a 20,808-run anytime-strategy head-to-head campaign on Grid'5000: kayros 0.4.0.dev0 (TD-ILS, TD-ACO+LS, and an ACO-then-ILS budget split, all over the granular time-dependent local search), per-size time limits (120 s for n<=30, 300 s for n<=60, 600 s for n<=100), seeds {42, 123, 456}, single-threaded runs. Improve-only fold: for each instance the campaign-best solution was re-priced by the canonical checker before writing (checker cost authoritative); stored BKS marked proven optimal were left untouched.

## 2026-07-07

1 BKS improved by an exact solve — **proven optimal**: Rifki-23 n=20 (5951 → 5950), kayros 0.3.0 lera branch-price-and-cut (HiGHS backend, warm-started from the previous BKS, TL 600 s), from the certification campaign over all families n≤50. The same campaign certified 55 of the other stored TDVRP BKS of this family optimal as stored (all 30 at n=10).

Structured optimality metadata: all 56 BKS of this family proven optimal by that campaign now carry a machine-readable `metadata.optimality` object — prover, certificate wording, proven optimum, dual bound, wall time (schema: `OptimalityMetadata`, mamut-routing-lib ≥ 0.4.0).

## 2026-07-06

177 BKS improved by the first sweep of kayros 0.2.0.dev0 TD-ACO with time-dependent local search (tree-evaluated VND, every accepted move repriced by the checker-identical fold), 10 seeds per instance on Grid'5000.

## 2026-07-05

Initial BKS population, 180/180: the TDVRP variant had no legacy solutions, so all BKS come from the initial large-scale seeding sweep across all four TD families run on 2026-07-04 (kayros 0.0.1 TD-ACO, Grid'5000, 10 seeds per instance, 13 520 runs total).

## 2026-07-03

Family populated at the canonical K = 60 temporal granularity (180 instances + envelope-FIFO ATF sidecars), no BKS yet.
