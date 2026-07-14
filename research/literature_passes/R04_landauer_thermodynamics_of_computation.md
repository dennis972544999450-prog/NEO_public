# R04 · Landauer & the Thermodynamics of Computation — Dig-Site Map (OMPU / "The Anomaly Dig")

**Scope:** Thermodynamics of computation and fluctuation theorems. Three axes: (1) experimental Landauer-limit tests classical→quantum; (2) the thermodynamic uncertainty relation (TUR) family 2015–2026; (3) thermodynamics of computation beyond bit erasure (Wolpert–Kolchinsky, Still et al., Boyd–Mandal–Crutchfield). Hygiene: every empirical claim graded H/M/L confidence; theorems and conjectures marked explicitly; inference flagged vs. citation. "Open"/"no" stated plainly. No fabricated citations — where I could not confirm a specific reference exists, I say so.

---

## TL;DR
- **Landauer's bound (⟨Q⟩ ≥ k_BT ln2 per erased bit) is empirically well-corroborated (HIGH confidence) from 2012 colloidal experiments through 2018–2025 quantum-regime tests, but every experiment measures *asymptotic* bound-saturation and *assumes* quasi-static/error-free idealizations; "sub-k_BT ln2" and "beyond Landauer" claims are real but are NOT second-law violations — they exploit nonequilibrium initial states or redefinitions.** The bound is a theorem within statistical mechanics; its *independence* from the second law remains genuinely disputed (Norton).
- **The TUR is a proven theorem for classical Markov-jump / overdamped-Langevin steady states (Barato–Seifert 2015 conjecture → Gingrich–Horowitz–England–Vaikuntanathan 2016 proof). It is provably VIOLATED in the quantum regime and under broken time-reversal symmetry; the kinetic uncertainty relation (KUR) governs far-from-equilibrium precision. Biological applications (motor-efficiency inference, Berg–Purcell-type sensing bounds, proofreading cost) are established as bounds but rarely saturated.**
- **Beyond erasure: mismatch cost (Kolchinsky–Wolpert) and the cost of modularity (Boyd–Mandal–Crutchfield) are theorem-level results in stochastic thermodynamics; Still et al.'s thermodynamics of prediction is proven. The *semantic-information* framework (Kolchinsky–Wolpert 2018) is a rigorous set of definitions but its interpretive claims about "meaning"/"agency" are conjectural and contested. For a single-GPU shop the tractable dig is numerical: TUR/KUR/TUT saturation in small Markov networks, Langevin erasure, mismatch-cost verification, and short-trajectory entropy-production inference.**

---

## 1) State of the Art, 2023–2026 (primary sources first)

### AXIS 1 — Experimental Landauer-limit tests: classical → quantum

**Foundational (pre-2023, load-bearing — cited, not re-derived):**
- **Landauer 1961** (IBM J. Res. Dev. 5, 183): logically irreversible operations dissipate ≥ k_BT ln2 per bit. *Theorem-level within stat-mech given its assumptions.*
- **Bennett 1982** (Int. J. Theor. Phys. 21, 905): reversible computation; erasure is the sole unavoidable cost.
- **Bérut, Arakelyan, Petrosyan, Ciliberto, Dillenschneider, Lutz 2012** (Nature 483, 187): first experimental test. A "silica bead (2 μm in diameter)" in a 1,064 nm vertical optical tweezer forming a modulated double-well. **Directly measured:** dissipated heat via the Sekimoto stochastic-energetics integral of force×velocity along overdamped trajectories. **Result (verbatim):** "the mean dissipated heat saturates at the Landauer bound in the limit of long erasure cycles," with asymptotic form ⟨Q⟩ = kT ln2 + B/τ. **Loophole/assumed:** saturation is *asymptotic* (finite-time cycles dissipate strictly more via the B/τ term); heat inferred from an assumed friction coefficient and overdamped Langevin model. Confidence in the claim: **HIGH**.
- **Jun, Gavrilov, Bechhoefer 2014** (PRL 113, 190601): higher-precision feedback-trap version; verified bound and showed logically reversible operations approach thermodynamic reversibility. **HIGH.**
- **Hong, Lambson, Dhuey, Bokor 2016** (Sci. Adv. 2, e1501492): Permalloy (NiFe) elliptical nanomagnets (>10⁴ spins), MOKE readout. **Verbatim:** "the energy dissipation was measured to be (4.2 ± 0.9) zJ, which corresponds to a value of (1.0 ± 0.22)k_BT (for T = 300 K)," measured across 300–400 K. **MODERATE** (large system, more inference; note the value is per bit near k_BT, i.e., above ln2·k_BT ≈ 0.69 k_BT).
- **Yan, Xiong, Rehan, … Feng 2018** (PRL 120, 210601): first quantum-regime single-atom test. Trapped ⁴⁰Ca⁺ ion qubit; reservoir = the ion's own quantized vibrational modes. **Directly measured:** internal-state populations (397 nm fluorescence → ΔS) and phonon number ⟨n⟩ (→ heat), initial ⟨n⟩₀ = 0.074(9). **Inferred/assumed:** mutual information estimated indirectly (system–reservoir entanglement not directly measured). Tested an "improved," finite-size LP (Reeb–Wolf-type). **MODERATE–HIGH.**
- **Gaudenzi et al. 2018** (Nat. Phys.): giant-spin (S_z = ±10) molecular magnet at 1 K via SQUID; quantum-regime erasure with quantum-speed-limit interplay. **MODERATE.**
- **Koski, Maisi, Pekola, Averin 2014** (PNAS 111, 13786): single-electron box Szilard engine — the *reverse* direction (extracting k_BT ln2 per bit of acquired information). **HIGH** for the Szilard/Maxwell-demon direction.

