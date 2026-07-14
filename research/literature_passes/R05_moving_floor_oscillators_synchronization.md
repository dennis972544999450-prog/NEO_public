# R05 · The Moving Floor: Oscillators & Synchronization — Dig-Site Literature Pass (OMPU / The Anomaly Dig)

## TL;DR
- **Low-dimensional structure is real and provably exact under sharp hypotheses** (Watanabe–Strogatz for identical sinusoidally-coupled oscillators; Ott–Antonsen for the Lorentzian/analytic thermodynamic limit) — but the exactness is *fragile*: heterogeneity beyond Lorentzian, non-sinusoidal coupling, common/multiplicative noise, and finite N all break it, and the 2023–2026 frontier (circular cumulants, collective coordinates, complex-Riccati and higher-order/hypergraph extensions) is essentially the science of *how* it breaks.
- **Chimeras are experimentally real across optical, chemical, mechanical, and neuromorphic platforms, but at finite N they are generically long transients, not eternal states.** Wolfrum & Omel'chenko (PRE 84, 015201(R), 2011) established verbatim that "the incoherent motion, which is described in the thermodynamic limit as a stationary behavior, in finite size systems appears as weak spatially extensive chaos"; the mean lifetime before collapse grows exponentially in N (chimeras "disappear quickly for N ≈ 20" but look stable for N > 100). The "are they stable?" dispute is largely a fight over N and definitions; the cleanest rigorous object is the Ashwin–Burylko weak chimera.
- **Quantum synchronization is a legitimate, now-experimentally-realized frontier (2020–2025 spin-1, trapped-ion, optomechanics), but the "vacuum/zero-point field as a universal synchronization substrate" claim is fringe.** The honest answer to Q3 is NO: no rigorous program treats vacuum fluctuations as a universal sync substrate; what exists nearby is Casimir/virtual-photon *coupling* of specific oscillators (ordinary QED), plus a separate fringe consciousness literature (Keppler ZPF, Orch-OR/Fröhlich) to steer around.

---

## 1) State of the Art 2023–2026 (primary sources first)

### 1A. Watanabe–Strogatz / Ott–Antonsen: exact conditions and what breaks them

**Foundational anchors (theorems, explicitly):**
- **Watanabe & Strogatz (WS), PRL 70, 2391 (1993); Physica D 74, 197 (1994).** *Theorem:* a population of N identical, globally and sinusoidally coupled phase oscillators (originally overdamped Josephson junctions in a series array with common load) has **N−3 constants of motion for all N ≥ 3**; the dynamics collapse to 3 collective ("macroscopic") variables via a time-dependent Möbius transformation. Exactness requires **identical oscillators** and **sinusoidal (first-harmonic) global coupling**. In the weak-coupling / integrable limit the phase space is foliated by invariant 2-tori.
- **Ott & Antonsen (OA), Chaos 18, 037113 (2008); Chaos 19, 023117 (2009).** *Result:* for a *continuum* of oscillators with frequencies drawn from a Lorentzian (Cauchy) distribution and sinusoidal coupling, the Fourier coefficients of the phase density admit the ansatz aₙ = a¹ⁿ, defining a 2-D invariant manifold (the "OA manifold") on which the order parameter obeys a closed low-dimensional ODE. Exactness requires: (i) thermodynamic limit N→∞; (ii) Lorentzian frequency heterogeneity (poles in the lower half-plane); (iii) sinusoidal coupling; (iv) initial conditions **on** the OA manifold.
- **Marvel, Mirollo & Strogatz, Chaos 19, 043104 (2009).** *Theorem:* the WS reduction *is* the action of the Möbius group (3-parameter fractional linear transformations of the unit disk); the N−3 constants of motion are the functionally independent cross-ratios of the phases. This exposed *why* WS works and unified WS/OA. (The paper also notes numerics on Josephson-junction arrays suggest the invariant manifolds often contain 3-D regions of neutrally stable chaos.)

