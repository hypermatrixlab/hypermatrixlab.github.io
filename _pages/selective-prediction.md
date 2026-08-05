---
layout: page
permalink: /selective-prediction/
title: Uncertainty-Guarded Selective Prediction for Large Language Models
nav: false
nav_order: 4
---

<div class="thesis-papers" markdown="0">

<nav class="tp-toc">
  <a href="#scope">SCOPE <span>ICML 2026</span></a>
  <a href="#sage">SAGE <span>ACL 2026</span></a>
  <a href="#clev">CLEV <span>IJCNLP-AACL 2025</span></a>
  <a href="#rgv">Reference-Guided Verdict <span>WiNLP 2025</span></a>
  <a href="#jra">Judge, Retrieve, or Abstain <span>In progress</span></a>
</nav>

<!-- ===================== SCOPE ===================== -->
<article class="tp-paper" id="scope">
  <div class="tp-meta">
    <span class="tp-venue">ICML 2026</span>
    <span class="tp-year">2026</span>
  </div>
  <h2 class="tp-title">SCOPE: Selective Conformal Optimized Pairwise LLM Judging</h2>
  <p class="tp-authors">Sher Badshah, Ali Emami, Hassan Sajjad</p>
  <p class="tp-links">
    <a href="https://doi.org/10.48550/arXiv.2602.13110">arXiv</a>
  </p>

  <h3 class="tp-h">Abstract</h3>
  <p class="tp-abstract">
    Large language models (LLMs) are increasingly used as scalable judges in pairwise
    evaluation, but they remain prone to miscalibration and biases. We propose SCOPE
    (Selective Conformal Optimized Pairwise Evaluation), a framework that calibrates an
    acceptance threshold so that, under exchangeability, the error rate among non-abstained
    judgments is at most a user-specified level&nbsp;&alpha;. To supply SCOPE with a
    bias-neutral uncertainty signal, we introduce Bidirectional Preference Entropy (BPE),
    which queries the judge under both response positions and converts the order-averaged
    preference probability into an entropy-based score. Across various pairwise judging
    benchmarks, BPE outperforms standard confidence proxies in calibration and
    discrimination, while SCOPE consistently satisfies the target risk bound (empirical FDR
    &asymp; 0.097&ndash;0.099 at &alpha;&nbsp;=&nbsp;0.10) and retains substantial coverage.
    Compared to vanilla baselines, SCOPE accepts up to 2.4&times; more judgments under the
    same risk constraint, demonstrating that BPE enables reliable and high-coverage
    LLM-based evaluation.
  </p>

  <figure class="tp-figure">
    <a href="{{ '/assets/img/thesis/scope_method.png' | relative_url }}" title="Open the full-resolution figure">
      <img src="{{ '/assets/img/thesis/scope_method.png' | relative_url }}"
            alt="SCOPE method: pairwise judging, bidirectional preference entropy, and conformal calibration of an acceptance threshold." loading="lazy">
    </a>
    <figcaption>
      A judge produces a pairwise verdict; Bidirectional Preference Entropy scores its
      uncertainty by querying both response orders; conformal calibration then fixes the
      largest acceptance threshold whose risk on accepted judgments stays at or below
      &alpha;.
    </figcaption>
  </figure>
</article>