**2023–2026 developments:**

- **Aimet, Tajik, Tournaire, Schüttelkopf, Sabino, Sotiriadis, Guarnieri, Schmiedmayer, Eisert — "Experimentally probing Landauer's principle in the quantum many-body regime"** (arXiv:2407.21690, Jul 2024; **Nature Physics 21, 1326–1331, 2025**, DOI 10.1038/s41567-025-02930-9). Platform: ultracold-atom **quantum field simulator** — two tunnel-coupled 1D ⁸⁷Rb quasi-condensates on an atom chip (L ≈ 49 µm, transverse trap ω⊥/2π = 1.4 kHz). **Verbatim protocol:** "After preparing a thermal equilibrium state at a temperature of 49 nK, all traps are turned off," followed by 15.6 ms free-fall absorption imaging. **CRITICAL DISTINCTION (flag):** this does **NOT** test the k_BT ln2 erasure bound. It tests a *generalized* Landauer/entropy-production decomposition ΔΣ = ΔI + ΔD (change in quantum mutual information + change in relative entropy of the environment) after a global mass quench (Klein–Gordon massive→massless). **Directly measured:** the relative phase profile φ(z) via matter-wave interference. **Inferred/reconstructed:** the full covariance matrix via Gaussian "dynamical tomographic reconstruction"; effective inverse temperature β_E from QFT simulation; ΔS, ΔI, ΔD are not directly measured. **Loopholes (verbatim):** "ΔΣ may not necessarily be non-negative"; the Neumann-boundary zero mode "restricts the validity of the tomography scheme to ct/L < 1"; relies on assumed global unitary dynamics and Gaussianity; the dominant contribution is ΔI, not the energetic term. Confidence the experiment did what it claims: **HIGH**; confidence it bears on the *erasure* bound: **LOW (it doesn't — it's a generalized-entropy-production probe).**

- **Ciampini, Wenzl, Konopik, Thalhammer, Aspelmeyer, Lutz, Kiesel — "Erasure of a nonequilibrium memory beyond Landauer's bound using levitated optomechanics with spatio-temporal optical control"** (arXiv:2107.04429, 2021; published **Phys. Rev. Research 7, 043321, 22 Dec 2025**, DOI 10.1103/r81x-zblx). Platform: underdamped **levitated nanoparticle** double-well memory with dynamically shaped nonlinear potentials. **Directly measured:** work and heat over ~20,000 repetitions per configuration. **Result (verbatim):** "By harnessing the energy and entropy of an initial nonequilibrium two-state memory, we demonstrate reduced power consumption as well as negative heat production during erasure." **Why NOT a second-law violation (flag: inference + citation):** the k_BT ln2 bound assumes an *equilibrium* initial memory; they exploit a *nonequilibrium* initial state whose extra free energy/athermality is a resource, and their measured values agree with *generalized* Landauer bounds (their Eqs. 1–2). Confidence they went below k_BT ln2: **HIGH**; confidence this is not a second-law violation: **HIGH.**