**Attractiveness of the OA manifold — the subtle part (mark carefully):**
- The OA manifold is **only neutrally stable for perfectly identical, noise-free oscillators** — it is an invariant manifold, not an attractor, in that case (Pikovsky & Rosenblum showed identical *macroscopic* initial conditions can have very different microscopic transients).
- **Ott & Antonsen, Chaos 19, 023117 (2009)** proved that with **genuine frequency spread (Lorentzian, nonzero width) and analytic initial phase densities**, trajectories are *attracted* to the OA manifold. **Pietras & Daffertshofer, Chaos 26, 103101 (2016)** extended the attractiveness proof to parameter-dependent oscillatory systems (e.g., theta-neuron networks) and to time-dependent/multidimensional parameters and non-global topologies, under stated conditions. *Open problem (per that literature):* proving exact (likely non-exponential) decay rates for **non-analytic** initial conditions remains unsolved.

**2023–2026 extensions (primary sources):**
- **Circular cumulants (Tyulkina, Goldobin, Klimenko, Pikovsky; Goldobin & Dolmatova, Phys. Rev. Research 1, 033139 (2019)).** Reformulate the Kuramoto–Daido order parameters as "circular cumulants." *Result (proved):* the **OA ansatz is the single-cumulant truncation** — "the only admissible truncation" — and is a rigorous first-order object; higher cumulants systematically capture departures from OA caused by noise. Two-cumulant reductions generalize both OA and the Gaussian ansatz.
- **Dolmatova, Tyulkina & Goldobin, J. Phys. A (2023), arXiv:2305.18027.** Circular-cumulant reductions for populations with **non-Gaussian (α-stable) white noise** — two-cumulant equations derived. This is the live 2023 edge: OA breaks under multiplicative/non-Gaussian noise, and circular cumulants are the repair.
- **Complex-Riccati generalization: Cestnik & Pikovsky (context) and PRL 132, 057201 (29 Jan 2024)** ("Integrability of a Globally Coupled Complex Riccati Array"). *Result:* an exact dimensionality reduction for arbitrary globally-coupled complex-valued Riccati equations that **generalizes WS** and **includes quadratic integrate-and-fire (QIF) neurons** as the real-valued special case — extends the "integrable" class beyond pure phase oscillators to a family of phase-amplitude oscillators.
- **Cestnik & Pikovsky, Chaos 32, 113126 (2022)** — exact finite-dimensional reduction for **noisy** oscillators linking OA and WS; shows for Cauchy noise the collective dynamics reduces to 6 dimensions (and asymptotically to the 2-D OA manifold).
- **Higher-order interactions / hypergraphs (2020–2026):** Skardal & Arenas (Commun. Phys. 3, 218, 2020) showed triadic/higher-order coupling produces abrupt (explosive) synchronization with OA-tractable reductions for specific coupling forms (e.g., sin(2θⱼ−θₖ−θᵢ)). Recent primary work: "Low-dimensional Watanabe–Strogatz approach for Kuramoto oscillators with higher-order interactions" (2025); León, Muolo, Hata & Nakao, "Theory of phase reduction from hypergraphs to simplicial complexes," Physica D (2025); Zhang, Skardal, Battiston, Petri & Lucas, "Deeper but smaller: higher-order interactions increase linear stability but shrink basins," Sci. Adv. 10, eado8049 (2024); "A double explosive Kuramoto transition in hypergraphs," Phys. Rev. Research 7, L022049 (2025); Suman & Jalan, "Finite-size effect in Kuramoto oscillators with higher-order interactions," Chaos 34, 101101 (2024).
- **Collective coordinates (Gottwald, Chaos 25, 053111 (2015); Hancock & Gottwald; Smith & Gottwald, Chaos 30, 093107 (2020); Yue, Smith & Gottwald, Phys. Rev. E 101, 062213 (2020)).** A complementary reduction that, unlike OA, works for **finite N and complex topologies** by positing an ansatz shape for the synchronized cluster and projecting the dynamics onto a few coordinates. The 2020 Kuramoto–Sakaguchi work showed **non-entrained "rogue" oscillators** must be included for accuracy — a concrete statement of how finite-N reality departs from the mean field.

### 1B. Chimera states: experiments and finite-N transients

