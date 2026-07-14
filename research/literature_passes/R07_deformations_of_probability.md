# R07 — Deformations of Probability Theory (DIG‑107, Workstream C‑7): Dig‑Site Literature Pass

**Bottom line up front:** All three sub-sites are real and mappable, but they differ sharply in health. The most load-bearing single fact: **Muraki's "exactly five independences" is a genuine theorem but a *boundary phenomenon*, not a universal law** — relax the normalization axioms and you get a two-parameter family (Gerhold–Lachs 2015); go to the two-faced/bi-free setting and there are uncountably many (Gerhold–Hasebe–Ulrich 2023). The KD sub-site is the healthiest and most experimentally live; the Tsallis q-CLT sub-site contains a settled negative result (a broken proof) wrapped in a contested repair; and categorical probability has produced real theorems but, honestly, nothing yet that classical language *could not state*.

## TL;DR
- **Muraki's "five":** THEOREM, but scope-limited to single-faced universal products with positivity + normalization + associativity (dropping only symmetry). Drop normalization → Gerhold–Lachs (r,s)-deformation of Boolean; go two-faced → uncountably many (Gerhold–Hasebe–Ulrich 2023). "Five" is conditional, not fundamental.
- **Kirkwood–Dirac negativity:** at THEOREM level a *necessary* resource for postselected-metrology advantage (Arvidsson-Shukur et al. 2020), experimentally realized (Lupu-Gladstein et al. 2022). Its link to generalized contextuality is *asymmetric*: KD-nonnegativity ⇒ noncontextuality, but the converse **fails** (Schmid et al. 2024–25). Strongest, most testable site.
- **Tsallis q-CLT:** the Umarov–Tsallis–Steinberg (2008) proof is broken — Hilhorst (2010) proved the q-Fourier transform is non-invertible for q>1, killing the uniqueness claim. q-Gaussians remain legitimate as *mechanism-backed* fits (cold atoms) but "universality" is contested. **Categorical probability** (Fritz et al.) has produced real theorems (de Finetti, zero-one, d-separation, ergodic decomposition, sufficient statistics) but these are clarifications/unifications — a clean negative to "classically inexpressible."

---

## Key Findings

1. **The "five independences" question has a definite, layered answer.** Symmetric case → three (Speicher 1997); drop symmetry, keep positivity + normalization → five (Muraki 2002/2003); drop normalization → five + a two-parameter (r,s)-Boolean deformation (Gerhold–Lachs 2015); go multi-faced → uncountably many (Gerhold–Hasebe–Ulrich 2023). Each layer is a **theorem**, not a conjecture.
2. **KD negativity is the best-established "deformation-as-resource" story.** Necessary for postselected metrological advantage (theorem, 2020), demonstrated in a photonics experiment (2022), extended to a resource for all convex resource theories (2025) and proposed as necessary for quantum computing (2025, recent/unrefereed-tier).
3. **The naive slogans in the KD literature have been corrected.** "Noncommutation ⇒ nonclassicality" is false (Arvidsson-Shukur–Chevalier Drori–Yunger Halpern 2021); "KD negativity ⇒ contextuality" is false as a converse (Schmid et al. 2024–25).
4. **The q-CLT's original proof is broken and this is settled;** whether a repaired restricted statement survives is defended by the Tsallis group and disputed in scope.
5. **Categorical probability's honest scorecard:** real, clean theorems that unify discrete/measure-theoretic/Gaussian probability and pinpoint hidden assumptions — but no new *classical* fact that was previously inexpressible.

---

## Details (State of the Art 2023–2026; primary sources first)

### Sub-site A — Muraki classification & deformations of independence