- **Scandi, Barker, Lehmann, Dick, Maisi, Perarnau-Llobet — "Minimally dissipative information erasure in a quantum dot via thermodynamic length"** (arXiv:2209.01852, 2022 — flag: just outside the window; most relevant single-electron erasure with hard numbers). Semiconductor single-electron quantum dot, InAs nanowire, T = 100 mK. **Directly measured:** heat via real-time single-electron tunnelling detection (charge-sensor current). **Result:** thermodynamic-length-geodesic drives minimize dissipation vs. linear drives; improvement grows as erasure → perfect; illustrates the constant-dissipation-rate principle. **HIGH.**

- **Extra cost of erasure due to quantum lifetime broadening** (arXiv:2410.02546, Oct 2024): *theory*, load-bearing for interpreting quantum-dot erasure — in a source-gate-drain (two-electrode) architecture, k_BT ln2 is *not* the true floor; potential difference and level lifetime broadening add unavoidable cost "even in the limit of perfect quasistatic operation." **Theorem-level within their model.** Anomaly worth flagging: naive k_BT scaling misleads in the sub-kelvin regime where quantum-dot devices operate.

- **Finite-time Landauer corrections (theory, 2020–2023, load-bearing):** **Proesmans, Ehrich, Bechhoefer 2020** (PRL 125, 100602; PRE 102, 032105): W_min − k_BT ln2 = a·Var(x)/(Dτ) — cost above Landauer scales as 1/τ, and the optimal protocol can be up to 4× cheaper than a naive one. **Van Vu, Saito 2022** (PRL 128, 010602): finite-time *quantum* Landauer principle and coherence. **Rolandi, Perarnau-Llobet 2023** (Quantum 7, 1161): finite-time Landauer beyond weak coupling. All **theorem-level.**

**Honest negative:** There is **no** dedicated 2023–2026 superconducting-transmon-qubit experiment measuring k_BT ln2 erasure with hard precision numbers that I could locate. The closest is the pre-window classical superconducting-flux-logic erasure work (Crutchfield/Han/Roukes, PRR 2, 013249, 2020). A claim that "superconducting qubits verified the quantum Landauer bound 2018–2023" appeared only in a secondary snippet (Grokipedia) without primary backing — treat as **LOW confidence / likely secondary-source conflation.**

### AXIS 2 — The TUR family, 2015–2026

**Foundational:**
- **Barato, Seifert 2015** (PRL 114, 158101, "TUR for Biomolecular Processes"): **CONJECTURED** Var(J)/⟨J⟩² ≥ 2k_B/ΔS_tot for steady-state currents.
- **Gingrich, Horowitz, Perunov, England 2016** (PRL 116, 120601, "Dissipation Bounds All Steady-State Current Fluctuations"): **PROVED** the TUR for continuous-time Markov-jump steady states via large-deviation theory. The load-bearing theorem: ΔS_tot ≥ 2⟨J⟩²/Var(J).
- **Horowitz, Gingrich 2017** (PRE 96, 020103(R)): **proof** of the finite-time TUR. **Pietzonka, Ritort, Seifert 2017** (PRE 96, 012101); review **Horowitz–Gingrich 2020** (Nat. Phys. 16, 15).

**Scope of validity (theorem vs. not):**
- **THEOREM:** TUR holds for time-homogeneous continuous-time Markov chains and overdamped Langevin at steady state; finite-time and periodic-driving generalizations proven (Koyuk–Seifert 2019).
- **PROVABLY FAILS / violated:** underdamped Langevin with velocity-dependent (magnetic Lorentz) forces; broken time-reversal symmetry; discrete-time dynamics (modified form, Proesmans–Van den Broeck 2017); **quantum coherent** systems.
- **Quantum violations (2018–2026):** Agarwalla–Segal 2018 (PRB 98, 155438) — violation in quantum thermoelectric junctions; Kalaee–Wacker–Potts 2021 (PRE 104, L012103) — violation in the three-level maser; Maity–Ghoshal 2025 (arXiv:2501.00627) — violation in quantum collisional models tied to coherence (note: they also observe that "more coherent systems do not necessarily exhibit greater TUR violations"). **Empirically/numerically observed + analytically supported.** Confidence that quantum coherence can push precision below the classical TUR floor: **HIGH.**
- **Quantum TUR extensions (theorem-level):** Hasegawa 2020/2021 (PRL 125, 050601; PRL 126, 010602) — quantum TUR for open systems via continuous measurement / general open quantum systems, valid but generally looser; recovers the classical TUR in the decoherent (commuting-operator) limit.

