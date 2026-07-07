# Changelog — Rifki2020 TDVRP BKS

All notable changes to the curated `Rifki2020` TDVRP best-known solutions (BKS) are recorded here. Objective: **Duration** (duration minimization — the depot departure time of each route is a decision variable). Costs are the authoritative output of the canonical checker (`mamut_routing_lib.td.check_td_solution`): exact IEEE-754 double arithmetic, no epsilon thresholds, routes in canonical order (sorted by first customer), total summed in that order — so any strict improvement is real. Reminder: vehicle attributes are Onyr's curated ones (see README.md); the TDVRP variant removes the time windows.

## 2026-07-07

1 BKS improved by an exact solve — **proven optimal**: Rifki-23 n=20 (5951 → 5950), kayros 0.3.0 lera branch-price-and-cut (HiGHS backend, warm-started from the previous BKS, TL 600 s), from the certification campaign over all families n≤50. The same campaign certified 55 of the other stored TDVRP BKS of this family optimal as stored (all 30 at n=10).

## 2026-07-06

177 BKS improved by the first sweep of kayros 0.2.0.dev0 TD-ACO with time-dependent local search (tree-evaluated VND, every accepted move repriced by the checker-identical fold), 10 seeds per instance on Grid'5000.

## 2026-07-05

Initial BKS population, 180/180: the TDVRP variant had no legacy solutions, so all BKS come from the initial large-scale seeding sweep across all four TD families run on 2026-07-04 (kayros 0.0.1 TD-ACO, Grid'5000, 10 seeds per instance, 13 520 runs total).

## 2026-07-03

Family populated at the canonical K = 60 temporal granularity (180 instances + envelope-FIFO ATF sidecars), no BKS yet.
