# R01 · Grokking & Learning Phase Transitions — Dig-Site Literature Pass (2023–2026)

## TL;DR
- **Q1 (LLC/SLT):** Yes, the local learning coefficient (λ) empirically MOVES at the grokking transition — rising to a peak then declining (memorizing→generalizing basin) in the clearest primary source (Cullen et al., arXiv:2603.01192) — but the signal is fragile: SGLD estimates vary "by orders of magnitude" with hyperparameters, and at least one reviewer argues the movement may be indistinguishable from the trivial training-loss drop. *Confidence: moderate that λ moves; low that it is a clean/robust order parameter.*
- **Q2 (mirage vs. abrupt):** NOT settled but MATURED. The strongest post-2023 evidence (Lubana et al. 2024 percolation; Zhao et al. 2025 distributional/bimodal; the 2026 sparse-attention work) shows sharp transitions survive on CONTINUOUS metrics — undercutting the pure "mirage" claim — while conceding Schaeffer's core point that thresholded metrics manufacture artificial cliffs. Both camps are partly right.
- **Q3 (finite-size scaling / universality class):** Largely OPEN. Multiple 2026 preprints attempt it (self-organized criticality/directed-percolation, Binder-cumulant crossings), but NO robust, cross-seed, cross-architecture universality-class claim has survived scrutiny; the leading effort explicitly says its exponent "does not match the tested reference exponents" and defers class identification. A clean negative for now.

## Key Findings

**The field has bifurcated into two research programs** that rarely cite each other cleanly: (a) a *singular-learning-theory / developmental-interpretability* program (Timaeus/Murfet et al.) using the LLC as a complexity probe, and (b) a *statistical-physics* program mapping grokking/emergence to phase transitions with order parameters and critical exponents. Both are real and active; neither has produced a settled, falsifiable universality-class result for a *generalization* transition.

**Grokking is increasingly viewed as "measurement-sensitive but real."** The 2023–2026 consensus (CITING): grokking in *loss* is real and mechanistically grounded (circuit formation, lazy→rich transition, complexity rise-and-fall), but grokking in *accuracy* is partly an artifact of thresholding. This is a genuine reconciliation, not a stalemate.

## Details

### Q1 — LLC/RLCT dynamics via devinterp; does λ move at grokking?

**Primary sources (CITING):**
- **Lau, Furman, Wang, Murfet, Wei (2025), "The Local Learning Coefficient: A Singularity-Aware Complexity Measure," AISTATS 2025 (arXiv:2308.12108).** THEOREM-grade foundation: defines the LLC as an estimable local version of Watanabe's RLCT. Load-bearing definitional paper.
- **Wang, Hoogland, van Wingerden, Furman, Murfet (2024/2025), "Differentiation and Specialization of Attention Heads via the Refined Local Learning Coefficient," ICLR 2025 (arXiv:2410.02984).** Introduces the *refined* LLC (rLLC); per-component rLLC tracks staged head differentiation during training. Not modular-arithmetic grokking, but the most rigorous "λ moves during training" evidence.
- **Hoogland, Wang, Farrugia-Roberts, Carroll, Wei, Murfet (2024), "The Developmental Landscape of In-Context Learning" (arXiv:2402.02364).** LLC used to detect developmental stages.
- **Cullen, Estan-Ruiz, Danait, Li (2026), "Grokking as a Phase Transition between Competing Basins / A Basin-Selection Perspective on Grokking via Singular Learning Theory" (arXiv:2603.01192).** Clearest direct claim: in a quadratic-activation network on modular addition, "the LLC rises to a peak and then declines, while training accuracy remains essentially unchanged and validation accuracy increases sharply." Direction: RISE→PEAK→DECLINE. Frames grokking as movement from a higher-LLC memorizing basin to a lower-LLC generalizing basin.
- **Panickssery (formerly Rimsky) & Vaintrob (2023), hackathon write-up** (LessWrong/AF; devinterp): fully-trained λ̂ ∝ p (prime) for generalizing modular-addition nets vs. ~quadratic (∝p²) for memorizers; dynamic λ̂ "notices the grokking transition." NOT peer-reviewed; the dynamic estimator is explicitly "ad hoc." (Note: the Timaeus project page's "Nina Rimsky" and the post's "Nina Panickssery" are the same person; this is a single investigation, not two.)

