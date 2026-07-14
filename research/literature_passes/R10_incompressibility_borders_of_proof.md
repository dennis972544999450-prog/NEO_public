# R10 · Incompressibility & the Borders of Proof — Dig-Site Literature Pass

## TL;DR
- **BB(5) = 47,176,870 is now a Coq/Rocq-verified theorem (bbchallenge, 2 July 2024); BB(6) is effectively out of reach** because it is gated by "Antihydra" and roughly a dozen other Collatz-like "cryptids," and the ZFC-independence frontier has collapsed from BB(745) (Riebel, 2023) to **BB(432)** (A. J. Wade, 19 Aug 2025), with a 372-state machine now independent of PA (Feb 2026).
- **The Laver-table first-row period p(n) is proven to diverge only from a rank-into-rank (I3) large cardinal; no ZFC-only proof exists** and, by a Dougherty–Jech result, no such proof exists even in primitive recursive arithmetic. A Nov 2025 preprint (Renrui Qi) pushed the *conditional* lower bound past ε₀ (PA-unprovable growth) — but it remains an I3-conditional theorem, not ZFC progress.
- **The hierarchy Martin-Löf ⊊ computable ⊊ Schnorr ⊊ Kurtz is a theorem with clean separations**; the philosophical stake is how "effective" a statistical test may be (c.e.-bounded vs. total-computable measure), and Chaitin's Ω is the canonical "ML-random-but-no-more" object.

---

## 1. State of the Art 2023–2026 (primary sources first)

### 1A. Busy Beaver frontier

**BB(5) = 47,176,870 — THEOREM (high confidence).** In July 2024 the bbchallenge collaboration announced and formally verified in Coq (Rocq) that S(5) = 47,176,870. The formalization "Coq-BB5" was authored principally by contributor **mxdys**, building on 10+ contributors; the announcement is dated **2 July 2024** (discuss.bbchallenge.org). The unique shift champion (in TNF) is `1RB1LC_1RC1RB_1RD0LE_1LA1LD_1RZ0LA`, running 47,176,870 steps; Σ(5) = 4098. The full write-up is the arXiv preprint **"Determination of the fifth Busy Beaver value"** (arXiv:2509.12337, the bbchallenge Collaboration, 15 Sept 2025). The proof enumerates 181,385,789 TMs in TNF; it depends on one axiom (functional extensionality). A key sub-result: the machine "Skelet #17" required a standalone ~7,000-line Coq proof (Chris Xu, arXiv:2407.02426). CITING.
- I FLAG: The Coq proof and the arXiv write-up are legitimate primary sources; the arXiv paper had not (to my knowledge) completed traditional peer review — the community treats the Coq artifact itself as the object of trust.

**BB(2,4) = S(2,4) = 3,932,964 — THEOREM (high confidence).** Proven by mxdys using a subset of the BB(5) deciders (Coq file BB24Theorem.v); reported by Shawn Ligocki, 27 Aug 2024. Notably all deciders here are "regular" (CTL with regular expressions) — making BB(5) the unique known domain with irregular machines but no cryptids. CITING.