<!-- ===================== SAGE ===================== -->
<article class="tp-paper" id="sage">
  <div class="tp-meta">
    <span class="tp-venue">ACL 2026</span>
    <span class="tp-year">2026</span>
  </div>
  <h2 class="tp-title">SAGE: A Search-AuGmented Evaluation of Large Language Models on Free-Form QA</h2>
  <p class="tp-authors">Sher Badshah, Ali Emami, Hassan Sajjad</p>
    <p class="tp-links">
    <a href="https://aclanthology.org/2026.acl-long.66/">ACL Anthology</a>
  </p>

  <h3 class="tp-h">Abstract</h3>
  <p class="tp-abstract">
    As Large Language Models (LLMs) become increasingly used for question-answering (QA),
    relying on static, pre-annotated references for evaluation poses significant challenges
    in cost, scalability, and completeness. Meanwhile, using LLMs themselves as evaluators
    without external grounding remains unreliable for objective tasks, as they systematically
    over-accept incorrect answers, fabricate supporting rationales, and degrade sharply on
    questions that fall outside their training data. We propose Search-AuGmented Evaluation
    (SAGE), a framework to assess LLM outputs without fixed ground-truth answers. Unlike
    conventional metrics that compare to static references or depend solely on
    LLM-as-a-judge knowledge, SAGE acts as an agent that actively retrieves and synthesizes
    external evidence. It iteratively generates web queries, collects information,
    summarizes findings, and refines subsequent searches through reflection. By reducing
    dependence on static reference-driven evaluation protocols, SAGE offers a scalable and
    adaptive alternative for evaluating the factuality of LLMs. Experimental results on
    multiple free-form QA benchmarks show that SAGE achieves substantial to perfect
    agreement with human evaluations.
  </p>

  <figure class="tp-figure">
    <a href="{{ '/assets/img/thesis/sage_method.png' | relative_url }}" title="Open the full-resolution figure">
      <img src="{{ '/assets/img/thesis/sage_method.png' | relative_url }}"
            alt="SAGE method: initial query, web search, evidence summarization, reflection, query refinement, and a final grounded verdict." loading="lazy">
    </a>
    <figcaption>
      SAGE turns the question into an initial query, searches the web, summarizes the
      retrieved evidence, and reflects on whether it is sufficient. If not, it refines the
      query and searches again. After N iterations the judge synthesizes the evidence into a
      decision with a rationale.
    </figcaption>
  </figure>
</article>

<!-- ===================== CLEV ===================== -->
<article class="tp-paper" id="clev">
  <div class="tp-meta">
    <span class="tp-venue">IJCNLP-AACL 2025 (Findings)</span>
    <span class="tp-year">2025</span>
  </div>
  <h2 class="tp-title">CLEV: LLM-Based Evaluation Through Lightweight Efficient Voting for Free-Form Question-Answering</h2>
  <p class="tp-authors">Sher Badshah, Moamen Moustafa, Hassan Sajjad</p>
  <p class="tp-links">
    <a href="https://aclanthology.org/2025.findings-ijcnlp.93/">ACL Anthology</a>
  </p>

  <h3 class="tp-h">Abstract</h3>
  <p class="tp-abstract">
    Evaluating free-form Question-Answering (QA) remains a challenge due to its diverse and
    open-ended nature. Traditional automatic metrics fail to capture semantic equivalence or
    accommodate the variability of open-ended responses. Leveraging Large Language Models
    (LLMs) as evaluators offers a promising alternative due to their strong language
    understanding and instruction-following capabilities. We propose the Consensus via
    Lightweight Efficient Voting (CLEV), which employs two primary LLMs as judges and engages
    a third judge only in cases of disagreement. This approach prioritizes evaluation
    reliability while reducing unnecessary computational demands. Through experiments,
    including human evaluation, we demonstrate CLEV's ability to provide consistent,
    scalable, and resource-efficient assessments, establishing it as a robust framework for
    evaluating LLMs on free-form QA.
  </p>

  <figure class="tp-figure">
    <a href="{{ '/assets/img/thesis/clev_method.png' | relative_url }}" title="Open the full-resolution figure">
      <img src="{{ '/assets/img/thesis/clev_method.png' | relative_url }}"
            alt="CLEV method: two primary judges evaluate an instance; a third judge is invoked only when they disagree." loading="lazy">
    </a>
    <figcaption>
      CLEV: Consensus via Lightweight Efficient Voting. Two primary judges evaluate each
      instance from the question, candidate output, and reference answer. Agreement settles
      the verdict; only on disagreement is a third judge invoked, cutting redundant calls by
      roughly 80&ndash;95% relative to a fixed three-judge vote.
    </figcaption>
  </figure>
</article>