**Foundational (CITING).**
- **R. Speicher**, "On universal products," Fields Inst. Commun. 12 (1997): in the symmetric case (symmetry + associativity + universality), exactly **three** universal products — tensor, free, Boolean. THEOREM.
- **A. Ben Ghorbal & M. Schürmann**, "Non-commutative notions of stochastic independence," Math. Proc. Camb. Phil. Soc. (2002): categorical axiomatization of universal products; recovered the three symmetric ones. THEOREM.
- **N. Muraki**, "The five independences as quasi-universal products," IDAQP 5 (2002) 113–134; **"The five independences as natural products,"** IDAQP 6 (2003) 337–371: dropping the commutativity/symmetry axiom yields **exactly five** natural products — tensor, free, Boolean, monotone, anti-monotone. THEOREM. This is the anchor result.
- **N. Muraki**, "A simple proof of the classification theorem for positive natural products," Probab. Math. Statist. 33 (2013) 315–326: simplified proof under an added positivity condition (genuine states). THEOREM. (Verified to exist; PDF at math.uni.wroc.pl.)

**The axioms (CITING, standard formulation).** A universal/natural product ⊙ sends two algebraic probability spaces to a joint one *on the free product of the underlying algebras*, subject to: (i) **extension of marginals** (restricting the joint state to each factor returns φ₁, φ₂); (ii) **associativity**; (iii) a **universality/functoriality** axiom (compatibility with algebra homomorphisms — the "universal calculation rule" for mixed moments); (iv) in the symmetric case, a **commutativity/symmetry** axiom (A₁ ⊥ A₂ ⇒ A₂ ⊥ A₁). Muraki's contribution was to drop (iv); monotone and anti-monotone are the two order-dependent, mirror-image survivors. Precise moment definitions (CITING): **free** — φ(a₁···aₙ)=0 for alternating indices with each φ(aⱼ)=0; **Boolean** — φ(a₁···aₙ)=∏φ(aⱼ) for alternating indices; **tensor** — classical factorization; **monotone** — an order on the index set with a specific alternating rule (Muraki).