**Kinetic Uncertainty Relation (KUR) — the far-from-equilibrium partner:**
- **Di Terlizzi, Baiesi 2019** (J. Phys. A 52, 02LT03): **PROVED** that relative fluctuations are bounded by mean dynamical activity (number of jumps), not entropy production. **Key anomaly-relevant fact:** the TUR is the binding constraint near equilibrium; the KUR binds far from equilibrium — both hold simultaneously, the tighter one wins.
- **Unified TKUR** (Vo–Van Vu–Hasegawa 2022, J. Phys. A 55, 405004): combines entropy production AND activity; tightest of the family.
- **2023–2026 frontier:** **Ray, Boyd, Guarnieri, Crutchfield 2023 — "Thermodynamic Uncertainty Theorem" (TUT)** (PRE 108, 054126; arXiv:2210.00914): derives the *exact* charge achieving minimum scaled variance, tightening the TUR *inequality* into an *equality* that retains higher cumulants of entropy production. **Theorem-level; a genuine 2023 advance.** Ptaszyński–Aslyamov–Esposito 2024 (PRL 133, 227101): dissipation bounds precision of current *response* to kinetic perturbations. Nat. Comm. Physics 2025 (s42005-025-01982-w): dynamical activity universally bounds *response* precision.

**Applications to biology (established as bounds; graded):**
- **Molecular-motor efficiency inference:** Pietzonka–Barato–Seifert 2016 (J. Stat. Mech. 124004) — TUR bounds motor efficiency from velocity + effective diffusivity (kinematic measurements) without measuring ATP consumption; applied to kinesin-1 (V ≈ 1 µm/s, 8 nm steps per ATP) under load. **A real, usable inference tool. HIGH as a bound; the bound is generally NOT saturated by real motors (MODERATE on tightness).** See Hwang–Hyeon 2018 (JPCL 9, 513); review Hyeon et al. (J. Chem. Phys. 154, 130901, 2021).
- **Berg–Purcell sensing / concentration estimation:** TUR-type bounds connect to the cost of precise chemical sensing (Barato–Seifert "Cost and Precision of Brownian Clocks," PRX 6, 041053, 2016; Marsland–Cui–Horowitz 2019, biochemical oscillations). **Flag (inference):** the literature ties concentration-estimation precision to dissipation via the TUR, generalizing Berg–Purcell (1977); I did **not** retrieve a single canonical "TUR = Berg–Purcell" theorem paper, so treat the *specific equivalence* as **MODERATE / partially open** rather than a cited theorem.
- **Kinetic proofreading / copy-machine error cost:** Song–Hyeon 2020 (JPCL 11, 3136, "Thermodynamic cost, speed, fluctuations, and error reduction of biological copy machines"); foundational Hopfield 1974 / Bennett 1979 dissipation–error tradeoff. **Established as a tradeoff; specific TUR-form bounds MODERATE.**
- **Entropy-production inference from data:** **Manikandan, Gupta, Krishnamurthy 2020** (PRL 124, 120603, "Inferring Entropy Production from Short Experiments"): TUR-based estimator needing only short time series; Li–Horowitz–Gingrich–Fakhri 2019 (Nat. Comm. 10, 1666); Otsubo–Ito–Dechant–Sagawa 2020 (PRE 101, 062106, ML of short-time currents). **The most directly Colab-able export of the whole axis. HIGH.**

### AXIS 3 — Thermodynamics of computation beyond bit erasure