<!-- ===================== RGV ===================== -->
<article class="tp-paper" id="rgv">
  <div class="tp-meta">
    <span class="tp-venue">WiNLP 2025</span>
    <span class="tp-year">2025</span>
  </div>
  <h2 class="tp-title">Reference-Guided Verdict: LLMs-as-Judges in Automatic Evaluation of Free-Form QA</h2>
  <p class="tp-authors">Sher Badshah, Hassan Sajjad</p>
  <p class="tp-links">
    <a href="https://doi.org/10.48550/arXiv.2408.09235">arXiv</a>
  </p>

  <h3 class="tp-h">Abstract</h3>
  <p class="tp-abstract">
    The emergence of Large Language Models (LLMs) as chat assistants capable of generating
    human-like conversations has amplified the need for robust evaluation methods,
    particularly for open-ended tasks. Conventional metrics such as EM and F1, while useful,
    are inadequate for capturing the full semantics and contextual depth of such generative
    outputs. We propose a reference-guided verdict method that automates the evaluation
    process by leveraging multiple LLMs as judges. Through experiments on free-form
    question-answering tasks, we demonstrate that combining multiple models improves the
    reliability and accuracy of evaluations, especially in tasks where a single model may
    struggle. The results indicate a strong correlation with human evaluations, establishing
    the proposed method as a reliable alternative to traditional metrics.
  </p>

  <figure class="tp-figure">
    <a href="{{ '/assets/img/thesis/rgv_method.png' | relative_url }}" title="Open the full-resolution figure">
      <img src="{{ '/assets/img/thesis/rgv_method.png' | relative_url }}"
            alt="Reference-guided verdict method: a candidate LLM answer is sent, with the question and reference answer, to several LLM judges that each return a verdict and explanation." loading="lazy">
    </a>
    <figcaption>
      A candidate LLM produces a free-form output <em>a</em> for question <em>x</em>. Each
      LLM judge receives the triple (<em>x</em>, <em>a</em>, <em>r</em>) with the reference
      answer <em>r</em> and returns a True/False verdict with an explanation; the verdicts
      are combined by majority vote.
    </figcaption>
  </figure>
</article>

<!-- ===================== JRA ===================== -->
<article class="tp-paper" id="jra">
  <div class="tp-meta">
    <span class="tp-venue tp-venue-wip">In progress</span>
    <span class="tp-year">2026</span>
  </div>
  <h2 class="tp-title">Judge, Retrieve, or Abstain: Uncertainty-Guided LLM Judging with Provable Risk Guarantees</h2>
  <p class="tp-authors">Sher Badshah, Ali Emami, Hassan Sajjad</p>

  <h3 class="tp-h">Abstract</h3>
  <p class="tp-abstract">
    Using LLMs as judges has become standard practice for evaluating model outputs at scale. This is particularly common for subjective, open-ended tasks such as assessing helpfulness or alignment, where no single reference answer exists. However, objective tasks introduce a distinct reliability challenge for reference-free LLM judging. In the absence of a reference answer, the judge evaluates factual correctness either through its parametric knowledge or tool augmentation. While parametric knowledge enables efficient evaluation, it may suffer from hallucinations or lack of evidence. Conversely, tool augmentation can provide additional evidence but introduces extra computational cost and yet requires an appropriate mechanism to determine when and how that evidence should be used reliably. More importantly, neither approach alone provides formal control over the risk of accepted verdicts, making it difficult to guarantee a desired level of reliability. We propose a risk-controlled framework that calibrates uncertainty thresholds on a held-out set so that the false discovery rate among accepted verdicts stays below a user-specified level~$\alpha$ with high probability, using finite-sample Clopper--Pearson intervals. When the parametric mode is not confident, the instance is routed to a retrieval-augmented mode, where the judge gathers web evidence and re-evaluates under a second calibrated threshold. The finite-sample guarantee carries over to this two-threshold routing without additional assumptions. Across open-domain QA benchmarks and judges of varying scale, the framework holds the target error rate while achieving substantially higher coverage than single-mode baselines.
  </p>

  <figure class="tp-figure">
    <a href="{{ '/assets/img/thesis/jra_method.png' | relative_url }}" title="Open the full-resolution figure">
      <img src="{{ '/assets/img/thesis/jra_method.png' | relative_url }}"
            alt="Two algorithms: offline calibration of the two routing thresholds, and the online test-time decision to answer, retrieve and re-judge, or abstain." loading="lazy">
    </a>
    <figcaption>
      Offline, two thresholds are calibrated using a Clopper--Pearson FDR bound. In the Online setting, confident cases are accepted directly while uncertain cases are routed to retrieval and re-evaluated. The remaining uncertain cases abstained and sent for human review.
    </figcaption>
  </figure>
</article>

</div>

<style>
.thesis-papers {
  max-width: 62rem;
  margin: 0 auto;
}

.thesis-papers .tp-intro {
  font-size: 1.05rem;
  line-height: 1.7;
  color: var(--global-text-color);
  margin-bottom: 2rem;
}

/* ---- jump nav ---- */
.thesis-papers .tp-toc {
  display: flex;
  flex-wrap: wrap;
  gap: 0.5rem;
  padding: 0 0 2.5rem 0;
  border-bottom: 1px solid var(--global-divider-color);
  margin-bottom: 3rem;
}