**Experimental realizations (primary, chronological):**
- **Optical/electro-optical:** Hagerstrom, Murphy, Roy, Hövel, Omelchenko & Schöll, *Nat. Phys.* 8, 658 (2012) — chimeras in a liquid-crystal spatial-light-modulator coupled-map lattice (1-D and 2-D). Critique at the time (Smart, *Phys. Today* 2012): coupling was computer-mediated.
- **Chemical:** Tinsley, Nkomo & Showalter, *Nat. Phys.* 8, 662 (2012); Nkomo, Tinsley & Showalter, *PRL* 110, 244102 (2013) — Belousov–Zhabotinsky discrete chemical oscillators; behavior differed from phase-oscillator predictions.
- **Mechanical:** Martens, Thutupalli, Fourrière & Hallatschek, *PNAS* 110, 10563 (2013) — metronomes on two coupled swings; chimera (one swing synchronized, one incoherent) appears in a "competition zone" between in-phase and anti-phase modes at intermediate spring coupling. Addressed the computer-coupling critique (purely mechanical coupling).
- **Newer (2023–2026):** Makinwa, Inaba, Inagaki et al. (NTT), *Commun. Phys.* 6 (2023), arXiv:2209.12087 — chimera states in a **photonic spiking neural network** of degenerate optical parametric oscillators (identical neurons, homogeneous interactions). Plus a large 2024–2025 simulation literature on neuronal/FitzHugh–Nagumo, higher-order, and wheel/hyperring networks.

**Finite-N transient result (the load-bearing negative result):**
- **Wolfrum & Omel'chenko, Phys. Rev. E 84, 015201(R) (2011)** — *"Chimera states are chaotic transients."* Abstract, verbatim: "our calculations of the Lyapunov spectrum show that the incoherent motion, which is described in the thermodynamic limit as a stationary behavior, in finite size systems appears as weak spatially extensive chaos." Chimeras collapse suddenly to the fully coherent state; **the mean lifetime before collapse grows EXPONENTIALLY with N** (type-II supertransient behavior). Practically (per the authors' follow-up, Sieber, Omel'chenko & Wolfrum, PRL 112, 054102 (2014)): chimeras "disappear quickly for N ≈ 20" but "appear as stable objects for any observable timespan if N > 100." The chaotic part of the Lyapunov spectrum tends to 0 as N→∞. *Note:* the Rapid Communication states the exponential-in-N growth law numerically (via Lyapunov spectrum + lifetime statistics); no closed-form analytic prefactor/exponent is published.
- **Independent experimental corroboration:** Rosin et al., Phys. Rev. E 90, 030902(R) (2014) — in Boolean phase oscillators, average transient time increases exponentially with network size and is well-modeled as a Poisson process.
- **Counterpoint (infinite-N stability is genuine):** Omel'chenko, Nonlinearity 26, 2469 (2013) proved that in the continuum limit stationary coherence–incoherence patterns exist and can be **stable** along the OA manifold; and Suda & Okuda, plus the finite-time-Lyapunov work (Sci. Rep. 6, 29213 (2016)), showed some models support **stable** chimeras at other α. So "chimeras are chaotic transients" is a statement about a *specific finite-N ring at a specific α (≈1.46)*, not a universal law.

**Definition disputes / weak chimeras (mark as the rigorous object):**
- **Ashwin & Burylko, Chaos 25, 013106 (2015)** — defined a **weak chimera** as an invariant set with partial frequency synchronization (two or more frequency-locked oscillators coexisting with drifting ones). *Theorem:* weak chimeras **cannot appear in globally coupled or too-small S_N-symmetric networks**; they exist in networks of 4, 6, 10 indistinguishable oscillators with appropriate (less symmetric but transitive) coupling. **Bick & Ashwin, Nonlinearity 29, 1468 (2016)** — chaotic weak chimeras and their persistence.
- Experimental weak chimeras: Wojewoda et al. (3 pendula, 2016); Hart, Bansal, Murphy & Roy (4 optoelectronic oscillators, 2016). This is the live controversy: much of the "chimera" experimental zoo does not meet a rigorous definition, and "persists in a finite simulation" ≠ "stable state."

### 1C. Quantum synchronization: the legitimate frontier

**Theory anchors:**
- **Lee & Sadeghpour, PRL 111, 234101 (2013)** and **Walter, Nunnenkamp & Bruder, PRL 112, 094102 (2014); Ann. Phys. 527, 131 (2015)** — quantum van der Pol (vdP) oscillator; phase locking is **more robust in the quantum model** than the classical equivalent; trapped ions proposed as the platform.
- **Roulet & Bruder, PRL 121, 053601 and 121, 063601 (2018)** — *"Synchronizing the smallest possible system":* qubits **cannot** synchronize (no limit cycle); a **single spin-1** is the minimal system that phase-locks to a weak drive. A clean theorem-like negative + positive result.

