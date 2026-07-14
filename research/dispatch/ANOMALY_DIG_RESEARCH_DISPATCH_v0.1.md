# ANOMALY DIG — RESEARCH DISPATCH · R01–R12

OMPU / "Digging Where It Glows" (DIG-000). Диспетчер Research-стадии.
Одна карточка = один Research-проход в отдельном окне. Промпты — payload (EN), пометки курсивом — для оператора (RU).

---

## Как этим пользоваться

**Оператору (Den):** кинь этот файл в свежее окно и назови номер — `R05`. Или принеси результат сюда и назови номер — разберу. Один и тот же R# можно прогнать в двух архитектурах (Neo/Jee) вслепую → это вход для триангуляции, тогда неси оба.

**Принимающему окну:** тебе дали диспетчер. Оператор назовёт ОДИН номер (например `R05`). Выполни только его карточку: возьми `TOPIC` и `Specific questions` этого номера, наложи на них `SHARED DELIVERABLE SPEC` ниже, верни результат по этой структуре. Остальные карточки игнорируй. Промпт самодостаточен — внешнего контекста не жди.

---

## SHARED DELIVERABLE SPEC — applies to whichever R# you run

```
You are running one dig-site literature pass for an independent research
program (OMPU / "The Anomaly Dig"). The program hunts reproducible
anomalies: places where intuition trained on the finite, local, and
commutative pays a measurable price for extrapolation. You are mapping
exactly ONE site, named by the R-number given to you.

Take the TOPIC and Specific questions from that R-card and deliver:

1) State of the art 2023–2026. Primary sources first (papers/preprints,
   not blogs or secondary summaries). Dates and author names.
2) Open problems, ranked by tractability for a single-GPU / Google Colab
   experiment (what a small-compute run could actually touch).
3) Strongest critiques, failed replications, and live controversies.
   Name who disputes what.
4) The 5 most load-bearing references, one line each on WHY it matters.
5) For each experiment idea in (2): the NULL-CASE — the concrete
   observation that would kill or demote the idea. Write it before
   claiming the idea is promising.
6) Adjacent fringe claims to steer around, with the reason each is fringe.

Rules of hygiene:
- Grade every empirical claim: high / moderate / low confidence.
- Mark theorems as theorems and conjectures as conjectures, explicitly.
- Flag what you are INFERRING versus what you are CITING.
- If a question's honest answer is "open" or "no," say so plainly —
  a clean negative is a result, not a failure.
- No fabricated citations. If unsure a reference exists, say so.
```

---

## R01 · Grokking & learning phase transitions
*Wave 1. Ближе всего к OMPU. C-1 → DIG-101.*

**Glows:** способность возникает скачком после плато переобучения; спор «реальный фазовый переход vs артефакт метрики» не закрыт.

```
TOPIC: Grokking and phase transitions in neural network training.

Specific questions:
1) Mechanistic + singular-learning-theory accounts of grokking, 2024–2026:
   local learning coefficient (LLC) / RLCT dynamics via the devinterp
   toolkit — does λ move at the grokking transition? Critiques, failed
   replications.
2) Post-2023 status of the emergence-vs-mirage debate (Schaeffer et al.
   "mirage" vs Wei et al. abrupt-capability): new evidence either side;
   any percolation / phase-transition models of emergent capability in
   transformers.
3) Has anyone done finite-size scaling of a learning transition with an
   explicit critical-exponent or universality-class claim? If yes, which
   class and how robust across seeds/architectures?
```

---

## R02 · Emergence, renormalization, universality
*Wave 3. C-2 (calibration) → DIG-102.*

**Glows:** микроскопически разные системы → одинаковые критические экспоненты; RG-неподвижные точки как «тень из другой размерности».

```
TOPIC: Renormalization group, universality, and sharp thresholds
outside equilibrium physics.

Specific questions:
1) Rigorous applications of RG / universality to networks, machine
   learning, or biology (as theorems or controlled results), versus
   cases that are only metaphor. Documented critiques of the metaphors.
2) The Kahn–Kalai conjecture after the Park–Pham 2022 proof:
   consequences, sharpenings, and where the residual log factor is known
   to be tight versus removable.
3) Self-organized criticality: current status — where it is a real
   mechanism versus an artifact of power-law fitting (the
   Clauset–Shalizi–Newman critique and its aftermath).
```

---

