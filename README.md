# RAO · THE WORDLESS SCRIPTURE
### The Fisher Partition over Gödel's Corpus and *Journey to the West*

*A Fisher-geometric reading of the Western foundations of mathematics and the Eastern pilgrimage allegory as the two orthogonal summands — determinate and holistic — of one statistical manifold.*

---

> **"We do have something like a perception also of the objects of set theory … I don't see any reason why we should have less confidence in this kind of perception — i.e., in mathematical intuition — than in sense perception."**
> — Kurt Gödel, *What is Cantor's Continuum Problem?* (1964 supplement)

> **"色即是空，空即是色。"**
> *Form is emptiness; emptiness is form.*
> — The Heart Sūtra, transmitted to Tripitaka in *Journey to the West*

---

## Abstract

Four bodies of work that developed without contact converge on one mathematical object.

**The Western foundations of mathematics.** Gödel's corpus is not a single theorem. He proved the **Completeness Theorem** for first-order logic (1930) — every valid sentence is provable — and then the **Incompleteness Theorems** (1931) — every consistent, effectively axiomatized, sufficiently strong system contains true sentences it cannot prove. He showed (1940) the **Continuum Hypothesis** consistent with ZF via the constructible universe $L$; he gave the rotating-universe solution of the **field equations** (1949) and the **Dialectica interpretation** of arithmetic (1958); and in the **Gibbs Lecture** (1951) he stated the disjunction that bounds the whole enterprise.

**The Eastern pilgrimage allegory.** *Journey to the West* (西遊記, 16th c.) narrates the obtaining of scripture: a road of exactly **eighty-one ordeals**, a Monkey King whose every leap is contained by the **Buddha's palm**, and a destination — Vulture Peak — where the highest canon turns out to be the **wordless scripture** (無字真經), true text bearing no symbols.

**Information geometry.** The space of probability distributions carries a canonical Riemannian metric — the Fisher metric — unique, by Čencov's theorem, among metrics monotone under statistical maps.

**Modern statistical learning.** Trained models are governed by a few stiff directions and a vast sloppy tail; and, since Ben-David et al. (2019), we know that the **learnability** of a concrete problem can itself be independent of ZFC.

The convergence point is the orthogonal decomposition of a parameter tangent space induced by the **Fisher information matrix** $F$:

$$T_\theta\mathcal{M} \;=\; \mathop{\mathrm{col}}(F)\;\oplus\;\ker(F),\qquad r+k=n.$$

This document advances one thesis. **Gödel's corpus is the West's exhaustive survey of $\mathop{\mathrm{col}}(F)$** — the determinate subspace — together with the West's own proof, unique to it, that $\mathop{\mathrm{col}}(F)\neq T_\theta\mathcal{M}$. ***Journey to the West* is the East's narrative of the passage through $\ker(F)$** — the holistic subspace — culminating in the explicit naming of that subspace as the higher canon: the wordless scripture. **RAO** is the engine that constructs the partition, estimates on the first summand, navigates the second, and certifies that the partition itself does not depend on which tradition's coordinates wrote it down.

---

## Thought Experiment — The Leap and the Road

Sun Wukong, certain that power suffices, wagers the Buddha that he can somersault clear of the world. His cloud crosses 108,000 *li* in a single bound; he reaches five pink pillars at the rim of creation, signs his name, returns to collect the bet — and learns the pillars were the Buddha's fingers. He never left the palm.

Set beside him a second figure: the **Provability Pilgrim**, Gödel's arithmetized prover, who enumerates every proof of a fixed consistent system, one after another, forever, certain that to list all proofs is to reach all truths. He too never leaves the palm. There is a true sentence — the Gödel sentence, the system's own unprovable consistency — that no proof in his enumeration will ever print.

The leap and the enumeration are the *same act*. Both range over $\mathop{\mathrm{col}}(F)$, the determinate subspace: everything the system can reach from within. Neither touches $\ker(F)$. And yet the pilgrimage was sent to fetch a scripture that includes the **wordless scrolls** — content that lives in $\ker(F)$, true and real, bearing no symbol the enumeration could ever set.