.thesis-papers .tp-toc a {
  display: inline-flex;
  align-items: baseline;
  gap: 0.4rem;
  padding: 0.35rem 0.75rem;
  border: 1px solid var(--global-divider-color);
  border-radius: 999px;
  font-size: 0.85rem;
  line-height: 1.3;
  color: var(--global-text-color);
  text-decoration: none;
  transition: background-color 0.15s ease, color 0.15s ease;
}

.thesis-papers .tp-toc a:hover {
  background-color: var(--global-theme-color);
  color: #fff;
}

.thesis-papers .tp-toc a span {
  font-size: 0.72rem;
  opacity: 0.7;
}

.thesis-papers .tp-toc a:hover span {
  opacity: 0.9;
}

/* ---- paper block ---- */
.thesis-papers .tp-paper {
  padding: 0 0 3rem 0;
  margin-bottom: 3rem;
  border-bottom: 1px solid var(--global-divider-color);
  scroll-margin-top: 5rem;
}

.thesis-papers .tp-paper:last-of-type {
  border-bottom: none;
  margin-bottom: 0;
}

.thesis-papers .tp-meta {
  display: flex;
  align-items: center;
  gap: 0.6rem;
  margin-bottom: 0.6rem;
}

.thesis-papers .tp-venue {
  display: inline-block;
  padding: 0.2rem 0.6rem;
  border-radius: 4px;
  background-color: var(--global-theme-color);
  color: #fff;
  font-size: 0.75rem;
  font-weight: 600;
  letter-spacing: 0.03em;
  text-transform: uppercase;
}

.thesis-papers .tp-venue-wip {
  background-color: transparent;
  color: var(--global-theme-color);
  border: 1px solid var(--global-theme-color);
}

.thesis-papers .tp-year {
  font-size: 0.8rem;
  color: var(--global-text-color-light);
}

.thesis-papers .tp-title {
  margin: 0 0 0.4rem 0;
  font-size: 1.45rem;
  line-height: 1.35;
  font-weight: 600;
  color: var(--global-text-color);
}

.thesis-papers .tp-authors {
  margin: 0 0 0.5rem 0;
  font-size: 0.95rem;
  color: var(--global-text-color-light);
}

.thesis-papers .tp-links {
  margin: 0 0 1.2rem 0;
  font-size: 0.85rem;
}

.thesis-papers .tp-links a {
  display: inline-block;
  padding: 0.15rem 0.55rem;
  margin-right: 0.4rem;
  border: 1px solid var(--global-divider-color);
  border-radius: 4px;
  color: var(--global-theme-color);
  text-decoration: none;
}

.thesis-papers .tp-links a:hover {
  background-color: var(--global-theme-color);
  color: #fff;
}

.thesis-papers .tp-h {
  margin: 1.4rem 0 0.5rem 0;
  font-size: 0.78rem;
  font-weight: 700;
  letter-spacing: 0.12em;
  text-transform: uppercase;
  color: var(--global-text-color-light);
}

.thesis-papers .tp-abstract {
  margin: 0;
  font-size: 0.97rem;
  line-height: 1.75;
  text-align: justify;
  color: var(--global-text-color);
}

/* ---- centered method figure ---- */
.thesis-papers .tp-figure {
  margin: 2rem auto 0 auto;
  text-align: center;
}

.thesis-papers .tp-figure a {
  display: block;
  cursor: zoom-in;
}

.thesis-papers .tp-figure img {
  display: block;
  max-width: 100%;
  height: auto;
  margin: 0 auto;
  padding: 0.75rem;
  border: 1px solid var(--global-divider-color);
  border-radius: 6px;
  background-color: #fff;
  transition: box-shadow 0.15s ease;
}

.thesis-papers .tp-figure a:hover img {
  box-shadow: 0 2px 12px rgba(0, 0, 0, 0.12);
}

.thesis-papers .tp-figure figcaption {
  max-width: 46rem;
  margin: 0.85rem auto 0 auto;
  font-size: 0.85rem;
  line-height: 1.6;
  text-align: center;
  color: var(--global-text-color-light);
}

@media (max-width: 576px) {
  .thesis-papers .tp-title { font-size: 1.2rem; }
  .thesis-papers .tp-abstract { text-align: left; }
}
</style>