**The empirical claim, graded:** That λ MOVES at grokking — MODERATE confidence (multiple independent setups agree qualitatively). That λ moves in a clean rise-then-fall shape usable as an order parameter — LOW confidence (cleanest only in the quadratic-network toy; not confirmed identically for standard ReLU/transformer grokking).

**Critiques / failed replications (CITING):**
- **SGLD hyperparameter sensitivity.** Cullen et al. (2026): varying only the SGLD sampler made final LLC estimates "vary by orders of magnitude"; log-linear dependence on localization γ and SGLD learning rate. Comparisons valid only at fixed hyperparameters.
- **Theoretical status of SGLD unclear.** The devinterp team itself ("Compressibility Measures Complexity," arXiv:2510.12077) states technical conditions for SGLD posterior convergence "do not hold for all neural networks"; the role of inverse temperature β is "not fully understood"; the only principled setting (1/log n) is "too small for stable estimation." Chen & Murfet (2025) prove temperature acts as a "resolution dial."
- **Distinguishability challenge.** A commenter (Olli Järviniemi) on the hackathon post argued the λ upturn "could be explained by the training loss going down" — i.e., not a distinct signal.
- **Pizza vs. clock via LLC: OPEN/unstarted** — no one has shown λ distinguishes the two known modular-addition circuits (Timaeus lists this as an unstarted follow-up). Anyone claiming otherwise overstates the record.
- **devinterp maintainers' own disclaimer:** "LLC Estimation is currently more of an art than a science."