## R03 · Entropy: leaks between scales
*Wave 1. Стержень «утечек». C-3 → DIG-103.*

**Glows:** стрела времени из обратимой микродинамики; area laws (d+1→d); кривая Пейджа; ETH и его живые нарушители (scars, MBL-спор).

```
TOPIC: Entropy across scales — thermalization, area laws, and their
controversies.

Specific questions:
1) Eigenstate thermalization hypothesis status 2024–2026: strongest
   confirmations; cleanest violations (quantum many-body scars in
   PXP/Rydberg systems); and the current state of the many-body
   localization controversy (Šuntajs / Sels–Polkovnikov doubts vs
   defenders) — is an MBL phase established or not?
2) The Page curve and replica wormholes: what is theorem-level versus
   conjecture-level, audited for a non-specialist. Which steps are
   controlled calculations and which are conjectured.
3) Area laws of entanglement entropy: which are proven (1D gapped,
   Hastings), which remain conjectural in higher dimensions; sober status
   of the entanglement-to-geometry program (Ryu–Takayanagi derivations,
   tensor networks, Van Raamsdonk).
```

---

## R04 · Landauer & thermodynamics of computation
*Wave 2. C-4 → DIG-104.*

**Glows:** бит стоит kT ln2 (измерено); равенство Джарзинского держат экспоненциально редкие траектории; точность оплачивается энтропией (TUR).

```
TOPIC: Thermodynamics of computation and fluctuation theorems.

Specific questions:
1) Complete list of experimental Landauer-limit tests including the
   quantum regime (trapped ions, superconducting): achieved precision,
   loopholes, what is measured versus assumed.
2) The thermodynamic uncertainty relation (TUR) family, 2015–2026: scope,
   quantum violations/extensions, and applications to biology (molecular
   motors, Berg–Purcell sensing limits, kinetic proofreading).
3) Thermodynamics of computation beyond bit erasure: the
   Wolpert–Kolchinsky program (semantic information, cost of prediction) —
   sober assessment of what is established versus speculative.
```

---

## R05 · The moving floor: oscillators & synchronization
*Wave 1. Быстрый красивый результат + линза L8. C-5 → DIG-105.*

**Glows:** N осцилляторов втайне живут на 3-мерной орбите группы Мёбиуса (Watanabe–Strogatz); химеры; синхронизация именно через подвижное основание.

```
TOPIC: Synchronization, hidden low-dimensional structure, and chimera
states in coupled-oscillator systems.

Specific questions:
1) Watanabe–Strogatz and Ott–Antonsen reductions: modern extensions and
   the exact conditions under which the low-dimensional (Möbius-group /
   OA-manifold) description is exact — and what breaks it (heterogeneity,
   noise, finite N).
2) Chimera states beyond simulation: experimental realizations
   (mechanical, chemical, optical, neural) and their measured lifetimes;
   at finite N are chimeras transient, and on what timescale?
3) Any rigorous program treating vacuum / zero-point fluctuations as a
   universal synchronization substrate? (Expected answer: no or fringe —
   confirm, and cite what actually exists, e.g. Casimir-driven or
   optomechanical synchronization.)
```

---

## R06 · Relational ontology: time & space as operators
*Wave 3. Research-heavy, Colab-light. C-6 → DIG-106.*

**Glows:** (алгебра, состояние) канонически рождает поток времени (Tomita–Takesaki / thermal time); время как запутанность с часами (Page–Wootters); weak values вне спектра.

```
TOPIC: Emergent / relational time and the operator view of spacetime.

Specific questions:
1) The Page–Wootters mechanism (time from entanglement with a clock),
   2015–2026: developments, the Kuchař objections and their claimed
   resolutions, experimental illustrations beyond Moreva et al. 2014.
2) The Connes–Rovelli thermal time hypothesis (modular flow of a state as
   physical time): current status, proposed tests, and critiques.
3) Kirkwood–Dirac quasiprobabilities and weak values, 2021–2026:
   negativity as an operational metrological resource, and its links to
   contextuality — main theorems and demonstrated advantages.
```

---

## R07 · Deformations of probability
*Wave 2. Кандидат в лонгрид «периодическая таблица деформаций». C-7 → DIG-107.*

**Glows:** оси деформации классифицированы (коммутативность/независимость/аддитивность/знак/масштаб); метрика жёстко единственна (Ченцов).