**Post-2010 refinements & challenges (the live part).**
- **M. Gerhold & S. Lachs**, "Classification and GNS-construction for general universal products," IDAQP 18 (2015), art. 1550004, DOI 10.1142/S0219025715500046: **dropping the two normalization conditions, the only new universal products beyond the five are a two-parameter (r,s)-deformation of the Boolean product** ("(r,s)-products"); non-symmetric when r≠s (the r≠s case attributed to Lachs solo in her thesis). THEOREM. This proves "five" depends on normalization. (No arXiv ID confirmed — cite by DOI.) *Correction to the folklore "one-parameter" phrasing: it is genuinely two-parameter.*
- **P. Varšo**, PhD thesis "Studies on positive and symmetric two-faced universal products," Greifswald 2021: in the two-faced case, the "highest coefficients" Speicher forced to be 0/1 in the single-faced setting **need not be 0/1** — the origin of the breakdown of discreteness. CITING (secondhand via GHU23).
- **M. Gerhold, T. Hasebe, M. Ulrich**, "Towards a classification of multi-faced independence: a representation-theoretic approach," arXiv:2111.07649, J. Funct. Anal. 285 (2023) 109907: verbatim — *"for many known 2-faced independences, we find that they admit continuous deformations within the class of 2-faced independences, showing in particular that, in contrast with the single faced case, this class is infinite (and even uncountable)."* THEOREM. This is the sharpest challenge to the "five is special" intuition — discreteness dissolves in the multi-faced world.
- **M. Gerhold & P. Varšo**, "Towards a classification of multi-faced independences: a combinatorial approach," arXiv:2301.01816, Algebraic Combinatorics 7 (2024) 679–711, DOI 10.5802/alco.356: finds new "exceptional" moment–cumulant relations giving symmetric universal products; **positivity of some remains OPEN** (conjecture-level; Varšo computed Hankel determinants without finding a contradiction to positivity).
- **Unifying/mixing constructions** (CITING; do NOT violate Muraki's axioms, so not counterexamples): T. Hasebe, "A three-state independence" / indented independence (arXiv:1009.1505) unifies free, monotone, anti-monotone, Boolean, c-free, c-monotone, c-anti-monotone while preserving associativity; O. Arizmendi, T. Hasebe, F. Lehner, "Cyclic independence: Boolean and monotone," Algebraic Combinatorics 6 (2023); "BMT independence" (arXiv:2309.04123, J. Funct. Anal. 2024); "Bigraph independence: a mixture of the five natural independences" (arXiv:2601.15215, 2026).

### Sub-site B — Kirkwood–Dirac negativity, metrology, contextuality

**Definition (CITING).** For bases {|a⟩},{|b⟩} and state ρ, Q(a,b)=⟨b|a⟩⟨a|ρ|b⟩; generalizes a classical joint distribution but can be negative or non-real. Its real part is the Margenau–Hill distribution.

**Metrological-advantage theorems (primary, CITING).**
- **D. R. M. Arvidsson-Shukur, N. Yunger Halpern, H. Lepage, A. Lasek, C. Barnes, S. Lloyd**, "Quantum advantage in postselected metrology," Nat. Commun. 11, 3775 (2020), arXiv:1903.02563. Their **Theorem 2** (verbatim): *"An anomalous postselected Fisher information implies that the quantum Fisher information cannot be expressed in terms of a nonnegative doubly extended Kirkwood–Dirac quasiprobability distribution"* — and the paper explicitly notes *"(The theorem's converse is not generally true.)"* Framing claim (verbatim): *"Negative quasiprobabilities enable postselected experiments to outperform optimal postselection-free experiments … This advantage, we prove, is unrealizable in any classically commuting theory."* THEOREM.
- **N. Lupu-Gladstein, Y. B. Yilmaz, D. Arvidsson-Shukur, A. Brodutch, A. Pang, A. M. Steinberg, N. Yunger Halpern**, "Negative quasiprobabilities enhance phase estimation in quantum-optics experiment," PRL 128, 220504 (2022), arXiv:2111.01194. EXPERIMENTAL. Verbatim: *"PPA [partially postselected amplification] amplifies, by over two orders of magnitude, the information obtained about the phase per detected photon"* (with the realized accuracy capped lower — an amplification factor of 78 ± 15 — due to systematic-error amplification). High confidence it occurred; moderate confidence in generality (single-group proof-of-principle).
- **M. Lostaglio**, "Certifying quantum signatures in thermodynamics and metrology via contextuality of quantum linear response," PRL 125, 230603 (2020), arXiv:2004.01213: quantum linear response is in general contextual; gives a quantum-engine example whose favorable power scaling *unavoidably* requires contextuality, plus contextual advantages for local metrology. THEOREM.
- "Saturating quantum advantages in postselected metrology with the positive Kirkwood-Dirac distribution," Phys. Rev. A 107, 042413 (2023): bounds the postselected advantage, linking it to weak-value/geometric-phase optimization.

**Incompatibility / uncertainty structure (primary, CITING).**
- **S. De Bièvre**, "Complete incompatibility, support uncertainty, and Kirkwood-Dirac nonclassicality," PRL 127, 190404 (2021): complete incompatibility of two observables ⟺ large support uncertainty of *all* states; support uncertainty is an efficient KD-nonclassicality witness. THEOREM. Extended in J. Math. Phys. 64, 022202 (2023).
- **D. Arvidsson-Shukur, J. Chevalier Drori, N. Yunger Halpern**, "Conditions tighter than noncommutation needed for nonclassicality," J. Phys. A 54, 284001 (2021): noncommutation is necessary but **not sufficient** for KD negativity. THEOREM. Corrects the folklore.

**Contextuality link — the key 2024–2025 correction (primary, CITING).**
- **D. Schmid, R. D. Baldijão, Y. Yīng, R. Wagner, J. H. Selby**, "Kirkwood-Dirac representations beyond quantum states (and their relation to noncontextuality)," arXiv:2405.04573 (v2 Aug 2025): if *any* KD representation is everywhere real and nonnegative, the experiment is consistent with generalized noncontextuality; but the **converse FAILS** — negativity/imaginarity in all KD representations does not by itself certify contextuality. THEOREM. Crucial correction to "KD negativity = contextuality."
- **J. J. Thio, W. Salmon, C. Barnes, S. De Bièvre, D. Arvidsson-Shukur**, "Verification of contextuality by noncontextual experiments," Phys. Rev. A 112, 062230 (2025): connects generalized contextuality to KD distributions; KD-positive states are exactly those whose KD distribution is a genuine joint probability.
- **C. Langrenez, W. Salmon, S. De Bièvre, J. Thio, C. Long, D. Arvidsson-Shukur**, "The set of Kirkwood-Dirac positive states is almost always minimal," arXiv:2405.17557 (2024): for generic observable pairs, KD-positive states form a minimal set — "almost no experiments have classical KD representations." Geometry: Langrenez–Arvidsson-Shukur–De Bièvre, J. Math. Phys. 65, 072201 (2024).

**Resource theory (primary, CITING).**
- **Reference of record:** Arvidsson-Shukur, Braasch Jr., De Bièvre, Dressel, Jordan, Langrenez, Lostaglio, Lundeen, Yunger Halpern, **"Properties and applications of the Kirkwood-Dirac distribution," New J. Phys. 26, 121201 (2024)**, arXiv:2403.18899.
- Lostaglio, Belenchia, Levy, Hernández-Gómez, Fabbri, Gherardini, "KD quasiprobability approach to the statistics of incompatible observables," Quantum 7, 1128 (2023).
- Y. Fan, Z. Guo, Y. Liu, H. Cao, "Resource theory of Kirkwood-Dirac imaginarity," Phys. Scr. 99, 085115 (2024): free = KD-real, resource = KD-imaginary w.r.t. a basis pair (A,B) (distinct from single-basis imaginarity).
- "Identifying quantum resources in convex resource theories with Kirkwood-Dirac quasiprobabilities," Phys. Rev. A (2025): KD distributions detect resources in *all* convex resource theories via strict negativity; negativity emerges only under measurement incompatibility.
- "Kirkwood-Dirac Nonpositivity is a Necessary Resource for Quantum Computing," arXiv:2506.08092 (2025) — MODERATE confidence pending review.

### Sub-site C — Tsallis/q-statistics and synthetic (categorical) probability

**Tsallis q-CLT (primary).**
- **S. Umarov, C. Tsallis, S. Steinberg**, "On a q-central limit theorem consistent with nonextensive statistical mechanics," Milan J. Math. 76 (2008) 307–328: claimed q-Gaussians are attractors under addition + rescaling of "q-independent" (strongly correlated) variables, proved via a q-Fourier transform. CLAIMED THEOREM.
- **H. J. Hilhorst**, "Note on a q-modified central limit theorem," J. Stat. Mech. (2010) P10023, arXiv:1008.4259; and "Central limit theorems for correlated variables: some critical remarks," Braz. J. Phys. 39 (2009) 371: the q-Fourier transform is **not invertible** for q>1 (an explicit invariance property produces distinct densities with the same q-FT), so the theorem "falls short of achieving its stated goal." **THEOREM** (the non-invertibility). Genuine, uncontested-in-substance refutation of the original proof strategy.
- Repair attempts: M. Jauregui & C. Tsallis (2011), "q-moments remove the degeneracy…"; S. Umarov & C. Tsallis, "The limit distribution in the q-CLT for q≥1 is unique and cannot have compact support," J. Phys. A 49, 415204 (2016), arXiv:1012.1814 — argue uniqueness is recoverable from intrinsic properties of q-independent variables, "ruling out Hilhorst's counterexamples." **Status: original proof broken (settled); a repaired restricted statement is defended by the Tsallis group and contested in scope.**

**Legitimate vs contested applications (CITING).**
- **Legitimate/mechanism-backed:** momentum distribution of cold atoms in dissipative optical lattices is a q-Gaussian — E. Lutz's 2003 analytical prediction (Phys. Rev. A 67, 051402(R)), verified by **P. Douglas, S. Bergamini, F. Renzoni**, "Tunable Tsallis distributions in dissipative optical lattices," PRL 96, 110601 (2006), verbatim: *"the momentum distribution of cold atoms in dissipative optical lattices is a Tsallis distribution … by changing the depth of the optical lattice, it is possible to change the momentum distribution from Gaussian, at deep potentials, to a power-law tail distribution at shallow optical potentials."* High confidence: a real q-Gaussian with a derived mechanism.
- **Contested/over-reaching:** broad "universality" claims (space plasma, seismicity, EEG/ECG, finance q-triplets), e.g. Pavlos et al., Physica A 395 (2014) 58 — curve-fits without derived mechanism. Low confidence as evidence *for* nonextensive mechanics.
- **Sharpest methodological critique:** D. Zanette & M. Montemurro, "A note on non-thermodynamical applications of non-extensive statistics," Phys. Lett. A 324 (2004) 383 — the formalism can be tuned to "derive" essentially any distribution, so a q-Gaussian fit is weak evidence. Also M. Nauenberg, "Critique of q-entropy for thermal statistics," Phys. Rev. E 67, 036114 (2003): q-entropy fails the zeroth law for systems with different q; rebutted by Tsallis (Phys. Rev. E 69, 038101, 2004), counter-rebutted by Nauenberg (arXiv:cond-mat/0305365). LIVE, but the thermodynamics-foundations weight favors the critics for the *universal* reading.
- Named dispute: F. Bouchet, T. Dauxois, S. Ruffo, "Controversy about the applicability of Tsallis statistics to the HMF model," Europhys. News 37 (2006) 9 — whether long-range quasi-stationary states are truly q-statistical vs ordinary Vlasov/kinetic.

**Synthetic/categorical probability (primary; Fritz school).**
- **T. Fritz**, "A synthetic approach to Markov kernels, conditional independence and theorems on sufficient statistics," Adv. Math. 370 (2020) 107239, arXiv:1908.07021: defines Markov categories; recovers conditioning/disintegration, conditional independence, a.s. equality, sufficient statistics, and the **Fisher–Neyman, Basu, and Bahadur** theorems synthetically, uniformly across discrete, measure-theoretic, and Gaussian probability. THEOREMS.
- **T. Fritz & E. F. Rischel**, "Infinite products and zero-one laws in categorical probability," Compositionality 2, 3 (2020), arXiv:1912.02769: **Kolmogorov and Hewitt–Savage zero-one laws** for Markov categories; instantiate measure-theoretically and, e.g., in the hyperspace monad on topological spaces. THEOREMS.
- **T. Fritz, T. Gonda, P. Perrone**, "De Finetti's Theorem in Categorical Probability," J. Stochastic Analysis 2 (2021) art. 6, arXiv:2105.02639: synthetic de Finetti; identifies the **Cauchy–Schwarz axiom** as the key ingredient and exhibits Markov categories where de Finetti *fails* — a genuine clarification of what de Finetti actually requires. THEOREM.
- **T. Fritz & A. Klingler**, "The d-separation criterion in categorical probability," JMLR 24(46) (2023): Pearl's d-separation soundness. THEOREM.
- **S. Moss & P. Perrone**, "A category-theoretic proof of the ergodic decomposition theorem," Ergodic Theory Dynam. Systems (2023), arXiv:2207.07353; N. Ensarguet & P. Perrone, arXiv:2310.04267. THEOREMS.
- Fritz, Gonda, Houghton-Larsen, Lorenzin, Perrone, Stein, "Dilations and information flow axioms in categorical probability," Math. Struct. Comp. Sci. 33 (2023) 913.

---

## Open Problems, ranked by single-GPU / Colab tractability

**Rank 1 — most tractable (linear algebra, small Hilbert spaces).**
- **O1.** Map KD-negativity vs postselected Fisher-information advantage over Haar-random qubit/qutrit/ququart basis pairs and states (d = 2–8, dense matrices). Chart where negativity is necessary/sufficient for advantage.
- **O2.** Empirically test "the KD-positive set is almost always minimal" (Langrenez et al. 2024): Monte-Carlo sample observable pairs in d = 3–6, measure the volume/dimension of the KD-positive set. Trivial compute.
- **O3.** Numerically probe the Gerhold–Lachs (r,s)-products: implement moment/cumulant recursions for the (r,s)-deformed Boolean product, verify associativity, and map where positivity fails. Symbolic/small-numeric.

**Rank 2 — tractable with care (simulation/statistics).**
- **O4.** Stress-test the q-CLT: generate the specific "q-independent" correlated sequences of Umarov–Tsallis–Steinberg / Moyano–Tsallis–Gell-Mann and check convergence to a q-Gaussian and uniqueness of the limit — directly probing the Hilhorst non-invertibility gap. Needs careful large-N tail statistics.
- **O5.** Reproduce a q-Gaussian fit vs a genuine mechanism: simulate Lutz-type cold-atom Langevin dynamics, confirm the q-parameter, then contrast with fitting q to a dataset from a *different* heavy-tailed mechanism (quantifying the Zanette–Montemurro over-fitting critique).

**Rank 3 — partially tractable (mostly formal; GPU marginal).**
- **O6.** Implement Markov-category string-diagram checks (d-separation soundness, semi-graphoid axioms) in FinStoch as an executable verifier; compare against a measure-theoretic Monte-Carlo check. Compute-light, engineering-heavy; build on the 2026 cubical formalization (arXiv:2606.20351).
- **O7.** Search for a *positive* multi-faced "exceptional" universal product (Gerhold–Varšo 2024) by testing Hankel-determinant positivity of candidate highest-coefficient families at low order. Feasible for low orders; the general positivity question is OPEN and NOT settleable by small compute.

---

## NULL-CASES (written before promotion)

- **O1 NULL:** If across thousands of d = 2–8 samples the metrological advantage correlates negligibly with KD negativity (advantage without negativity or vice versa), demote "negativity is *the* resource" to "one witness among several." *Inference (flagged):* the doubly-extended-KD theorem predicts a tight link, so a null here most likely signals a coding error, not new physics — this is a validation run. O1 is "promising" only if the tight relationship replicates cleanly as a mapping/teaching tool.
- **O2 NULL:** If the KD-positive set has substantial volume for generic pairs (not minimal), the Langrenez et al. genericity claim is contradicted — kill the "almost no classical experiments" framing.
- **O3 NULL:** If the (r,s) recursion fails associativity, the implementation is wrong; if it satisfies associativity *and* positivity everywhere, that contradicts Gerhold–Lachs (they are non-positive in general) — again a bug signal. Informative only as a positivity-boundary mapper; if positivity holds everywhere, the idea is dead.
- **O4 NULL:** If the sequences converge cleanly to a *unique* q-Gaussian with the predicted q, that empirically rehabilitates the q-CLT despite Hilhorst → promising. If the limit depends on construction details / is non-unique / is not a q-Gaussian, the q-CLT stays demoted. *Prior (flagged inference):* expect messiness.
- **O5 NULL:** If a non-Tsallis heavy-tailed mechanism fits a q-Gaussian just as well (comparable q-stability) as the Lutz mechanism, that *confirms* Zanette–Montemurro and demotes q-Gaussian fits as evidence for nonextensive mechanics. This "null for Tsallis universality" is the expected, informative outcome.
- **O6 NULL:** If the finite-Markov-category verifier and the measure-theoretic Monte-Carlo check disagree on a d-separation/conditional-independence instance, the synthetic axioms are mis-encoded (bug) — no new math. Promising only as pedagogy/formal verification, not as a source of new probabilistic facts.
- **O7 NULL:** If candidate exceptional-product coefficient families fail Hankel positivity at low order, they are eliminated — a clean negative narrowing the search. If they pass at all computed orders, that is *suggestive only*; it does NOT prove positivity (the general question stays open). Do not overclaim.

---

## The 5 most load-bearing references (why each matters)

1. **Muraki, "The five independences as natural products," IDAQP 6 (2003) 337–371** — the theorem that anchors the entire "how many independences?" question; every deformation/multi-faced result is defined relative to it.
2. **Arvidsson-Shukur et al., "Quantum advantage in postselected metrology," Nat. Commun. 11, 3775 (2020)** — the theorem tying KD negativity to a quantifiable, classically-impossible metrological advantage; launched the resource program.
3. **Arvidsson-Shukur et al. (9 authors), "Properties and applications of the Kirkwood-Dirac distribution," New J. Phys. 26, 121201 (2024)** — the definitive review; the map of the whole KD sub-site.
4. **Hilhorst, "Note on a q-modified central limit theorem," J. Stat. Mech. (2010) P10023** — the clean negative that broke the q-CLT's original proof; the model of "a clean negative is a result."
5. **Fritz, "A synthetic approach to Markov kernels…," Adv. Math. 370 (2020) 107239** — the paper that made Markov categories a working framework and proved Fisher–Neyman/Basu/Bahadur synthetically.

---

## Strongest critiques, failed replications, live controversies (who disputes what)

- **q-CLT:** Hilhorst (Paris-Saclay) vs Umarov–Tsallis–Steinberg (CBPF/UNM). Hilhorst *proved* q-Fourier non-invertibility for q>1 (settled; the 2008 proof is broken as stated). Tsallis group counters (2016) that uniqueness is recoverable from intrinsic q-independence. Non-invertibility: **HIGH** confidence. "q-CLT is fine after repair": **LOW / CONTESTED**.
- **Tsallis thermodynamics foundations:** Nauenberg (UC Santa Cruz) vs Tsallis; Zanette & Montemurro showed the formalism fits anything. Universal reading not established. Grade for "nonextensive mechanics is a universal framework": **LOW**.
- **HMF applicability:** Bouchet–Dauxois–Ruffo dispute that long-range quasi-stationary states are genuinely Tsallis-statistical. **LIVE**.
- **KD ⇒ contextuality:** Schmid–Baldijão–Yīng–Wagner–Selby (2024–25) disproved the naive converse. **HIGH**.
- **Noncommutation ⇒ nonclassicality:** disproven by Arvidsson-Shukur–Chevalier Drori–Yunger Halpern (2021). **HIGH**.
- **Muraki "exactly five" as universal:** challenged by Gerhold–Lachs (drop normalization → (r,s)) and Gerhold–Hasebe–Ulrich (two-faced → uncountably many). "Five" is real but boundary-conditioned. **HIGH** (theorems).
- **Categorical probability:** no failed replications (pure math), but the fair critique is that it mostly *reproves* known theorems more cleanly and *clarifies* assumptions rather than proving classically-unprovable statements.

---

## Adjacent fringe claims to steer around (and why)

- **"Tsallis q-statistics is a universal law of complex systems"** (q-triplets in brain/markets/earthquakes/plasma). Fringe: fitting a q-Gaussian is under-constrained (Zanette–Montemurro), usually with no derived mechanism. The mechanism-backed core (cold atoms) is *not* fringe; the universality extrapolation is.
- **"q-entropy is THE unique correct generalization of Boltzmann–Gibbs / resolves black-hole & cosmological entropy."** Over-reach: many inequivalent generalized entropies exist (Rényi, Landsberg, superstatistics); uniqueness/necessity is disputed (Nauenberg zeroth-law failure).
- **"Anomalous/negative weak values are, by themselves, proof of contextuality/advantage"** (unqualified). Fringe-adjacent: Schmid et al. (2024) and Kunjwal–Lostaglio–Pusey show the inference is subtler (nonnegativity ⇒ noncontextuality, not the converse; Pusey 2014 requires careful operational framing).
- **"KD negativity = quantum advantage"** as a blanket slogan. Uncritical: negativity is necessary for *specific* postselected-metrology/computation advantages, is basis-dependent, and is not a universal certificate.
- **"Category theory reveals probability theorems impossible to state classically."** Overclaim: Markov categories re-derive and unify known theorems and clarify assumptions across models; to date they have produced no probabilistic theorem about *classical* probability that was previously inexpressible. The payoff is uniformity and new proofs.
- **"Quantum/deformed probability proves the universe is [X]"** metaphysics from the independence-classification results. The math is about algebraic axioms, not ontology.

---

## Direct answers to the three framing questions

**Q1 (Muraki).** "Exactly five" is a THEOREM, scope-limited to single-faced universal products satisfying positivity + normalization + associativity + (dropping only) symmetry. Relaxing axioms *does* yield more: Gerhold–Lachs two-parameter (r,s)-deformation without normalization; uncountably many in the two-faced setting (Gerhold–Hasebe–Ulrich 2023, verbatim "infinite (and even uncountable)"). Hasebe's indented/cyclic and BMT/bigraph constructions unify or mix the five *without* violating Muraki's axioms. Honest answer: five is a genuine but conditional classification, not a law of nature.

**Q2 (KD).** KD negativity is at THEOREM level a *necessary* resource for postselected metrological advantage (2020, Theorem 2; converse explicitly not generally true), experimentally demonstrated (2022), and necessary for detecting resources in all convex resource theories (2025). Its link to generalized contextuality is *asymmetric* and was corrected in 2024–25 (nonnegativity ⇒ noncontextuality; converse false). Resource theories of KD nonclassicality/imaginarity exist (2024). Healthiest, most experimentally grounded site.

**Q3 (Tsallis + categorical).** The q-CLT's original proof is broken (Hilhorst, settled); a repaired restricted version is defended but contested; q-Gaussians are legitimate as mechanism-backed fits (cold atoms) and over-used as universal fits (contested). Categorical probability has produced real theorems (de Finetti, zero-one, d-separation, ergodic decomposition, sufficient statistics), but the honest answer to "has it proven something classically inexpressible?" is essentially **NO** (clean negative): its value is uniform cross-model proofs and pinpointing hidden assumptions, not new classical facts.

---

## Caveats (confidence & epistemic hygiene)

- All classification and quasiprobability results marked THEOREM are published/peer-reviewed — **high confidence** in mathematical content.
- The KD metrology experiment (Lupu-Gladstein 2022) is a **single-group proof-of-principle**: high confidence it happened, moderate confidence in generality. The realized amplification (78 ± 15 in accuracy) is below the >2-orders-of-magnitude information-per-photon figure due to systematic-error amplification — do not conflate the two numbers.
- The 2025–2026 KD-computing/moment papers (arXiv:2506.08092, 2506.08107) and the temporal-KD / "natural conditional expectations" preprints are recent — graded **MODERATE** pending citation/review.
- **Inferences flagged as such:** the O1 and O4 "prior expectations" are my inference, not cited fact; the null-case reasoning about bugs-vs-physics is analysis, not citation.
- **Reference existence honesty:** every citation above is to a paper I located in this pass. The one identifier I could **not** confirm is an arXiv number for Gerhold–Lachs 2015 — cite by DOI 10.1142/S0219025715500046. The Gerhold–Lachs deformation is **two-parameter (r,s)**, not the "one-parameter" sometimes loosely stated. The combinatorial multi-faced paper (arXiv:2301.01816) is **Gerhold–Varšo**; the representation-theoretic one (arXiv:2111.07649) is **Gerhold–Hasebe–Ulrich** — distinct papers, distinct author lists.
- No fabricated citations. Where a claim's honest status is "open" (positivity of exceptional multi-faced products; whether a repaired q-CLT holds) or "no" (categorical probability proving classically-inexpressible facts), that is stated plainly as a result, not a gap.