**Honest answer to Q1:** λ appears to move at grokking (moderate confidence), consistent with SLT's Bayesian-phase-transition picture, but the estimator's fragility means it is not yet an established, robust diagnostic. The Bayesian-phase-transition framing is a CONJECTURE for non-toy nets (Murfet's own words: "not established yet").

### Q2 — Emergence-vs-mirage, post-2023

**The poles (CITING):**
- **Wei et al. (2022), "Emergent Abilities of Large Language Models," TMLR.** Defines emergence as an ability "not present in smaller models but is present in larger models"; Jason Wei's companion catalog lists 137 emergent abilities, the largest sources being BIG-Bench (67 emergent tasks) and the Massive Multitask (MMLU) benchmark (51 tasks). Frames the jumps as sharp and unpredictable with scale.
- **Schaeffer, Miranda, Koyejo (2023), "Are Emergent Abilities of LLMs a Mirage?" NeurIPS 2023 Outstanding Paper (arXiv:2304.15004).** Core claim, verbatim: "nonlinear or discontinuous metrics produce apparent emergent abilities, whereas linear or continuous metrics produce smooth, continuous, predictable changes in model performance." Demonstrated on the InstructGPT/GPT-3 family plus a BIG-Bench meta-analysis; switching accuracy → Brier score removes the apparent jump.

**New evidence, both directions (CITING):**
- **Against pure mirage / for real transitions:**
  - **Lubana, Kawaguchi, Dick, Tanaka (2024), "A Percolation Model of Emergence," ICLR 2025 (arXiv:2408.12578).** Trains transformers on a context-sensitive formal language; emergence occurs "once the language's underlying grammar and context-sensitivity inducing structures are learned." They "analogize [the] network's learning dynamics with the process of percolation on a bipartite graph, establishing a formal phase transition model that predicts the shift in the point of emergence… when changing the data structure." Reports a sublinear scaling of the transition point (empirically an exponent ~1.5 for one sub-task). This is the strongest existing percolation/phase-transition model of emergent capability in transformers.
  - **Zhao, Qin, Alvarez-Melis, Kakade, Saphra (2025), "Random Scaling of Emergent Capabilities" (arXiv:2502.17356).** Verbatim: "breakthroughs are instead driven by continuous changes in the probability distribution of training outcomes when performance is bimodally distributed across random seeds… These distributions may become abruptly bimodal at a capacity threshold—but this threshold appears at scales well before most seeds achieve breakthrough. Our observations hold true even under continuous loss metrics." Reconciles both camps.
  - **"Emergent Capabilities Arise Randomly from Learning Sparse Attention Patterns" (2026, arXiv:2606.25010).** Reproduces Zhao et al. on "the Pythia suite, which includes models trained with 10 random initializations across multiple parameter scales," measuring the change in ground-truth-token probability via single-attention-head ablation. On the CONTINUOUS metric of correct-token probability, capabilities still arise sharply throughout training; causal patching of a few attention heads elicits capabilities early. Direct empirical rebuttal to the "purely a metric artifact" reading.
  - **Michaud, Liu, Girit, Tegmark (2023), "The Quantization Model of Neural Scaling," NeurIPS 2023 (arXiv:2303.13506).** Proposes the "Quantization Hypothesis, where network knowledge and skills are 'quantized' into discrete chunks (quanta)," and shows that "when quanta are learned in order of decreasing use frequency, then a power law in use frequencies explains observed power law scaling of loss" — mechanistically unifying smooth loss with sharp skills.
- **For the mirage side / caution:**
  - **Levi, Beck, Bar-Sinai (2023/2024), "Grokking in Linear Estimators — A Solvable Model that Groks without Understanding," ICLR 2024 (arXiv:2310.16441).** In a solvable linear model, grokking is provably an artifact of the accuracy measure: loss dynamics are "oblivious" to the accuracy threshold.
  - **Kumar, Bordelon, Gershman, Pehlevan (2024), "Grokking as the Transition from Lazy to Rich Training Dynamics," ICLR 2024 (arXiv:2310.06110).** Explicitly: "grokking in accuracy does not imply grokking in loss"; accuracy grokking can be a mirage from threshold sweeps, while the loss-level lazy→rich transition is the real object. They demonstrate the mechanism "in more general settings, like on MNIST, one-layer Transformers, and student-teacher networks," using vanilla GD on a two-layer polynomial-regression network "which exhibits grokking without regularization in a way that cannot be explained by existing theories."

**Honest answer to Q2:** Neither "mirage" nor "abrupt capability" wins outright. Refined position (moderate-to-high confidence): underlying capability changes are often continuous, but (i) they can be genuinely sharp even on continuous metrics in specific controlled settings, and (ii) seed-level bimodality plus thresholding jointly produce the appearance of emergence. Percolation (Lubana) is the most concrete phase-transition model; it is a phenomenological analogy, not a derived universality result.

### Q3 — Finite-size scaling with explicit critical exponent / universality class

**Attempts (CITING):**
- **Žunkovič & Ilievski (2024), "Grokking phase transitions in learning local rules with gradient descent," JMLR 25(199) (arXiv:2210.15435).** THEOREM/analytic: solvable rule-learning (cellular-automaton) models with *exact* analytic critical exponents, grokking probability, and grokking-time distributions; numerically extracts a critical exponent for the rule-30 task. Most rigorous exponent result — but for a bespoke solvable model, not generic deep nets.
- **Rubin, Seroussi, Ringel (2024), "Grokking as a First Order Phase Transition in Two Layer Networks," ICLR 2024 (arXiv:2310.03789).** Maps grokking to a FIRST-ORDER transition (adaptive-kernel theory); reports hysteresis/mixed-phase signatures. First-order ⇒ no diverging correlation length / no standard continuous universality class.
- **Ping Wang (2026), "Grokking as Dimensional Phase Transition" (arXiv:2604.04655) and "Dimensional Criticality at Grokking Across MLPs and Transformers" (arXiv:2604.16431).** Finite-size scaling of gradient-avalanche dynamics across 8 model scales; claim a self-organized-criticality (SOC) dimensional crossing D=1 at generalization; D_pre=1.12±0.02, D_post=0.92±0.02. Authors state: "the precise universality class of this dimensional crossover remains an open question."
- **"Weight Decay Regimes in Grokking Transformers" (2026, arXiv:2605.20441).** Reports ν=0.757 power-law fit to time-to-grok but states plainly: "the measured exponent does not match the tested reference exponents, so universality-class identification is deferred."
- **"Bi et al. (2026)"** — cited secondhand as concurrent work applying finite-size scaling with Binder-cumulant crossings and spectral head-tail contrast as order parameter. I could NOT independently verify this preprint's arXiv ID or results; treat as UNVERIFIED, do not cite as established.
- **Absorbing-phase-transition work (arXiv:2307.02284)** places MLPs in mean-field and CNNs in directed-percolation universality classes for *signal propagation* (not grokking generalization) — adjacent, not the same transition.

**Honest answer to Q3:** NO — there is no robust, cross-seed, cross-architecture critical-exponent/universality-class claim for a *learning/generalization* transition that has survived scrutiny. Exact exponents exist only for solvable toy models (Žunkovič–Ilievski). The 2026 SOC/dimensional and Binder-cumulant efforts are promising but self-describe the universality class as open, and their exponents don't match reference classes. Clean negative.

## Open Problems, ranked by single-GPU / Colab tractability

**1. (Most tractable) Reproduce the LLC rise-then-fall at grokking on modular addition and stress-test its robustness.**
- NULL-CASE (stated first): If, across a fixed-hyperparameter SGLD sweep, λ(t) shows no peak distinct from the training-loss curve — i.e., λ(t) tracks train loss with no separate feature at the val-accuracy onset — the "λ is an order parameter" idea is demoted to "λ restates loss." Also killed if the peak's existence flips under reasonable γ/lr changes.
- Why promising (only after null): Cullen et al. and the hackathon both report movement on tiny Colab-scale models; devinterp is public. Directly touches Q1.

**2. Test whether accuracy-grokking is a threshold mirage vs. loss-grokking on a controlled task.**
- NULL-CASE: If test *loss* drops at essentially the same step as test *accuracy* (no wide gap), the "mirage" framing doesn't apply here and there is nothing metric-artifactual to demote. Also null if the gap vanishes when sweeping the accuracy threshold θ.
- Why promising: Kumar et al. and Levi et al. give exact predictions to check; a Colab MLP suffices.

**3. Distinguish pizza vs. clock circuits with the LLC (currently unstarted).**
- NULL-CASE: If λ̂ for pizza- and clock-solution networks overlap within SGLD estimation noise at fixed hyperparameters, the LLC does NOT resolve circuit identity — demote. (Likely outcome: LLC measures degeneracy, not circuit type.)
- Why promising: known open question; small models; but expect the null.

**4. Small-scale finite-size-scaling / data-collapse of time-to-grok across model widths.**
- NULL-CASE: If time-to-grok vs. control parameter does NOT collapse onto a single scaling function across widths/seeds (residuals larger than seed variance), there is no clean critical exponent — the "universality" idea dies for that setup. Given the best current effort's exponent "does not match reference exponents," expect fragility.
- Why promising: Colab-feasible across a few widths; high null risk (a clean negative is itself a result).

**5. (Least tractable on single GPU) Replicate the percolation-emergence scaling on a formal language.**
- NULL-CASE: If the emergence point does not shift as predicted by the bipartite-graph percolation threshold when data structure is varied, the percolation model is falsified for your setup.
- Why hard: Lubana et al. train many transformers; borderline for Colab.

## Strongest Critiques, Failed Replications, Live Controversies (who disputes what)

- **Schaeffer, Miranda, Koyejo (Stanford)** dispute Wei et al. (Google) on whether emergence is real or a metric artifact. Status: partially vindicated (metrics matter) but overturned as a *universal* explanation by Zhao et al. and the 2026 sparse-attention work showing sharpness on continuous metrics.
- **Levi, Beck, Bar-Sinai** and **Kumar, Bordelon, Gershman, Pehlevan** dispute that accuracy-grokking reflects a "memorization→understanding" transition — showing it can be a threshold artifact over unremarkable loss curves.
- **"Not All Explanations for Deep Learning Phenomena Are Equally Valuable" (2025, arXiv:2506.23286)** disputes grokking's practical relevance: grokking has NOT been observed in realistic large-scale settings (cites a Dziri et al. 2024 failure); it typically requires small algorithmic data or inflated init scale.
- **The devinterp/Timaeus team disputes ITS OWN tool's maturity** — repeated public caveats that SGLD-LLC is hyperparameter-sensitive and theoretically incomplete. This self-skepticism is a positive epistemic signal.
- **Olli Järviniemi** (commenter) disputes that dynamic λ̂ carries information beyond training loss.

## The 5 Most Load-Bearing References (why each matters)

1. **Lau, Furman, Wang, Murfet, Wei (2025), AISTATS — "The Local Learning Coefficient" (arXiv:2308.12108).** The definitional/estimation backbone; without it, no LLC-at-grokking discussion exists.
2. **Schaeffer, Miranda, Koyejo (2023), NeurIPS Outstanding Paper — "Are Emergent Abilities a Mirage?" (arXiv:2304.15004).** The hinge of the entire emergence debate; every later paper positions relative to it.
3. **Lubana, Kawaguchi, Dick, Tanaka (2024), ICLR 2025 — "A Percolation Model of Emergence" (arXiv:2408.12578).** The only concrete, predictive phase-transition (percolation) model of emergent capability in transformers.
4. **Žunkovič & Ilievski (2024), JMLR — "Grokking phase transitions in learning local rules" (arXiv:2210.15435).** The only rigorous source with EXACT analytic critical exponents for a grokking transition.
5. **Rubin, Seroussi, Ringel (2024), ICLR — "Grokking as a First Order Phase Transition" (arXiv:2310.03789).** The most-cited statistical-physics mapping; its first-order (not continuous) claim directly shapes whether a continuous universality class should even exist.

## Adjacent Fringe Claims to Steer Around (and why each is fringe)

- **"Grokking / criticality explains or indicates machine consciousness / edge-of-chaos intelligence."** Fringe: conflates signal-propagation criticality (a real, narrow phenomenon) with cognition; no operational definition, no falsifiable prediction.
- **"A single universal critical exponent / universality class governs all neural-network learning transitions."** Fringe/premature: contradicted by first-order mappings (Rubin et al.) and by the SOC papers' own admission that the class is open; SOC models notoriously have non-universal exponents.
- **"Grokking is a general property of large-model training you should expect in production LLMs."** Fringe relative to evidence: grokking is largely confined to small algorithmic data / inflated-init regimes; realistic-scale replications have failed (arXiv:2506.23286).
- **Overreaching SLT claims that "the LLC measures the model's true complexity / generalization in practice."** Fringe when stated unconditionally: order-of-magnitude hyperparameter sensitivity means it is currently a research probe, not a validated complexity meter.
- **Very recent (2026) single-preprint "universal convergence across complex systems" grokking papers** (e.g., sweeping arXiv:2606.07563-type claims) — treat as unvetted; grand cross-domain universality claims from single un-replicated preprints are a classic fringe signature.

## Caveats
- Several key items are 2026 preprints (arXiv:2603.01192, 2604.04655, 2604.16431, 2605.20441, 2606.25010) that are recent and in some cases not peer-reviewed; grade their empirical claims LOW-to-MODERATE pending replication.
- I could NOT independently verify the "Bi et al. (2026)" Binder-cumulant finite-size-scaling paper's existence/ID — referenced secondhand; do not cite as established.
- The distinction between (a) generalization/grokking transitions and (b) signal-propagation criticality (mean-field vs. directed-percolation classes) is frequently blurred in secondary sources; they are different transitions.
- THEOREMS here: Žunkovič–Ilievski exact exponents (for their solvable model); Lau et al. LLC estimability results. CONJECTURES: Bayesian-phase-transition framing for non-toy nets; SOC universality of grokking; percolation as the mechanism of LLM emergence.
- "Confidence" grades reflect the state of evidence as of this pass, not the plausibility of the underlying idea.