**BB(6) — OPEN and believed "Hard" (high confidence it is Collatz-gated).** In June 2024 mxdys discovered **Antihydra**, `1RB1RA_0LC1LE_1LD1LC_1LA0LB_1LF1RE_---0RA`, a 6-state cryptid whose halting is equivalent to a Collatz-like statement: iterate the Hydra map H(n)=⌊3n/2⌋ from n=8; the machine halts iff the count of odd values ever exceeds twice the count of even values. Reported first on Discord 28 June 2024; high-level rules by "Racheline." A biased-random-walk heuristic makes it "probviously" non-halting. CITING. On the exact halting probability, sources differ: the primary arXiv write-up (2509.12337) states the chance of Antihydra halting is "less than 10^(−200,000,000)"; secondary community summaries cite figures nearer 10^(−10^10). Either way it is a **heuristic, not a proof** — treat the specific magnitude as low-confidence and the "unproven" status as high-confidence.
- Current BB(6) champion: `1RB1RA_1RC1RZ_1LD0RF_1RA0LE_0LD1RC_1RA0RE`, discovered by mxdys June 2025, proving **S(6) > Σ(6) > 2↑↑↑5** (pentation). Per Quanta ("Busy Beaver Hunters Reach Numbers That Overwhelm Ordinary Math," 22 Aug 2025), the runtime exceeds "2↑↑↑5, or 2↑↑(2↑↑(2↑↑(2↑↑2)))"; OEIS A060843 records "a(6) > 2^^^5 >> 10^^(10^7)." Prior champions climbed through exponentiation (Pavel Kropitz, 10↑↑15) and tetration levels. CITING.
- Holdout count: per the BusyBeaverWiki BB(6) page (last edited 29 June 2026), "@mxdys's informal holdouts list has 1094 machines up to equivalence and 2320 machines not considering equivalence as of June 2026"; a partial Rocq proof for BB(6) is on GitHub. Roughly a dozen 6-state cryptids are known, plus a "Beaver Math Olympiad" problem and probviously-*halting* cryptids ("Lucy's Moonlight").
- Other minimal cryptids: **Bigfoot** (BB(3,3), `1RB2RA1LC_2LC1RB2RB_---2LA1LA`, savask/Ligocki Oct 2023, halting prob < 10^(−1,000,000)); **Hydra** (BB(2,5)).

**ZFC/PA independence frontier — THEOREM chain (high confidence the machines exist; the "smallest" is a moving upper bound).** The construction: an explicit n-state TM enumerates ZFC theorems and halts on finding 0=1; by Gödel's Second Incompleteness Theorem, ZFC (if consistent) cannot prove it runs forever, so BB(n) is independent of ZFC. Progression of the *upper bound* on the smallest such n:
- 7,910 — Yedidia & Aaronson, 2016 (arXiv:1605.04343), under a stronger consistency hypothesis (subtle cardinals / stationary Ramsey).
- 1,919 then 748 — Stefan O'Rear, 2016 (Ramsey dependency removed; machine directly enumerates ZFC).
- 745 — Johannes Riebel, bachelor's thesis, U. Augsburg, July 2023.
- 643 (July 2024) and 636 (31 Aug 2024) — Rohan Ridenour.
- 588 (12 July 2025), 549 (16 July 2025), and **432 (19 Aug 2025)** — Andrew J. Wade. Wade's 432-state champion also omits the axiom of regularity. Current proven range **6 ≤ N_ZF ≤ 432** (lower bound because BB(5) is proven; ZF and ZFC coincide by Shoenfield absoluteness).
- PA-specific: a **372-state** machine independent of PA (user LegionMammal978, 11 Feb 2026) replaces the ZF axioms with an adjunction+separation schema interpreting PA. A separate 493-state machine independent of "ZFC + arbitrarily large subtle cardinals" also exists (Feb 2026).
- I FLAG (inference): the post-745 results are self-reported via GitHub/Codeberg commits and the bbchallenge "Logical independence" wiki page; they are **not formally verified**, per the wiki's own caution. Confidence they are *correct*: moderate-high; confidence 432 is the *current record*: moderate (records move; my subagent verified 432 as of the wiki's March 2026 state).
- CONJECTURE (Aaronson, "The Busy Beaver Frontier," SIGACT News 2020): N_PA ≤ 10 and N_ZFC ≤ 20 — explicitly a conjecture, not a theorem.

**BB(15) / BB(5,4) tied to an Erdős conjecture — THEOREM (Stérin & Woods, 2021, arXiv:2107.12475; pub. Reachability Problems 2024).** Explicit 15-state (and 5-state, 4-symbol) TMs halt iff Erdős's base-3 conjecture is false (for all n > 8, 2^n has at least one digit 2 in base 3). So the knowable/unknowable BB frontier lies somewhere between BB(6) and BB(15). CITING.

### 1B. Laver tables

**Definitions/facts (THEOREM, high confidence).** The n-th Laver table A_n is the unique left-distributive operation on {1,…,2^n}. The first-row period p(n) is nondecreasing and always a power of two; the period sequence is 1,1,2,4,4,8,8,8,8,16,… (OEIS A098820). Richard Laver (1992/1995) proved, **assuming a rank-into-rank cardinal (I3)**, that p(n) → ∞. CITING.