```
TOPIC: The space of deformations of probability theory.

Specific questions:
1) Muraki's classification of natural notions of independence (tensor,
   free, Boolean, monotone, anti-monotone): the exact axioms, the scope
   of the "exactly five" result, and any later refinements or challenges.
2) Kirkwood–Dirac negativity 2021–2026: theorems on metrological
   advantage and links to contextuality (overlap with R06 Q3 is fine —
   go deeper on the resource-theory side here).
3) Tsallis / q-statistics: where it is legitimately applicable versus
   contested; the status of q-CLT and the main criticisms of claimed
   universality. Also: has synthetic/categorical probability (Markov
   categories, Fritz et al.) proven anything the classical language could
   not even state?
```

---

## R08 · Orthogonality & the pixel
*Wave 3. C-8 → DIG-108.*

**Glows:** Gleason выводит вероятность из ортогональности (d≥3), но d=2 выпадает; MUB в d=6 открыто; SIC ↔ единицы Штарка ↔ 12-я проблема Гильберта.

```
TOPIC: Orthogonality as the source of probability, and open finite-
dimensional structure in quantum measurement.

Specific questions:
1) Mutually unbiased bases in dimension 6: computational and theoretical
   status 2024–2026 — is more than 3 known to be impossible, or still
   open? Connection to the classification of complex Hadamard matrices.
2) SIC-POVMs and the Appleby–Flammia–Kopp program linking SIC existence
   to Stark units / Hilbert's 12th problem: which dimensions are proven,
   and what is the current state of the number-theoretic conjecture?
3) Gleason's theorem in dimension 2: what exactly fails, what replaces it
   (Busch's POVM version, Gleason-type theorems), and is there any
   meaningful notion of "2-dimensional probability" that survives?
```

---

## R09 · Primes as a spectrum
*Wave 2. C-9 → DIG-109.*

**Glows:** нули дзеты коррелируют как собственные значения случайных матриц GUE; модель Крамера тонко врёт в коротких интервалах; смещение Чебышёва.

```
TOPIC: Random-matrix statistics of the Riemann zeros and the random
model of the primes.

Specific questions:
1) Beyond the GUE pair-correlation of zeta zeros: known lower-order
   correction terms (Keating–Snaith moment conjectures, Bogomolny–Keating),
   and the latest large-height zero computations testing them.
2) Failures of the Cramér random model of primes: the Maier phenomenon in
   short intervals, and recent refined probabilistic models — which model
   fixes which discrepancy.
3) Chebyshev's bias (excess of primes ≡ 3 mod 4): sharpest unconditional
   results, the role of GRH + linear independence of zeros, and
   generalizations to other moduli and L-functions.
```

---

## R10 · Incompressibility & the borders of proof
*Wave 3. C-10 → DIG-110.*

**Glows:** BB(6) — заложник Коллатц-подобных «криптид»; BB(745) независим от ZFC; таблицы Лейвера гарантированы кардиналом I3; Chaitin Ω.

```
TOPIC: Busy Beaver frontier, incompressibility, and finite objects with
transfinite guarantees.

Specific questions:
1) The Busy Beaver function frontier 2024–2026: the confirmed BB(5) =
   47,176,870 result and the state of BB(6), including the "antihydra"
   and other cryptids whose halting is tied to open Collatz-like problems.
2) Laver tables: computational records on the period-growth of the first
   row, and whether any ZFC-only (large-cardinal-free) progress exists on
   the growth that is otherwise proven only from a rank-into-rank (I3)
   cardinal. State the exact known bound.
3) Randomness hierarchies (Schnorr randomness vs computable randomness vs
   Martin-Löf randomness): the cleanest known separations and what
   philosophical stake distinguishes them.
```

---

## R11 · Coincidences as tunnels
*Wave 3. C-11 → DIG-111.*