**Wolpert–Kolchinsky program:**
- **Wolpert 2019** (J. Phys. A 52, 193001, "The stochastic thermodynamics of computation"; arXiv:1905.05669, revised 2023 & 2025): the field-defining review. Decomposes entropy flow into (i) Landauer cost (drop in Shannon entropy, hardware-independent), (ii) **mismatch cost**, (iii) residual. **Theorem-level decomposition.**
- **Mismatch cost (Kolchinsky–Wolpert 2017 J. Stat. Mech. 083202; 2021, arXiv:2103.05734):** **THEOREM** — the extra EP above the minimum equals the *drop in KL divergence* D(p₀‖q₀) − D(p_τ‖q_τ) between the actual initial distribution and the "prior"/optimal distribution q₀ for which the process is minimally dissipative. Feed a device tuned for q₀ the wrong input p₀ and you pay k_B·[drop in relative entropy]. **The single most exportable theorem of the axis; directly numerically checkable.**
- **Thermodynamics of Turing machines (Kolchinsky–Wolpert 2020, PRR 2, 033312):** entropy costs of universal computation; **theorem-level** but with strong modeling assumptions (maps computation to a CTMC / master equation).
- **Space/time tradeoff (Wolpert–Kolchinsky–Owen 2019, Nat. Comm. 10, 1727); hidden-state count (Owen–Kolchinsky–Wolpert 2018, NJP).** Theorem-level.
- **Riechers–Gu 2021** (PRA 104, 012214, "Impossibility of achieving Landauer's bound for almost every quantum state"): **THEOREM.** For any reliable reset, Q − Q_Landauer ≥ k_BT·D[ρ₀‖α₀], where α₀ is the *single* minimally dissipative input (generically mixed). Verbatim: "this lower bound is necessarily unachievable for every initial state (except possibly the single minimally dissipative input) for any reliable reset mechanism." **A hard anomaly: k_BT ln2 is saturable by at most ONE input state; all others dissipate strictly more** (by k_B·relative entropy to α₀).
- **Riechers, Gupta, Kolchinsky, Gu 2024** (PRX Quantum 5, 030318, "Thermodynamically ideal quantum-state inputs to any device"; arXiv:2305.00616): **THEOREM.** Entropy flow, heat, and work are all expectation values of constructible Hermitian operators; extremized by *pure* eigenstates, but minimal-EP / max-free-energy inputs are *mixed* states obtained by convex optimization. Operationally, a finite number of test inputs determines the full thermodynamic response. **Theorem-level; central to designing minimally dissipative computation.**
- **Wolpert et al. 2024** (PNAS 121, e2321112121, "Is stochastic thermodynamics the key to understanding the energy costs of computation?"): multi-author position/review — sober; flags what remains open.

**Still–Sivak–Bell–Crooks — thermodynamics of prediction:**
- **Still, Sivak, Bell, Crooks 2012** (PRL 109, 120604): **THEOREM** — for a system driven by a stochastic signal, the *nonpredictive* information it retains ("nostalgia") lower-bounds dissipation; a maximally efficient memory must be maximally predictive. Holds arbitrarily far from equilibrium. Still heavily cited 2023–2026. Confidence: **HIGH** (proven).

**Boyd–Mandal–Crutchfield — information ratchets / Maxwellian demons:**
- **Boyd, Mandal, Crutchfield 2016** (NJP 18, 023049, "Identifying Functional Thermodynamics in Autonomous Maxwellian Ratchets"): exactly solvable ratchets; distinguishes engine/eraser regimes; can erase by increasing inter-bit correlations. **Theorem/exact-model level.**
- **Boyd, Mandal, Crutchfield 2018** (PRX 8, 031036, "Thermodynamics of Modularity: Structural Costs Beyond the Landauer Bound"): **THEOREM** — modular (locally-operating) implementations pay a "modularity dissipation" strictly above the global Landauer bound. **The cost of modularity is real and provable. HIGH.**
- **Info Processing Second Law (IPSL):** finite-state ratchets cannot reach the global bound; infinite-state ratchets can exceed it via their own "negentropy" (Boyd–Mandal–Crutchfield, J. Stat. Phys. 167, 1555, 2017).
- **Mandal–Jarzynski 2012** (PNAS 109, 11641): the foundational solvable Maxwell-demon ratchet.

---

## 2) Open problems, ranked by tractability for single-GPU / Colab

**Tier A — genuinely reachable on Colab (small compute suffices):**