**ZFC-only progress: OPEN / effectively NO (high confidence).** Whether p(n) → ∞ is provable in ZFC *without* the large-cardinal hypothesis remains unknown. Sharper than "unknown": per Dehornoy–Lebed, "Laver tables and combinatorics" (arXiv:1810.00548), no proof avoiding the Laver axiom has been found, and by a Dougherty–Jech result **such a proof does not exist in primitive recursive arithmetic**. Dehornoy's survey chapter ("More about the Laver Tables") states that a purely finite/combinatorial proof, if it exists, "has to be very complicated." So the honest answer to the assignment's question 2 is: **no ZFC-only (large-cardinal-free) proof of divergence is known, and any such proof is provably non-elementary.** CITING.

**Known bounds (THEOREM, conditional on I3).** Define q(n) = pseudo-inverse of p; q is total iff p diverges. First values 0,2,3,5,9; the existence of q(5) is not confirmed in ZFC alone. Under I3, **Dougherty (1993/1995) showed q^n(1) > f_{ω+1}(⌊log₃ n⌋ − 1)** (modified fast-growing hierarchy) and **q(5) > f_9(f_8(f_8(254)))**; for proving q(5) is even defined, a 4-huge cardinal suffices. Dougherty's critical-point-counting function F(n) satisfies F(4) > Ack(9, Ack(8, Ack(8, 254))) and dominates Ack(n,n). Dougherty explicitly "expressed pessimism about the complexity of proving better lower bounds," and for three decades none were found. CITING.

**New 2025 preprint (THEOREM conditional on I3; moderate confidence — unrefereed preprint).** Renrui Qi, "Notes on Laver Tables" (arXiv:2501.06733, dated 18 Nov 2025), sharpens Dougherty: it proves **F(n) dominates every computable function whose totality is provable in Peano Arithmetic** (i.e., F grows at least at the H_{ε₀} rate, hence F's totality is not PA-provable), and gives F(4) ≥ γ_{m_{ω+2}(2)} (Steinhaus–Moser, exceeding Graham's number). It introduces "Laver table yarns" and a function existing only under I2.
- I FLAG (critical, directly answering the brief): This remains an **I3-conditional** result. Qi's own paper states "no axiom system weaker than ZFC+I3 has been shown to be strong enough to prove the totality of F." It sharpens *how fast* F grows *given* the large cardinal; it does **not** remove the large-cardinal hypothesis. So it is **not** ZFC-only progress on divergence.

### 1C. Randomness hierarchies

**Hierarchy (THEOREM, high confidence).** For the uniform measure on 2^ω: **Martin-Löf random ⇒ computably random ⇒ Schnorr random ⇒ Kurtz random**, and none of the implications reverse (Rute; Downey–Hirschfeldt; Nies). CITING.