**Experiments (2020–2025, primary):**
- **Laskar, Adhikary, Mondal, Katiyar, Vinjanampathy & Ghosh, PRL 125, 013601 (2020)** — quantum phase synchronization in **spin-1 atoms**. Abstract, verbatim: "In experiments with dilute ensemble of laser cooled spin-1 ⁸⁷Rb atoms, we observe phase difference of spin coherences to synchronize with phases of external classical fields... Furthermore, we observe a blockade of synchronization due to quantum interference and emergence of Arnold-tongue-like features."
- **Koppenhöfer, Bruder & Roulet, Phys. Rev. Research 2, 023026 (2020)** — quantum synchronization on the **IBM Q** superconducting quantum computer (digital simulation of spin-1).
- **Krithika, Solanki, Vinjanampathy & Mahesh, Phys. Rev. A 105, 062206 (2022)** — quantum entrainment in a **nuclear-spin (NMR)** system.
- **Zhang et al., Phys. Rev. Research 5, 033209 (2023)** — quantum synchronization of a **single trapped-ion qubit**.
- **Li et al., Sci. Adv. 11, eady5649 (2025)** — experimental realization and synchronization of a quantum vdP oscillator.
- **Liu, Wu, Moore, Haeffner & Wächtler, arXiv:2509.18423 (2025), to appear Phys. Rev. X** — **first observation of mutual synchronization between two quantum vdP oscillators** (two axial motional modes of a ⁴⁰Ca⁺–⁴⁴Ca⁺ trapped-ion crystal, engineered dissipative coupling). Key genuinely-quantum feature: the synchronized state is a fixed *relative* phase, **inaccessible to local measurements** and revealed only by joint readout — unlike classical sync, observable per-oscillator. The authors explicitly flag as open "whether genuinely quantum features persist" beyond two oscillators.

**Optomechanics (light-mediated mechanical sync):**
- **Zhang, Wiederhecker, Manipatruni, Barnard, McEuen & Lipson, PRL 109, 233906 (2012)**; **Zhang, Shah, Cardenas & Lipson, PRL 115, 163902 (2015)** — synchronization of silicon-nitride micromechanical oscillators coupled "purely through an optical radiation field"; the 2015 paper reports verbatim that "the phase noise of the synchronized oscillators can be improved by almost 10 dB below the phase noise limit for each individual oscillator." **Bagheri et al., PRL 111, 213902 (2013); Matheny et al., PRL 112, 014101 (2014); Heinrich, Ludwig, Qian, Kubala & Marquardt, PRL 107, 043603 (2011)** (collective dynamics in optomechanical arrays, theory). Optomechanical chimeras: Pelka, Peano & Xuereb, Phys. Rev. Research 2, 013201 (2020).

**Is "quantum synchronization" a genuinely distinct/quantum phenomenon? (contested):**
- The survey **"Synchronization in the quantum regime" (arXiv:2606.21226, 2026)** lays out the conceptual obstacles: Heisenberg uncertainty forbids classical phase-space trajectories; linearity of quantum dynamics appears to preclude limit cycles; no Hermitian phase operator exists. It argues genuinely-quantum synchrony (e.g., measurement-induced, arXiv:2306.12986) does exist.
- **Critique / deflationary view:** L.-C. Kwek, "No synchronization for qubits," *Physics* 11, 75 (2018); much of the debate is that reported quantum synchronization is often *weak* (small Pearson/synchronization measures, e.g. saturating far below the classical bound in optomechanics). Multiple incompatible measures (Husimi-Q phase distributions, Pearson factor, quantum information/correlation measures) mean "how quantum is it" is genuinely unsettled (see arXiv:1610.05060, 2006.13623). *Inference (flagged as mine):* the field is real but the "genuinely quantum" label is claim-by-claim, not settled in general.

---

## 2) Open problems ranked by tractability for single-GPU / Google Colab

Coupled-oscillator ODE/SDE integration is extremely cheap: N ~ 10²–10⁵ Kuramoto-type systems integrate in seconds–minutes on Colab. Ranked most→least tractable. **Each idea states its NULL-CASE first.**

**Tier 1 — Directly doable this week (pure ODE/SDE integration):**

