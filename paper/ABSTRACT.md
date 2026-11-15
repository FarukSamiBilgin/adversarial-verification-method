# Extended abstract

**Status:** Manuscript in preparation. Faruk Sami Bilgin, Independent Researcher.

Computational and theoretical design studies increasingly carry the evidentiary weight once reserved for experiments: a chain of simulations and analytic estimates, each plausible, is assembled into a quantitative proposal. Such chains fail silently. A single mis-normalized quantity, a gauge-dependent intermediate, or a plotting-pipeline fallback can produce a confident, internally consistent, and wrong result that survives ordinary self-review because the author's checks share the author's assumptions.

We report a verification protocol built around one principle: every load-bearing result is re-derived by an independent procedure constructed to use an *orthogonal* method. We document three errors it removed from a real design study, each of a distinct and generalizable type:

1. a **gauge artifact**: a spurious 1/R pair-correlator tail that had become the basis of a claimed "geometric" signature, exposed by recomputing the gauge-invariant real-space density matrix (exponential decay, xi = 17.9 nm) and by a localization theorem that forbids the claimed behaviour;
2. a **tautology**: a "quantum-geometric twist-angle law" that a decomposition showed to be 98% (97.8%) a restatement of the bandwidth minimum that defines the operating point;
3. a **silent parameter fallback**: a figure showing a sharp resonant peak (7x contrast; 1.7x when recomputed) that a parser had generated from a provisional parameter, off by 6x, after failing to read the converged one.

None of the three was a coding bug in the ordinary sense; each was a reasoning error rendered invisible by shared assumptions, and each was caught only because the verifier was built not to share them. We abstract the protocol into a seven-point checklist and propose a seeded-error benchmark, and argue that adversarial re-derivation should accompany computational design studies as routinely as unit tests accompany software. As a single case study it is a demonstration, not a measured efficacy.