**Cleanest separations (THEOREM, high confidence).**
- *Exact degree-theoretic separation:* **Nies, Stephan & Terwijn (2005)** — for any set A, A is high ⟺ there is B ≡_T A that is computably random but not ML-random ⟺ there is C ≡_T A that is Schnorr random but not computably random. Both separations are realized exactly in the high Turing degrees (and can be taken left-c.e. when A is left-c.e. and high). CITING.
- *Compressibility separation (the philosophically pointed one):* there exist computably random sequences that are highly compressible (Bienvenu–Hölzl–Kräling–Merkle, arXiv:0907.2324; also Nies). By contrast, ML-randomness *is* incompressibility: X is ML-random ⟺ ∃c ∀n K(X↾n) > n − c (Schnorr's theorem, via Levin/Chaitin). So computable/Schnorr randomness permit initial segments of low prefix-free complexity, which ML-randomness forbids. CITING.
- *c.e. reals:* there are c.e. reals that are Schnorr random but not ML-random; unlike ML-random c.e. reals, not all Schnorr-random c.e. reals are Turing-complete, though all are high (Downey–Griffiths). CITING.

**Chaitin's Ω (THEOREM, high confidence).** Ω = halting probability of a universal prefix-free machine; it is a left-c.e. real and ML-random (Chaitin, 1975). The c.e. ML-random reals are *exactly* the Ω-numbers of universal machines (Calude–Hertling–Khoussainov–Wang; Kučera–Slaman). Ω is "ML-random but no more": difference randomness (a slight strengthening) characterizes exactly the ML-randoms that do *not* compute the halting problem, and Ω *does* compute ∅′ ("Aspects of Chaitin's Omega," arXiv:1707.08109). Calude–Solovay: for a suitable universal machine, ZFC (if arithmetically sound) can determine no more than Ω's initial block of 1-bits. CITING.

**Philosophical stake (CITING + inference).** Schnorr (1971) criticized ML-randomness because ML-tests are c.e. (the measure of the n-th test level is merely computably *bounded*), which he argued admits tests whose stochasticity "cannot be visualized." Schnorr required the test-level measures to be *total-computable* reals — a more constructive standard — yielding a strictly larger random set. The trade-off: computable/Schnorr randomness has a "natural" martingale/betting definition but poor closure (compressible randoms exist); ML-randomness has the clean incompressibility characterization but a "less natural" c.e.-test definition. Rute (arXiv:1812.03375) argues Schnorr randomness is the notion implicit in Brouwer/Bishop/Demuth constructive measure theory (Schnorr randoms = Lebesgue points of L¹-computable functions; ML randoms = differentiability points of computable bounded-variation functions).

---

## 2. Open Problems, Ranked by Tractability for Single-GPU / Colab

Ranked most → least tractable for small compute.

**(T1) BB(6) holdout deciding / accelerated simulation — MOST tractable.** ~150 BB(6) machines remain to be simulated to 1e14 steps, ~230 to 1e15; the informal holdout list is ~1,094 (up to equivalence). XnoobSpeakable solved 11 of the final holdouts by running the Ligockis' Enumerate.py at higher parameters (`--block-mult`, `--max-loops=50M`, `--max-block-size=100`). This is embarrassingly parallel and genuinely open-ended.

**(T2) Finite Laver-table computation / period search.** A_n is computable and the first-row period is a power of two. Reproducing and modestly extending the period table (A098820) and testing conjectured combinatorial identities (Drápal, Biane, Dehornoy–Lebed) is a concrete finite computation. The catch: divergence is Ackermann-scale, so you will not reach it.

**(T3) Prefix-free-machine / martingale experiments for randomness.** Constructing explicit computably-random-but-compressible sequences, or probing initial-segment complexity K(X↾n) of candidate reals, is small-compute-feasible (K is only approximable from above).

**(T4) Cryptid rediscovery / new-cryptid search in small BB domains** (BB(3,3), BB(2,5), BB(6)). Enumerate + simulate + pattern-match for Collatz-like behavior; tractable to search, hard to *prove* anything.

**(T5) Antihydra / specific-cryptid resolution — LEAST tractable (effectively impossible on any compute).** Resolving Antihydra's halting is equivalent to a Collatz-like open problem; no amount of simulation settles it.

---

## 3. Null-Cases (written BEFORE any promise claim)

**(T1) BB(6) holdout deciding.**
- NULL-CASE: After a full parameter sweep of existing deciders (FAR, MITMWFAR, Enumerate.py), you decide *zero* machines beyond the public baseline, or everything you decide is already marked in the shared spreadsheet. Kill signal: net new-decided count over baseline = 0.
- Only if you clear that null does it become promising — and XnoobSpeakable's 11/2728 shows a small positive yield is achievable, so this is **conditionally promising**.

**(T2) Laver-table periods.**
- NULL-CASE: Your computed periods merely reproduce A098820 with no new n reached (memory/time blow-up) and no conjectured identity tested beyond the literature. Kill signal: you cannot exceed the largest published n and produce no novel combinatorial check.
- Given Ackermann-scale growth, the "find divergence" framing is dead on arrival; only "test identities / extend the table modestly" survives, so this is **demoted to a replication/verification exercise** unless tied to a specific open combinatorial identity.

**(T3) Randomness/compressibility experiments.**
- NULL-CASE: Because K is not computable (only approximable from above), measured complexities are upper bounds that never *certify* incompressibility, and separations concern asymptotic/total behavior, not finite prefixes. Kill signal: your finite-prefix statistics are consistent with both hypotheses and cannot distinguish Schnorr from ML randomness.
- This makes T3 **illustrative only, not evidential** — promising as pedagogy/visualization, not as a result-generating experiment.

**(T4) New-cryptid search.**
- NULL-CASE: Your search rediscovers only known cryptids (Antihydra, Bigfoot, Hydra, the Space Needle family) or flags "chaotic" machines with no identifiable link to an open math problem (hence not classifiable as cryptids). Kill signal: no flagged machine reduces to a *named* open problem.
- Promising only if a flagged machine maps to a recognizable conjecture; otherwise it lands in the "potential cryptid" limbo the wiki already tracks.

**(T5) Antihydra.**
- NULL-CASE: trivially — any simulation halts without deciding; the problem is provably as hard as a Collatz-type statement. Dead for small compute by construction. **Not promising** as a "solve"; only viable as a heuristic-data contribution (extending the biased-random-walk statistics).

---

## 4. Strongest Critiques, Failed Replications, Live Controversies

- **"Is BB(5) really 'proved' if it's only in Coq / not peer-reviewed?"** The community answer: the Coq artifact *is* the proof; traditional peer review is secondary. The residual soft spot is reliance on the Coq kernel plus the functional-extensionality axiom (a benign, widely-used axiom). This is a philosophical/sociological dispute about what counts as a proof, not a substantive doubt. Advocates: Stérin, Woods, mxdys, Ligocki. Confidence the result is correct: high.
- **The original 7,910-state ZFC machine rests on an unpublished Harvey Friedman result** (order-invariant graphs / stationary Ramsey). O'Rear's later machines removed that dependency by directly enumerating ZFC, so the modern 748→432 machines do not share the weakness. CITING.
- **Post-745 ZFC bounds are unverified.** The bbchallenge wiki explicitly cautions that the 643/636/588/549/432 machines are self-reported and not formally verified. The headline "BB(432) independent of ZFC" is therefore moderate-confidence pending verification. Names: Ridenour (643, 636), Wade (588, 549, 432), LegionMammal978 (PA-372, subtle-cardinal-493).
- **Doubts about I3 consistency.** A minority position: per the Googology Wiki's Laver-table page, "the latter axiom is so strong that there are a few specialists who doubt the consistency of the system." Wikipedia's "rank-into-rank" entry notes the I-axioms "were at first suspected to be inconsistent... but this has not yet happened and they are now usually believed to be consistent." Since Laver's divergence proof rests on I3, this is a genuine foundational caveat — though most set theorists accept I0–I3. The deeper, philosophically loaded point: divergence of p(n) is a *finite/arithmetic* statement currently provable only from a large cardinal.
- **KL-randomness vs ML-randomness.** Whether Kolmogorov–Loveland randomness equals ML-randomness is a *fundamental open question* (Muchnik; Miller–Nies). KL is "quite close" to ML but not known to coincide. Live, decades-old.
- **Chaitin's incompleteness interpretation.** Chaitin's philosophical framing (that a theory can prove only finitely many "K(x) > c" statements) has drawn published criticism ("Revisiting"/"On Interpreting Chaitin's Incompleteness Theorem"). The mathematics is solid; the interpretation is disputed.

---

## 5. The 5 Most Load-Bearing References (one line each on WHY)

1. **The bbchallenge Collaboration, "Determination of the fifth Busy Beaver value," arXiv:2509.12337 (Sept 2025)** — the definitive primary write-up of the BB(5) theorem, the cryptid taxonomy, and the Coq methodology; anchors all of §1A.
2. **Coq-BB5 (mxdys / ccz181078 GitHub, 2024)** — the actual machine-checked proof object that makes BB(5)=47,176,870 a theorem rather than a 34-year-old conjecture; the epistemic center of gravity.
3. **Yedidia & Aaronson, "A Relatively Small Turing Machine Whose Behavior Is Independent of Set Theory," arXiv:1605.04343 (2016)** — founded the entire ZFC-independence line (7,910 → … → 432) and gave the first upper bound on the highest ZFC-provable BB value.
4. **Dougherty, "Critical points in an algebra of elementary embeddings" I & II (1993/1995)** — the standing Ackermann-scale lower bounds on Laver-table critical points under I3; the exact benchmark Qi (2025) improves, and the source of the q(5) > f_9(f_8(f_8(254))) figure.
5. **Nies, Stephan & Terwijn (2005), "Randomness, relativization and Turing degrees"** — pins the Schnorr/computable/ML separations exactly to the high degrees; the single cleanest separation theorem in the hierarchy.

(Secondary but crucial: Aaronson, "The Busy Beaver Frontier," SIGACT News 2020 — source of the N_PA ≤ 10, N_ZFC ≤ 20 conjectures; Downey & Hirschfeldt, *Algorithmic Randomness and Complexity*, 2010 — the standard reference for §1C.)

---

## 6. Adjacent Fringe Claims to Steer Around (with reasons)

- **"BB(6) has been / is about to be solved."** FRINGE. It is gated by Antihydra (Collatz-hard); no serious researcher claims imminent resolution. As Aaronson told Quanta (Brubaker, "Amateur Mathematicians Find Fifth 'Busy Beaver' Turing Machine," 2 July 2024), "It's conceivable that this is the last busy beaver number that we will ever know."
- **"Antihydra definitely never halts."** OVERCLAIM. The probabilistic argument (whether 10^(−200,000,000) or ~10^(−10^10)) is a *heuristic* ("probvious"), not a proof. Treating it as settled is fringe.
- **"BB(745) is the smallest ZFC-independent value" — or *any* fixed number as THE smallest.** STALE / WRONG framing. 745 was July 2023; the *upper bound* is now 432 (Aug 2025), and the true smallest n is unknown (conjectured ~20). These are upper bounds on a still-open minimum, not the minimum itself.
- **Laver tables "prove large cardinals exist," or divergence is "known."** FRINGE. Divergence is proven *from* I3, not the converse; there is no ZFC-only proof and (Dougherty–Jech) none in primitive recursive arithmetic. Conflating "conditional on I3" with "unconditional" is the central trap here.
- **Chaitin's Ω "encodes the answer to all mathematical problems" / is a mystical number.** FRINGE (pop-science inflation). Ω is a specific machine-dependent left-c.e. ML-random real; its "power" is exactly ∅′-completeness — nothing mystical.
- **"Busy Beaver values give you a lookup table to decide the Riemann Hypothesis / all of math."** MISLEADING. In principle BB(n) settles Π₁ statements decidable by ≤ n-state machines (Goldbach ~27 states; ZFC-consistency ~432), but BB is non-computable and independence kicks in early, so it is not an actual decision procedure.
- **The Googology-wiki "named giant functions" ecosystem** (extrapolated I0-function / loader-style growth presented as established math). Fine for orientation only; cite the underlying set-theory papers (Laver, Dougherty, Dehornoy), not the informal googology framing.

---

### Hygiene summary
- **Theorems (asserted as such):** BB(5)=47,176,870; BB(2,4)=3,932,964; existence of ZFC-independent TMs at 7,910/748/745/…/432 states; Antihydra ⇔ a Collatz-like statement; BB(15) ⇔ ¬Erdős; Laver p(n)→∞ *under I3*; Dougherty's Ack-scale bounds *under I3*; Qi's H_{ε₀} bound *under I3*; the four-level randomness hierarchy and its non-reversal; Nies–Stephan–Terwijn highness characterization; Ω is left-c.e. + ML-random; c.e. ML-randoms = universal Ω-numbers.
- **Conjectures (asserted as such):** N_PA ≤ 10, N_ZFC ≤ 20 (Aaronson); Antihydra/Bigfoot/Hydra non-halting (probabilistic).
- **Clean negatives (a result, not a failure):** No ZFC-only proof of Laver divergence exists, and none can exist in primitive recursive arithmetic. Whether KL-randomness = ML-randomness is open. The exact value of BB(6) is open and expected to remain so.
- **Inferences vs. citations:** Tractability rankings, null-cases, and the "epistemic center of gravity" judgments in §5 are my inferences; all dated results, names, bounds, and quotes are cited to the named sources above. The post-745 ZFC bounds and the June-2026 holdout counts come from the bbchallenge wiki and self-reported GitHub/Codeberg commits (verified via a targeted secondary pass), and carry the flagged moderate confidence.