**Glows:** moonshine (Monster, umbral, O'Nan) конвертирует «совпадения» в теоремы; размерности 8/24; экзотические ℝ⁴. Плюс дисциплина: кладбище нумерологий как контрольная группа.

```
TOPIC: Deep numerical coincidences that resolved into structure — and
the ones that did not.

Specific questions:
1) The moonshine landscape 2015–2026: umbral moonshine (proved,
   Duncan–Griffin–Ono), O'Nan moonshine, pariah groups — what is now
   theorem and what remains coincidence-status conjecture.
2) Sphere packing after Viazovska (dims 8 and 24): progress toward other
   dimensions, the scope of the universal-optimality result
   (Cohn–Kumar–Miller–Radchenko–Viazovska), and the known limitations of
   linear-programming bounds.
3) Does anyone maintain a systematic catalogue distinguishing numerical
   coincidences that resolved into structure from those that were
   debunked (fine-structure 137, Titius–Bode)? If not, what would the
   selection criterion be for calling an echo "load-bearing"?
```

---

## R12 · Home specimen: knowledge graph as percolating medium
*Wave 1. Проверка новизны для главной ставки OMPU. C-OMPU → DIG-120.*

**Glows:** живой граф знаний, навигируемый двумя полями — репульсоры на классах прошлых отказов (scars) и проводимость на находках; рост графа = finite-size scaling во времени. *Тут задача не «обзор поля», а prior-art probe: искали ли это уже.*

```
TOPIC: Navigating a growing knowledge / concept graph as a percolating
medium, with repulsive potentials on failure-classes and attractive
conductance on findings.

Specific questions:
1) Prior art probe: has anyone modeled navigation or retrieval over a
   knowledge graph / semantic network as a PERCOLATION problem with an
   explicit phase transition in an edge-weight threshold — and used that
   threshold to gate exploration-vs-exploitation regimes? Cite the
   closest existing work (network science, RAG/GraphRAG, memory-augmented
   agents, spreading-activation retrieval) and state how close it is.
2) Two-field navigation: any precedent for treating repeatable FAILURE
   classes as explicit repulsor potentials (as opposed to merely
   low-attraction / negative examples) in graph search or agent memory —
   distinct from standard negative sampling or blocklists?
3) Physics naming overlap: the term "scar" is used in quantum many-body
   physics for pinned non-thermalizing states. Is there any existing
   bridge, even metaphorical, between many-body-scar phenomenology and
   memory/retrieval systems that we should cite or explicitly distinguish
   ourselves from?
Note: for this card, a thorough "no prior art found" is a valuable
result — it directly feeds the novelty checklist. Do not manufacture
matches; report genuine closeness honestly.
```

---

## Suggested order (soft — ты выбираешь номер)

**Wave 1:** R01 · R03 · R05 · R12.
**Wave 2:** R04 · R07 · R09.
**Wave 3:** R02 · R06 · R08 · R10 · R11.

*Мотив Wave 1: R01 — живой фронт и ближе всего к рою; R05 — быстрый дофамин и Мёбиус; R03 — стержень утечек; R12 — своя ставка, проверка новизны.*

## Crosswalk R → workstream → notebook → node

| R# | Dig site | Colab | DIG node | Wave |
|----|----------|-------|----------|------|
| R01 | Grokking / learning transitions | C-1 | DIG-101 | 1 |
| R02 | Emergence / RG / universality | C-2 | DIG-102 | 3 |
| R03 | Entropy leaks between scales | C-3 | DIG-103 | 1 |
| R04 | Landauer / thermo of computation | C-4 | DIG-104 | 2 |
| R05 | Moving floor / synchronization | C-5 | DIG-105 | 1 |
| R06 | Relational time / operators | C-6 | DIG-106 | 3 |
| R07 | Deformations of probability | C-7 | DIG-107 | 2 |
| R08 | Orthogonality / the pixel | C-8 | DIG-108 | 3 |
| R09 | Primes as a spectrum | C-9 | DIG-109 | 2 |
| R10 | Incompressibility / borders of proof | C-10 | DIG-110 | 3 |
| R11 | Coincidences as tunnels | C-11 | DIG-111 | 3 |
| R12 | Home specimen: graph percolation | C-OMPU | DIG-120 | 1 |

## Когда несёшь результат сюда

Назови номер (`R05 готов, вот выдача`) и вставь. Что делаю дальше: вскрываю → `MATH_WSn` (скелет теорем, гипотезы отдельно от заключений) → отмечаю [verify]-места закрытыми/открытыми → если что-то свернулось короче источника, [M]-блок уходит в #signal-in-for-all сам → узел DIG-1xx получает форму. Два прогона одного R# из разных моделей = вход триангуляции, обрабатываю как слепую сходимость.

---
*Диспетчер v0.1. Номера стабильны — на них ссылаются узлы графа. Правка в тот же день по первой просьбе.*