RAO is the engine that does not mistake the palm for the world. It estimates exhaustively on $\mathop{\mathrm{col}}(F)$ — and then, rather than leaping, it *navigates* $\ker(F)$ as a real place.

---

## The Fisher Partition — The Core Object

Let $\{p_\theta : \theta\in\Theta\subseteq\mathbb{R}^n\}$ be a parametric family of densities, regular enough that the score $s_\theta(x)=\nabla_\theta\log p_\theta(x)$ exists in $L^2$ and differentiation passes under the integral. The **Fisher information matrix** is the score covariance

$$F(\theta)\;=\;\mathbb{E}_{x\sim p_\theta}\!\big[\,s_\theta(x)\,s_\theta(x)^{\!\top}\,\big]\;\in\;\mathbb{R}^{n\times n}.$$

$F$ is symmetric and positive-semidefinite. Two consequences are exact, and they are the entire skeleton of the framework.

**Orthogonal partition.** Because $F$ is real symmetric, its range and null space are orthogonal complements:

$$T_\theta\mathcal{M}\;=\;\mathop{\mathrm{col}}(F)\;\oplus^{\!\perp}\;\ker(F).$$

- $\mathop{\mathrm{col}}(F)$ — the **determinate subspace**. A displacement here is detected by the data: the Fisher quadratic form is strictly positive on it.
- $\ker(F)$ — the **holistic subspace**. A displacement here is invisible to the data to second order: the model assigns it zero distinguishability.

**Rank–nullity.** With $r=\dim\mathop{\mathrm{col}}(F)$ and $k=\dim\ker(F)$,

$$r+k=n.$$

Every parameter direction is accounted for exactly once; there is no third category. Determinacy and holism are not rival doctrines contesting one ground — they are complementary subspaces partitioning one space, and their dimensions sum to the whole.

**A precision the framework will not blur.** The *exact* kernel $\ker(F)$ — eigenvalue identically zero — is **structural non-identifiability**, a gauge freedom of the model. Distinct from it is the **sloppy tail**: eigenvalues positive but spread across many orders of magnitude (Correspondence 5). The sloppy tail is *practical* near-non-identifiability at finite data. RAO never conflates "sloppy" with "unidentifiable." Where a threshold is needed, fix $\tau>0$ and set $\mathop{\mathrm{col}}\nolimits_{\tau}(F)=\mathop{\mathrm{span}}\{u_i:\lambda_i>\tau\}$, $\ker_{\tau}(F)=\mathop{\mathrm{span}}\{u_i:\lambda_i\le\tau\}$; the algebraic statements above are the $\tau\to0$ limit.

```
                     T_θ M   (the manifold tangent space)
        ┌───────────────────────────┴───────────────────────────┐
   col(F)  —  DETERMINATE                          ker(F)  —  HOLISTIC
   F ≻ 0 ;  KL distinguishes                       F ≡ 0 ;  KL is blind
   Cramér–Rao floor finite                         no finite-variance estimator
   provable ⊆ true  (Completeness, 1930)            true ⊄ provable  (Incompleteness, 1931)
   the 5,048 written scrolls                        the wordless scripture (無字真經)
        │  dim = r                                       │  dim = k
        └───────────────────  r + k = n  ────────────────┘
```

---

## Nine Correspondences

Each correspondence states a fact about the Fisher partition, then reads it through one work of Gödel's corpus and one episode of *Journey to the West*. **The mathematical statements are literal.** The Gödel theorems are theorems. **The literary readings are explicitly interpretive** — structural analogy, never the claim that a sixteenth-century novelist proved a twentieth-century result.