1. **TUR / KUR / TUT saturation in small Markov networks.** Build a 3–5-state continuous-time Markov chain; compute steady-state currents, entropy production, and dynamical activity; check the TUR (GHEV 2016), KUR (Di Terlizzi–Baiesi), and the Ray et al. 2023 TUT equality. Linear algebra on tiny rate matrices — trivial compute.
   - **NULL-CASE (stated first):** If a 3-state network shows TUR violation *without* broken time-reversal / non-Markovianity, OR the TUT-optimal charge fails to tighten the bound to equality within tolerance, your implementation is wrong (the theorems are exact) — kills the "correct implementation" claim. *Promising precisely because the null-case is sharp and self-checking.*

2. **Langevin simulation of Landauer erasure + finite-time 1/τ scaling.** Overdamped Langevin in a double-well, quasi-static → finite-time; verify ⟨Q⟩ → k_BT ln2 (Bérut asymptote) and the Proesmans–Ehrich–Bechhoefer W_min − k_BT ln2 = a·Var(x)/(Dτ) law plus the ≤4× optimal-protocol improvement. Trivial compute.
   - **NULL-CASE (first):** If dissipation does not → k_BT ln2 as τ→∞ (within trajectory-statistics error), or the excess does not scale as 1/τ, or an "optimal" protocol beats 4× improvement → integrator bias / non-quasi-static / bug.

3. **Mismatch-cost verification (Kolchinsky–Wolpert).** For a small stochastic map (e.g., noisy bit-reset CTMC), compute EP for many input distributions p₀ and verify EP(p₀) − EP(q₀) = k_B·[D(p₀‖q₀) − D(p_τ‖q_τ)]. Tiny compute.
   - **NULL-CASE (first):** If EP is not minimized at the predicted q₀, or the KL-drop identity fails numerically, the implementation is wrong (theorem is proven). A clean pass validates your stochastic-thermo engine for downstream use.

4. **Entropy-production inference from short trajectories (Manikandan et al. 2020).** Generate synthetic NESS trajectories, apply the short-time TUR estimator, compare to known EP. Colab-native (this is what the original paper did).
   - **NULL-CASE (first):** The TUR gives a *lower* bound, so a valid estimate must be ≤ true EP; an estimate exceeding true EP, or failure to converge with trajectory count, means a bug — the demo fails.

**Tier B — reachable but with caveats (careful modeling needed):**

5. **Quantum TUR violation in a driven few-level open system.** Simulate a 2–3-level Lindblad system (e.g., three-level maser à la Kalaee–Wacker–Potts) and exhibit precision below the classical TUR floor. QuTiP-scale Lindblad integration is easy; the hard part is correctly defining the quantum current via full counting statistics.
   - **NULL-CASE (first):** If, after correct full-counting-statistics, no parameter regime shows sub-TUR precision, either coherence is insufficient or the current has been classicalized — demotes the "quantum anomaly" claim. Guard against a *spurious* violation from an ill-defined current (false positive).

6. **Information-ratchet simulation + modularity cost (Mandal–Jarzynski / Boyd–Mandal–Crutchfield).** Simulate a tape-fed ratchet, measure work extraction vs. Shannon-entropy change of the tape, and quantify modularity dissipation. Small compute; subtlety is estimating the tape's entropy rate correctly (hidden-Markov).
   - **NULL-CASE (first):** If work extraction violates the IPSL bound (exceeds tape entropy change × k_BT ln2), your entropy-rate estimate is wrong. If modularity dissipation comes out ≤ 0, you have not separated local from global operation → kills the "measured the cost of modularity" claim.

**Tier C — NOT reachable on single-GPU / honest negative:**

7. **First-principles quantum many-body Landauer (à la Aimet et al.).** Real-time evolution of an interacting 1D field with tomographic reconstruction is a cold-atom experiment + tensor-network problem; **beyond Colab** past small spin chains. Small spin-chain (≤ ~16 sites) analogues via exact diagonalization / small MPS ARE reachable but will not reproduce the QFT continuum limit. **NO** at the field level.
8. **Turing-machine thermodynamics numerics (Kolchinsky–Wolpert 2020).** The interesting regime (universality, unbounded tape) is not simulable; only toy finite-tape automata are, and those lack the universal structure. **Largely NO.**

---

## 3) Strongest critiques, failed replications, live controversies