1. **Finite-N OA-manifold departure via circular cumulants under non-Gaussian noise.**
   - **NULL-CASE (kills/demotes it):** If, across noise strengths and N, the second circular cumulant κ₂ stays ≤ your integration error floor and the two-cumulant reduction never beats OA by more than numerical noise, then there is no measurable finite-N/non-Gaussian correction to report — the anomaly is absent.
   - Why promising if it survives: Dolmatova–Tyulkina–Goldobin (2023) give the α-stable-noise reduction analytically; reproducing and stress-testing where the two-cumulant truncation fails is a clean, bounded target.

2. **Wolfrum–Omel'chenko exponential-lifetime scaling: measure the exponent.**
   - **NULL-CASE:** If mean chimera lifetime does NOT grow exponentially in N (e.g., fits a power law, or saturates) across your α range, the supertransient claim fails to reproduce — a real negative result. Also null if lifetimes are so variable that no scaling law is statistically distinguishable given feasible ensemble sizes.
   - Why promising: exponential-in-N is a sharp, falsifiable prediction; measuring the prefactor/exponent as a function of coupling range R and phase lag α is under-explored and cheap.

3. **Weak-chimera existence/stability in minimal (N = 4, 6, 10) networks.**
   - **NULL-CASE:** If, for the Ashwin–Burylko coupling classes, you cannot locate a numerically robust invariant set with partial frequency locking (all trajectories collapse to full sync or full drift), the weak chimera is absent for your parameters.
   - Why promising: tiny systems, rigorous target, directly comparable to a published theorem.

**Tier 2 — Doable with modest effort:**

4. **Higher-order/hypergraph "deeper but smaller basins" claim (Zhang et al. 2024).**
   - **NULL-CASE:** If Monte Carlo basin sampling shows higher-order coupling does NOT shrink basins of the synchronized state (or does not increase linear stability), the headline effect fails to replicate.
   - Why promising: basin estimation is embarrassingly parallel on a GPU; the claim is quantitative.

5. **Collective-coordinate accuracy vs. "rogue oscillators" (Yue–Smith–Gottwald 2020).**
   - **NULL-CASE:** If the collective-coordinate reduction reproduces the full Kuramoto–Sakaguchi order parameter to within tolerance **without** explicitly modeling non-entrained oscillators, then rogue oscillators are not load-bearing for your regime — demoting the specific claim.

**Tier 3 — Harder (open quantum systems; small Hilbert spaces only):**

6. **Two/three quantum vdP oscillators: does "genuinely quantum" survive beyond N = 2?**
   - **NULL-CASE:** If, in a Lindblad simulation of 3 dissipatively-coupled quantum vdP oscillators (truncated Fock space), every synchronization signature is reproducible by a classical stochastic (semiclassical/truncated-Wigner) model, there is no genuinely-quantum feature to claim — exactly the open question Liu et al. (2025) flagged.
   - Feasibility caveat: Fock-space truncation makes 3 oscillators borderline for Colab RAM; 2 is comfortable. **This is the honest compute wall.**

**NOT tractable on small compute (flagged):** any many-body quantum sync beyond a handful of modes; large-scale optomechanical arrays; anything requiring experimental hardware.

---

## 3) Strongest critiques, failed replications, live controversies (who disputes what)

- **"Chimeras are chaotic transients" (Wolfrum & Omel'chenko 2011) vs. "chimeras can be stable."** Suda & Okuda and the Panaggio–Abrams review note the 2011 conclusion was drawn at a single α (≈1.46); other α and the continuum limit (Omel'chenko 2013) give stable chimeras. **Resolution (inference, flagged):** both are right — finite-N rings at generic parameters give exponentially-long transients; the infinite-N manifold can be genuinely stable. The dispute is semantic unless N and α are stated.
- **What counts as a chimera (definition dispute).** Ashwin & Burylko (2015) and Bick argue most "chimera" claims lack a checkable definition; "persists in simulation" conflates long transients with stability. The weak-chimera definition is the rigorous fix but captures only a subset of the phenomenology.
- **Computer-mediated coupling critique.** Smart (Phys. Today, 2012) questioned whether the Roy optical and early experiments were "real" physical coupling; the Martens metronome experiment (2013) is the standard rebuttal (purely mechanical).
- **Is quantum synchronization "quantum"?** Kwek ("No synchronization for qubits," 2018) and the proliferation of incompatible measures mean the "genuinely quantum" label is disputed case-by-case. Reported effects in optomechanics are weak (far from the theoretical synchronization bound).
- **Vacuum-as-synchronization-substrate:** no scientific dispute because there is no rigorous claim to dispute (see §6). The adjacent *consciousness* claims (Keppler ZPF; Orch-OR/Fröhlich) are disputed by Tegmark (2000) and Reimers et al. (2009) — see §6.