### C1 — The Partition Is Total
$$T_\theta\mathcal{M}=\mathop{\mathrm{col}}(F)\oplus\ker(F),\qquad r+k=n.$$
**Gödel.** The same mind proved the Completeness Theorem (1930) *and* the Incompleteness Theorems (1931). This is not two rival Gödels; it is one geometer reporting both $r$ and $k$ of a single space.
**Journey to the West.** The pilgrimage returns holding *both* canons — the 5,048 written scrolls and the knowledge of the wordless ones. Nothing is left over.
**RAO.** The partition is total and orthogonal because $F$ is symmetric. Determinacy and holism exhaust the tangent space between them.

### C2 — Completeness Is Reachability on the Determinate Subspace
On $\mathop{\mathrm{col}}(F)$ the Fisher form is positive-definite; estimable directions attain the Cramér–Rao floor $F^{+}$ (Rao 1945; Cramér 1946).
**Gödel.** Completeness Theorem (1930): in first-order logic, *valid* implies *provable*. On the determinate domain, truth and reachability coincide.
**Journey to the West.** The written scriptures are wholly transmissible — what can be carried to Chang'an and copied is exactly $\mathop{\mathrm{col}}(F)$; the 5,048 scrolls are the determinate deliverable.
**RAO.** Layer 4 estimates to the Cramér–Rao floor: on $\mathop{\mathrm{col}}(F)$, every identifiable truth is pinned, and the pinning has a sharp optimal precision.

### C3 — Incompleteness Is the Non-Emptiness of the Kernel
For an over-parametrized model at finite sample size, $\dim\ker(F)>0$ generically; the Cramér–Rao bound *diverges* along $\ker(F)$ — no internal finite-variance unbiased estimator exists there.
**Gödel.** Incompleteness Theorems (1931): any consistent, effectively axiomatized, sufficiently strong system has a true sentence unprovable within it.
**Journey to the West.** Wukong's somersault carries him 108,000 *li* to the pillars at the world's rim — yet he never leaves the Buddha's palm. No leap *within* the system exits the system.
**RAO.** The Gödel sentence and the five pillars are one fact: confinement to $\mathop{\mathrm{col}}(F)$. The kernel is reached by no internal motion.