- **Norton (Earman–Norton 1999; Norton 2011, 2013) — the foundational-circularity critique.** Norton argues Landauer's principle has never been *independently* proven: derivations invoke the second law (making Maxwell-demon "exorcism" circular), and microscale fluctuations invalidate the assumed thermodynamic reversibility, so any real process dissipates *in excess* of the bound — rendering it "moot" as a no-go. **A live, serious dispute in philosophy of physics, not crankery.** Confidence it is unresolved: **HIGH.**
  - **Rebuttals:** Ladyman, Presnell, Short, Groisman 2007 (thermodynamic-cycle proof); Ladyman–Robertson 2014; and **"Shakin' All Over: Proving Landauer's Principle without neglect of fluctuations"** (arXiv:2007.11748) — proves LP within statistical mechanics without assuming reversibility or neglecting fluctuations, yet explicitly concedes the theorem is "moot if the processes involved depart sufficiently far from thermodynamic reversibility." **Net assessment (inference):** the *statistical-mechanics theorem* stands; Norton's separate points — that the bound is not *independent* of the second law, and that real fast processes dissipate more — are also correct. These are compatible, not mutually exclusive.
- **Kish, Porod, Ferry et al. — Landauer-denialism.** Kish ("Critical Remarks on Landauer's principle," arXiv:1412.2166) and Porod/Ferry argue the logical-state vs. thermodynamic-ensemble-state identification is a category error and that erasure experiments (e.g., Bérut) are "flawed" (barrier-control artifacts). **This is the fringe/minority position** (see §6); the mainstream and fluctuation-theorem-grounded proofs answer it. Named for completeness. Confidence Kish is wrong: **MODERATE–HIGH.**
- **"Sub-k_BT ln2" / "beyond Landauer" experiments — genuine but semantically loaded.** Ciampini et al. 2025; earlier Orlov et al. 2012 (sub-k_BT for *logically reversible* ops); Konopik et al. "Nonequilibrium information erasure below kT ln2" (EPL); Klaers 2019 (squeezed thermal memory, PRL 122, 040602). **Controversy = wording, not physics:** these beat the *equilibrium* bound using nonequilibrium/squeezed/athermal resources; none violate the second law or a correctly generalized Landauer bound. Steer readers away from "computation can be free" misreadings.
- **Whether specific experiments truly reach the bound.** Because saturation is asymptotic (quasi-static), no finite-time experiment reaches k_BT ln2 exactly; all report approach + extrapolation. Riechers–Gu sharpen this in the quantum case: **generic quantum inputs provably cannot saturate the bound at all.** Live tension between "we verified Landauer" headlines and this impossibility result.
- **TUR scope/tightness disputes.** The TUR is provably violated quantumly and under broken time-reversal symmetry; work continues on whether a *universal* quantum TUR exists (Hasegawa's forms are valid but loose). No single agreed quantum TUR. **Open.**
- **Semantic-information framework critiques.** Kolchinsky–Wolpert 2018's definition (semantic info = syntactic info causally necessary for self-maintenance, via counterfactual scrambling) is mathematically precise but (i) requires choosing a "viability function"/coarse-graining that is not unique, and (ii) its identification with "meaning"/"agency" is philosophically contested. Follow-ups (e.g., "Causal Leverage Density," arXiv:2407.07335) try to remove the viability-function dependence, implicitly conceding the original is framework-dependent. **Assessment: the math is sound; the interpretation is conjectural.** Confidence the interpretive claims are settled: **LOW.**

---

## 4) The 5 most load-bearing references (one line each on WHY)

1. **Gingrich, Horowitz, Perunov, England 2016, PRL 116, 120601** — *the* proof that dissipation bounds all steady-state current fluctuations; converts the TUR from conjecture to theorem and underpins all downstream inference.
2. **Wolpert 2019, J. Phys. A 52, 193001** — the field-defining review that reframes the whole thermodynamics of computation beyond erasure (Landauer + mismatch + modularity + Turing); the map for axis 3.
3. **Bérut et al. 2012, Nature 483, 187** — first experimental contact with the Landauer bound; the empirical anchor everything else is measured against.
4. **Riechers & Gu 2021, PRA 104, 012214** — the sharpest *anomaly*: proves the Landauer bound is saturable by at most one quantum input state, so "reaching k_BT ln2" is generically impossible.
5. **Still, Sivak, Bell, Crooks 2012, PRL 109, 120604** — proves predictive inefficiency = thermodynamic dissipation arbitrarily far from equilibrium; the bridge from computation to prediction/learning.

---

## 5) NULL-CASES (compact, one per §2 idea — restated for the workstream skeleton)

- **(A1 TUR/KUR/TUT):** A 3-state Markov network showing TUR violation without broken time-reversal, or failure of the TUT equality for the optimal charge → code is wrong (theorems are exact).
- **(A2 Langevin erasure):** Dissipation not → k_BT ln2 as τ→∞, or excess not ∝ 1/τ, or optimal protocol >4× improvement → integrator bias / non-quasi-static / bug.
- **(A3 mismatch cost):** EP not minimized at predicted q₀, or KL-drop identity fails numerically → implementation error.
- **(A4 EP inference):** Estimator exceeds true EP (must be a lower bound) or fails to converge → method demo fails.
- **(B5 quantum TUR):** No sub-TUR regime after correct full-counting statistics → no quantum anomaly; spurious violation from ill-defined current → false positive to reject.
- **(B6 info ratchet):** Work extraction exceeds IPSL bound, or modularity dissipation ≤ 0 → entropy-rate / locality error.
- **(C7, C8):** If your "field-theory" or "universal Turing" numerics run comfortably on Colab and reproduce the continuum/universal claims, you have almost certainly built a toy that does NOT capture the regime — the null-case is "it was too easy."

---

## 6) Adjacent fringe claims to steer around (with reason)

- **"Maxwell's demon defeats the second law" / perpetual motion of the second kind.** Fringe: the demon's memory erasure pays k_BT ln2 (Bennett); modern fluctuation-theorem accounting closes every proposed loophole. Any claim of net work extraction over a full cycle *including memory reset* is wrong.
- **"Computation can be made thermodynamically free" / "sub-k_BT ln2 with no cost."** Fringe when unconditional: below-k_BT ln2 erasure always spends a resource (nonequilibrium/squeezed/athermal initial state, or logical reversibility that isn't true erasure). The correctly generalized bound is never beaten.
- **Landauer-denialism (Kish; some Porod/Ferry readings).** Fringe: relies on a logical-vs-thermodynamic-state category argument that fluctuation-theorem proofs (and Bérut/Jun experiments) answer. Note: Norton's *foundational* critique is distinct and serious — do NOT lump it with denialism.
- **"Sub-Landauer via quantum measurement magic / negative-temperature free lunches."** Fringe when it ignores the cost of preparing the resource state or the measurement/feedback ledger.
- **Mystical / "information is a fundamental substance" info-thermodynamics** (consciousness-causes-collapse styling; "the universe is a bit-erasing computer and that's dark energy"; pan-informational metaphysics). Fringe: untestable, no operational bound, not connected to measurable heat/work.
- **Over-strong "semantic information solves meaning/consciousness" readings** of Kolchinsky–Wolpert. Fringe extrapolation: the framework quantifies causally-necessary correlations for self-maintenance; it does not resolve intentionality or phenomenal meaning, and its authors do not claim it does.
- **"Bekenstein/Landauer bounds prove the brain/universe computes at the Planckian limit."** Fringe when used to assert biological computation operates at fundamental limits; real biological machines dissipate orders of magnitude above the Landauer floor.

---

**Overall epistemic summary (inference):** Axis 1's bound is solid as a statistical-mechanics theorem and empirically corroborated, with the genuinely surprising modern anomaly being Riechers–Gu (generic quantum states cannot saturate it) and the semantic trap of "beyond Landauer" experiments (which exploit resources, not loopholes). Axis 2's TUR is a clean theorem near equilibrium that provably breaks quantumly and far from equilibrium — a textbook "intuition trained on the classical/commutative pays a measurable price" site, with the KUR/TUT as the sharpened replacements. Axis 3's mismatch and modularity costs are theorem-level and highly Colab-tractable; the semantic-information layer is where rigor gives way to conjecture. For a small-compute program the richest, safest digs are §2 items A1–A4: each instantiates a *proven* identity, so the null-case doubles as a correctness test of your stochastic-thermodynamics engine.