---

## 4) The 5 most load-bearing references (one line each on WHY)

1. **Ott & Antonsen, Chaos 18, 037113 (2008).** The reason low-dimensional behavior exists at all in the thermodynamic limit — every modern reduction is a correction to, or generalization of, this manifold.
2. **Watanabe & Strogatz, Physica D 74, 197 (1994)** (+ **Marvel–Mirollo–Strogatz, Chaos 19, 043104 (2009)** as its group-theoretic explanation). The exact finite-N reduction and the Möbius-group structure that make "hidden low-dimensional structure" a theorem, not a coincidence.
3. **Wolfrum & Omel'chenko, Phys. Rev. E 84, 015201(R) (2011).** The single most important *negative* result: at finite N chimeras are exponentially-long chaotic transients — the measurable price of extrapolating from the continuum to reality.
4. **Ashwin & Burylko, Chaos 25, 013106 (2015).** Gives the field its only rigorous, checkable chimera definition (weak chimera) and a non-existence theorem for globally-coupled/too-small networks.
5. **Liu, Wu, Moore, Haeffner & Wächtler, arXiv:2509.18423 (2025).** The first mutual quantum-vdP synchronization experiment; defines the current quantum frontier and its honest open question (does "genuinely quantum" survive N > 2?). (For the noise/heterogeneity breakdown edge, **Goldobin & Dolmatova / Tyulkina et al., Phys. Rev. Research 1, 033139 (2019)** on circular cumulants is the runner-up.)

---

## 5) Null-cases — consolidated (each experiment idea's kill condition, restated)

- **Circular-cumulant correction:** dead if κ₂ never exceeds numerical error / two-cumulant model never beats OA.
- **Chimera lifetime scaling:** dead if lifetime is not exponential in N, or statistically indistinguishable.
- **Weak chimera in small nets:** dead if no partial-frequency-locked invariant set exists for Ashwin–Burylko couplings.
- **Higher-order basin shrinkage:** dead if basins do not shrink / stability does not rise with higher-order coupling.
- **Rogue-oscillator load-bearingness:** demoted if collective coordinates are accurate without modeling rogues.
- **Quantum-vdP beyond N=2:** dead if a semiclassical/truncated-Wigner model reproduces every sync signature (no quantum advantage).

---

## 6) Adjacent fringe claims to steer around (and why each is fringe)

- **"Vacuum / zero-point fluctuations as a UNIVERSAL synchronization substrate" (the Q3 target).** **Verdict: fringe / no rigorous program exists.** *Confirmed plainly:* there is no peer-reviewed physics program treating the quantum vacuum as a substrate that synchronizes oscillators universally. What *legitimately* exists nearby, and must not be conflated with it:
  - **Casimir / virtual-photon coupling of mechanical oscillators** — Di Stefano, Settineri, Macrì, Ridolfo, Stassi, Kockum, Savasta & Nori, *PRL* 122, 030402 (2019). Their abstract is explicit about the scope: "by tuning the two mechanical oscillators into resonance, energy is exchanged between them at the quantum level. This coherent motional coupling is enabled by the exchange of virtual photon pairs, originating from the dynamical Casimir effect. The process proposed here shows that the electromagnetic quantum vacuum is able to transfer mechanical energy somewhat like an ordinary fluid" — i.e., a coupling between *two specific bodies*, not a universal sync substrate. Also Fong et al., *Nature* 576, 243 (2019) (phonon heat transfer across vacuum via quantum fluctuations); non-reciprocal Casimir energy transfer (arXiv:2102.12857). All are ordinary QED: vacuum fluctuations mediate a short-range *force/coupling*; none claim synchronization-as-substrate.
  - *Inference (flagged):* the fringe claim likely equivocates between "vacuum fluctuations can couple two oscillators" (true, short-range, engineered) and "vacuum is a universal sync field" (unsupported). The gap is enormous and unbridged.