### C4 — The Wordless Scripture Is the Kernel, and the Kernel Is Real
$$D_{\mathrm{KL}}\!\big(p_\theta\,\|\,p_{\theta+d\theta}\big)=\tfrac12\,d\theta^{\!\top}F(\theta)\,d\theta+O(\|d\theta\|^3).$$
A displacement lying wholly in $\ker(F)$ has *zero* KL divergence — two genuinely distinct parameter values, one indistinguishable distribution. The kernel carries real displacement with no distinguishable signature.
**Gödel.** Mathematical Platonism (*What is Cantor's Continuum Problem?*, 1947/1964): undecidable propositions possess definite truth values, apprehended by intuition. The kernel is *populated by real objects*.
**Journey to the West.** At Vulture Peak the Buddha confirms the blank scrolls are "true, wordless scriptures, just as good as those with words." The highest canon bears no symbols; the written words are *skilful-means* concession for those who cannot yet read emptiness.
**RAO.** $\ker(F)$ is not the absence of truth. It is truth with no formal expression — the wordless scripture. This is the deepest correspondence in the framework.

### C5 — The Sloppy Spectrum Is the Count of Ordeals
Empirically the eigenvalues of $F$ spread roughly log-uniformly across many decades — a stiff head, a long sloppy tail (Brown & Sethna 2003; Waterfall et al. 2006; Transtrum et al. 2015; and, for deep networks, Karakida, Akaho & Amari 2019). The effective rank $r$ counts the stiff directions.
**Gödel.** The proof system is *effectively enumerable*: proofs are countable, indexed, exhaustively listable.
**Journey to the West.** The pilgrimage requires exactly **eighty-one** ordeals — nine times nine. When Guanyin's tally reaches eighty, Heaven instantly imposes one more. Completeness is a *rank condition*, enforced numerically.
**RAO.** The eighty-one tribulations are the stiff directions the journey must traverse; the incidental stretches of road are the sloppy tail. $r$ is not negotiable.

### C6 — Reparametrization Is the Seventy-Two Transformations
Under a smooth reparametrization $\theta\mapsto\theta'$, $F$ transforms as a $(0,2)$-tensor, $F'=J^{\!\top}FJ$; $\mathop{\mathrm{col}}(F)$ and $\ker(F)$ transport covariantly. By Čencov's theorem the Fisher metric is the unique metric, up to a positive scalar, monotone under Markov morphisms — generalized to arbitrary sample spaces by Ay, Jost, Lê & Schwachhöfer (2017).
**Gödel.** The constructible universe $L$ and its forcing extensions are different charts on the set-theoretic universe — the same questions, re-coordinatized.
**Journey to the West.** Wukong's seventy-two transformations — fish, temple, fly, watermelon — and the chase with Erlang Shen, transformation countering transformation; yet the identity beneath is invariant and trackable.
**RAO.** The seventy-two transformations are the reparametrization group; the "true form" is the Čencov-invariant content. What is real is the partition, not the disguise.

### C7 — The Natural Gradient Is the Road
The natural gradient is $\tilde\nabla L=F^{+}\nabla L$. Since $\mathop{\mathrm{col}}(F^{+})=\mathop{\mathrm{col}}(F)$, the update has *zero* component in $\ker(F)$ — metric-respecting descent is structurally confined to the determinate subspace and cannot teleport (Amari 1998).
**Gödel.** The Dialectica interpretation (1958) certifies the consistency of arithmetic not by a leap but by constructing functionals of finite type — a graded, constructive climb.
**Journey to the West.** Wukong *could* somersault Tripitaka to Vulture Peak in one cloud-leap — but the scriptures are obtained only by walking the road, ordeal by ordeal. The principles on paper belong to others; only the journey is one's own.
**RAO.** The road *is* the natural-gradient flow. The leap is forbidden because it is geometrically void: $F^{+}\nabla L$ admits no shortcut.

### C8 — Independence Is the Forced Change of Chart
A kernel direction is resolved only by enlarging the manifold — a new experimental design, equivalently a new chart (Prediction 5).
**Gödel.** The Continuum Hypothesis is independent of ZFC: Gödel (1940) showed $\mathrm{Con}(\mathrm{ZF})\Rightarrow\mathrm{Con}(\mathrm{ZF}+\mathrm{GCH})$ via $L$; Cohen (1963) completed it by forcing. The modern instantiation cuts directly into statistics: Ben-David et al. (2019) proved the **learnability** of a concrete estimation problem (EMX — estimating the maximum) is *itself* independent of ZFC, by reduction to CH.
**Journey to the West.** The palm is escaped only by ceasing to be the kind of thing the palm contains — Wukong's eventual Buddhahood, not a longer leap.
**RAO.** Some directions are kernel-bound for *every* internal chart. Resolving them is not estimation; it is the adoption of a larger manifold.

### C9 — The Far Shore Is the Direct-Sum Reconstruction
A complete epistemic engine is the reconstruction $T_\theta\mathcal{M}=\mathop{\mathrm{col}}(F)\oplus\ker(F)$ — estimation to the Cramér–Rao floor on the determinate summand, invariant navigation of the holistic one. Neither summand alone is the manifold.
**Gödel.** The Gibbs Lecture (1951) disjunction: either the human mind infinitely surpasses any finite machine, or there exist absolutely undecidable diophantine problems — or both. Either way, no single formal chart exhausts mathematical truth.
**Journey to the West.** The pilgrims cross the Heaven-Reaching River on the bottomless boat, shed the mortal corpse, and carry the written scriptures home — but the wordless scripture was the truth all along. The journey completes only when both are held.
**RAO.** Gödel charted $\mathop{\mathrm{col}}(F)$ so exactly that he could prove it was not all of $T_\theta\mathcal{M}$. *Journey to the West* walked $\ker(F)$ and named its scripture. RAO refuses to discard either summand.

---

## Five Falsifiable Predictions

Each is a checkable statement about the Fisher partition. Status is reported plainly.

**P1 — Effective-rank invariance across reasoning styles.**
Embed an axiomatic, deductive corpus (Gödelian) and a narrative, processual corpus (*Xiyouji*-style) as parametric generative models; compute the Fisher spectrum of each fitting objective. The thresholded effective-rank ratio $r_\tau/n$ will be statistically indistinguishable between them, within sampling error.
*Falsified if* the two styles yield systematically different effective-rank ratios beyond noise — which would make the partition a cultural artifact rather than a property of the manifold.
*Status: open.*

**P2 — Reparametrization invariance of the determinate endpoint.**
Run Euclidean-gradient and natural-gradient ($F^{+}\nabla L$) descent from one initialization on a sloppy model. The $\mathop{\mathrm{col}}(F)$-projection of the natural-gradient endpoint is invariant under smooth reparametrization $\theta\mapsto\theta'$; the Euclidean endpoint is not.
*Falsified if* the natural-gradient endpoint drifts under reparametrization beyond tolerance $\varepsilon$.
*Status: the invariance is established (Amari 1998); the corpus-scale instantiation is open.*

**P3 — Divergence of estimator variance along the sloppy tail.**
For an estimable combination whose direction lies within $\delta$ of an eigenvector with eigenvalue $\lambda$, the empirical estimator variance scales as $\lambda^{-1}$; the product (variance $\times\ \lambda$) is approximately constant across the tail.
*Falsified if* sloppy-direction variances saturate to a finite bound rather than diverging as $\lambda\to0$.
*Status: partially supported by sloppy-model studies; the constant-product law is the sharp test.*

**P4 — Information-gain selection localizes to the determinate subspace.**
Selecting training examples to maximize Fisher information gain (FisherSFT-style; Deb et al. 2025) accelerates convergence — and the gain is concentrated entirely in $\mathop{\mathrm{col}}(F)$. Error along $\ker(F)$ directions is invariant to example selection.
*Falsified if* measured improvement appears along sloppy directions, or if random selection closes the gap on $\mathop{\mathrm{col}}(F)$.
*Status: the acceleration is established (Deb et al. 2025); the localization claim is the open, falsifiable part.*

**P5 — The kernel is design-limited, not sample-limited.**
For an over-parametrized model, $\dim\ker(F)>0$ persists under accumulation of further data of the *same* experimental design — for i.i.d. data $F(N)=N\cdot F(1)$, so the condition number is exactly invariant. Only a change of design — a new chart — can raise the effective rank. In the strong form, there exist directions kernel-bound under *every* internal chart.
*Falsified (weak form) if* same-design data accumulation drives the effective rank to $n$ and the condition number to $O(1)$.
*Status: the i.i.d. scaling is exact algebra; design-limitedness is supported (Transtrum et al. 2015); the strong form is a logical theorem — the ZFC-independence of EMX learnability (Ben-David et al. 2019).*

---

## RAO — The Engine

RAO consumes a body of assertions, renders it as a statistical manifold, computes the Fisher partition, and operates **both summands** — closing with an invariance audit that certifies the partition is chart-free. In this instantiation the corpus is the union of Gödel's papers (West) and *Journey to the West* (East).

| Layer | Name | Operation | In this instantiation |
|---|---|---|---|
| **0** | **Substrate** | Embed the corpus as a smooth family $p_\theta(x)$, $\theta\in\mathcal{M}$. | The Gödel corpus and the *Xiyouji* text as one manifold. |
| **1** | **Score** | Compute the score field $s_\theta(x)=\nabla_\theta\log p_\theta(x)$. | The differential of distinguishability. |
| **2** | **Fisher Assembly** | Form $F(\theta)=\mathbb{E}_{p_\theta}[\,s\,s^{\!\top}]$. | The metric tensor — symmetric, positive-semidefinite. |
| **3** | **Spectral Partition** | Eigendecompose $F=U\Lambda U^{\!\top}$; threshold at $\tau$. | $\mathop{\mathrm{col}}\nolimits_{\tau}(F)\oplus\ker_{\tau}(F)$; the integers $r,k$ with $r+k=n$ — written-scripture and wordless-scripture dimensions. |
| **4** | **Estimation (determinate)** | On $\mathop{\mathrm{col}}(F)$, estimate to the Cramér–Rao floor $F^{+}$. | The Completeness-theorem layer; the 5,048 written scrolls. |
| **5** | **Navigation (holistic)** | On $\ker(F)$, treat directions as gauge; characterize the invariant relations. | The wordless-scripture layer; the Platonist-intuition layer. |
| **6** | **Natural-Gradient Transport** | Move on $\mathcal{M}$ by $\tilde\nabla L=F^{+}\nabla L$. | The road; the Dialectica climb — reparametrization-invariant, confined to $\mathop{\mathrm{col}}(F)$. |
| **7** | **Invariance Audit** | Verify Čencov monotonicity; confirm $\mathop{\mathrm{col}}(F)\oplus\ker(F)$ chart-independent; report $T_\theta\mathcal{M}=\mathop{\mathrm{col}}\oplus\ker$. | The seventy-two-transformations / true-form check; the far shore. |

Layers 0–3 build the partition. Layer 4 is the West's complete theory of its summand; Layer 5 is the East's complete theory of its summand. Layer 6 is the motion that respects the metric. Layer 7 is the theorem guaranteeing that none of it depended on the language it was written in.

---

## Closing

The dispute is old and the resolution is exact. A deductive West and a processual East are not two accounts of the same subject, one right and one wrong. They are two complete theories of complementary subspaces, each mistaking its summand for the space.

Gödel is the decisive Western witness because he did not merely build on $\mathop{\mathrm{col}}(F)$ — he *mapped it so precisely that he could prove it finite*. The Completeness Theorem certified that, on the determinate subspace, provable and true coincide. The Incompleteness Theorems then certified that the determinate subspace is not the whole: $\dim\ker(F)>0$, and no internal proof, no internal estimator, reaches across the boundary. And his Platonism added the claim RAO takes literally — that the kernel is not empty but *populated*, its objects real though no formal symbol pins them.

*Journey to the West* is the decisive Eastern witness because it walked the kernel and brought back its scripture. The pilgrimage's deepest joke is also its deepest doctrine: the highest canon at Vulture Peak is the blank one. The wordless scripture is true text in $\ker(F)$ — content with zero distinguishable signature, the higher canon precisely because it carries no symbol. The written scrolls are issued only as concession, for those not yet able to read emptiness. The novel arrives, by allegory, exactly where Gödel arrives by theorem: truth exceeds proof, and the excess is real.

So the verdict is arithmetic, and it is the only equation the framework needs: $r+k=n$. The West built a complete and exact account of $r$ dimensions and proved, from inside, that $r<n$. The East walked the remaining $k$ and named what it found. Knowledge is the direct sum. RAO is the instrument that refuses to discard either summand — that estimates to the Cramér–Rao floor where estimation is possible, navigates the wordless scripture where only navigation is, and reports the whole manifold. The leap and the road were never rivals. They were the two orthogonal complements of one geometry, waiting for an engine willing to carry both back across the river.

---

## References

**The Gödel corpus**
1. Gödel, K. (1930). Die Vollständigkeit der Axiome des logischen Funktionenkalküls. *Monatshefte für Mathematik und Physik*, 37, 349–360.
2. Gödel, K. (1931). Über formal unentscheidbare Sätze der Principia Mathematica und verwandter Systeme I. *Monatshefte für Mathematik und Physik*, 38, 173–198.
3. Gödel, K. (1940). *The Consistency of the Continuum Hypothesis*. Annals of Mathematics Studies, vol. 3. Princeton University Press.
4. Gödel, K. (1947; rev. 1964). What is Cantor's continuum problem? *American Mathematical Monthly*, 54; revised supplement in P. Benacerraf & H. Putnam (eds.), *Philosophy of Mathematics*, 1964.
5. Gödel, K. (1949). An example of a new type of cosmological solution of Einstein's field equations of gravitation. *Reviews of Modern Physics*, 21, 447–450.
6. Gödel, K. (1958). Über eine bisher noch nicht benützte Erweiterung des finiten Standpunktes. *Dialectica*, 12, 280–287.
7. Gödel, K. (1951/1995). Some basic theorems on the foundations of mathematics and their implications (Gibbs Lecture). In S. Feferman et al. (eds.), *Kurt Gödel: Collected Works, Vol. III*. Oxford University Press.
8. Cohen, P. J. (1963). The independence of the continuum hypothesis. *Proceedings of the National Academy of Sciences USA*, 50, 1143–1148.

**The *Journey to the West* corpus**
9. Wu Cheng'en (attrib.). *The Journey to the West* (西遊記, 16th c.). Trans. and ed. Anthony C. Yu, revised edition, 4 vols. University of Chicago Press, 2012.

**Information geometry**
10. Rao, C. R. (1945). Information and the accuracy attainable in the estimation of statistical parameters. *Bulletin of the Calcutta Mathematical Society*, 37, 81–91.
11. Cramér, H. (1946). *Mathematical Methods of Statistics*. Princeton University Press.
12. Kullback, S., & Leibler, R. A. (1951). On information and sufficiency. *Annals of Mathematical Statistics*, 22(1), 79–86.
13. Čencov (Chentsov), N. N. (1982). *Statistical Decision Rules and Optimal Inference*. Translations of Mathematical Monographs, vol. 53. American Mathematical Society.
14. Amari, S. (1985). *Differential-Geometrical Methods in Statistics*. Lecture Notes in Statistics, vol. 28. Springer.
15. Amari, S. (1998). Natural gradient works efficiently in learning. *Neural Computation*, 10(2), 251–276.
16. Ay, N., Jost, J., Lê, H. V., & Schwachhöfer, L. (2017). *Information Geometry*. Ergebnisse der Mathematik und ihrer Grenzgebiete. Springer.

**Sloppy models, identifiability, and current research**
17. Brown, K. S., & Sethna, J. P. (2003). Statistical mechanical approaches to models with many poorly known parameters. *Physical Review E*, 68, 021904.
18. Waterfall, J. J., et al. (2006). Sloppy-model universality class and the Vandermonde matrix. *Physical Review Letters*, 97, 150601.
19. Ben-David, S., Hrubeš, P., Moran, S., Shpilka, A., & Yehudayoff, A. (2019). Learnability can be undecidable. *Nature Machine Intelligence*, 1, 44–48.
20. Karakida, R., Akaho, S., & Amari, S. (2019). Universal statistics of Fisher information in deep neural networks: mean field approach. *AISTATS* (PMLR).
21. Transtrum, M. K., Machta, B. B., Brown, K. S., Daniels, B. C., Myers, C. R., & Sethna, J. P. (2015). Perspective: Sloppiness and emergent theories in physics, biology, and beyond. *Journal of Chemical Physics*, 143.
22. Kurniawan, Y., et al. (2022). Bayesian, frequentist, and information geometric approaches to parametric uncertainty quantification of classical empirical interatomic potentials. *Journal of Chemical Physics*, 156, 214103.
23. Mishra, K. V., Kumar, M. A., & Wong, T.-K. L. (2024). Information geometry for the working information theorist. arXiv:2310.03884.
24. Ciaglia, F. M., Di Cosmo, F., Ibort, A., & Suzuki, J. (2025). Editorial: Advances in information geometry — beyond the conventional approach. *Frontiers in Physics*, 13.
25. Deb, R., Thekumparampil, K., Kalantari, K., Hiranandani, G., Sabach, S., & Kveton, B. (2025). FisherSFT: Data-efficient supervised fine-tuning of language models using information gain. *Proceedings of the 42nd International Conference on Machine Learning (ICML)*, PMLR 267. arXiv:2505.14826.