- **Zero-point-field theories of consciousness (Keppler, DIWISS; Frontiers in Human Neuroscience 2024–2025; phys.org Dec 2025).** **Fringe.** Proposes consciousness arises from resonant brain–ZPF coupling producing synchronized (gamma/beta) critical dynamics. No independent experimental confirmation; mechanism (macroscopic QED coherence in warm wet tissue) faces the same decoherence objection as Orch-OR. Treat as speculative, not established.
- **Orch-OR / Fröhlich condensation in microtubules (Penrose–Hameroff).** **Fringe / contested.** Fröhlich's underlying physics (H. Fröhlich, *Int. J. Quantum Chem.* 2, 641 (1968); *Phys. Lett. A* 26, 402 (1968)) is legitimate condensed-matter theory. But **Tegmark, Phys. Rev. E 61, 4194 (2000)** computed microtubule decoherence times of **~10⁻¹³ s** (and ~10⁻²⁰ s for neuron firing) — far shorter than the ~10⁻³–10⁻¹ s neural dynamical timescales — concluding the brain is effectively classical and that "this conclusion disagrees with suggestions by Penrose and others that the brain acts as a quantum computer." **Reimers, McKemmish, McKenzie, Mark & Hush, PNAS 106, 4219 (2009)** classified Fröhlich condensation into weak/strong/coherent regimes and concluded the **coherent (quantum) regime is "inaccessible in a biological environment"** and the Orch-OR model is "untenable," noting "despite intense research, no unambiguous example has been documented." Hagan–Hameroff–Tuszynski (PRE 65, 061901 (2002)) rebutted with 10⁻⁵–10⁻⁴ s; still contested, still no unambiguous experimental example of *coherent (quantum)* Fröhlich condensation in a living system as of 2023–2026 (the 2015 Lundholm/Katona lysozyme result, *Struct. Dyn.* 2, 054702, is a driven, non-living crystal interpreted as a weak/classical "coherent-like" state). **Steer around** the quantum-coherence-in-vivo claim; only the weak/classical regime is plausible.
- **Synchronization-based theories of consciousness (gamma-binding overreach).** The gamma-synchrony "solution to the binding problem" (Crick–Koch, Singer, Fries "communication through coherence") is *legitimate neuroscience as a correlate*, but overreaches when stated as *the* mechanism of consciousness. Pockett & Holmes (2009), an intracranial-EEG study, found the opposite of the naive prediction: "For both gamma and beta passbands, synchrony measurements showed more widespread phase synchrony in the unconscious than the conscious state... We conclude that neither gamma activity per se nor phase synchrony per se are neural correlates of consciousness." Use synchrony as a correlate/tool, not as an explanation.

---

## Hygiene summary
- **Theorems (explicitly):** WS N−3 constants of motion (1994); Marvel–Mirollo–Strogatz Möbius-group action (2009); OA manifold attractiveness under Lorentzian heterogeneity + analytic ICs (2009; Pietras–Daffertshofer 2016); "OA is the only admissible circular-cumulant truncation" (2019); Ashwin–Burylko weak-chimera non-existence in global/too-small networks (2015).
- **Conjectures / open (explicitly):** exact decay rates onto OA for non-analytic ICs (open); whether genuinely-quantum sync survives beyond 2 oscillators (open, per Liu et al. 2025); universal definition of chimera (open/disputed).
- **Empirical confidence grades:** Chimeras exist experimentally — **high**. Finite-N chimeras are exponentially-long transients on a specific ring — **high** (numerics + Boolean-oscillator experiment). Exponential-in-N lifetime as a universal law — **moderate** (model/parameter dependent). Quantum vdP mutual synchronization observed — **high** (single 2025 experiment; independent replication pending → **moderate** for generality). "Quantum synchronization is genuinely quantum" in general — **low/contested**. Vacuum-as-universal-sync-substrate — **no credible evidence**.
- **Cited vs. inferred:** citations are to primary papers with DOIs/arXiv IDs where given; items explicitly marked "inference/flagged" are my synthesis, not direct claims from a single source. I have not fabricated citations; where a specific numeric prefactor is not published (e.g., the Wolfrum–Omel'chenko exponent constant), I say so. One caution: I cite the quantum-regime survey as arXiv:2606.21226 with a 2026 date and the Liu et al. quantum-vdP paper as arXiv:2509.18423 (2025) from search results; if you need to quote them formally, verify the identifiers directly, as I was unable to independently re-confirm the exact arXiv numbers beyond the returned metadata.