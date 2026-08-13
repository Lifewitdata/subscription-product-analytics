<div align="center">

<img src="https://capsule-render.vercel.app/api?type=soft&color=0:1a1a2e,50:16213e,100:0f3460&height=220&section=header&text=Subscription%20Product%20Analytics&fontSize=38&fontColor=e94560&animation=twinkling&fontAlignY=40&desc=8%20phases%20%C2%B7%2098%20tables%20%C2%B7%2057%20charts%20%C2%B7%20zero%20black%20boxes&descAlignY=58&descSize=17&descColor=eaeaea" width="100%"/>

<br/>

<img src="https://readme-typing-svg.demolab.com?font=JetBrains+Mono&weight=500&size=20&duration=3200&pause=1000&color=E94560&center=true&vCenter=true&multiline=true&repeat=true&width=850&height=100&lines=raw+CSVs+%E2%86%92+data%2F;pipeline.run()+%E2%86%92+8+phases+of+analysis;insight+%E2%86%92+outputs%2F*.md+%2B+57+charts;no+pandas.+no+sklearn.+no+scipy.stats." alt="Typing SVG" />

<br/><br/>

<a href="#-quickstart"><img src="https://img.shields.io/badge/Python-3.11-1a1a2e?style=for-the-badge&logo=python&logoColor=E94560&labelColor=0f3460"></a>
<a href="#-quickstart"><img src="https://img.shields.io/badge/Polars-engine-1a1a2e?style=for-the-badge&logo=polars&logoColor=E94560&labelColor=0f3460"></a>
<a href="#%EF%B8%8F-built-by-hand-not-imported"><img src="https://img.shields.io/badge/Stats-hand--written-1a1a2e?style=for-the-badge&labelColor=0f3460&color=E94560"></a>
<a href="#%EF%B8%8F-built-by-hand-not-imported"><img src="https://img.shields.io/badge/NumPy-vectorized-1a1a2e?style=for-the-badge&logo=numpy&logoColor=E94560&labelColor=0f3460"></a>
<a href="#-repo-map"><img src="https://img.shields.io/badge/Jupyter-single%20entry%20point-1a1a2e?style=for-the-badge&logo=jupyter&logoColor=E94560&labelColor=0f3460"></a>

<br/>

<sub>Status</sub>

![](https://progress-bar.xyz/100/?title=Phase%208%20shipped&width=300&color=e94560&suffix=%25)

</div>

<br/>

## 🧭 What this actually is

A subscription fintech/SaaS business, fully simulated end to end — **generation →
subscriptions → engagement → marketing → support → prioritisation** — where
*every single number in every chart traces back to a CSV in `data/`*. Nothing in
here is hand-typed or vibes-based.

> [!NOTE]
> No pandas. No scikit-learn. No `scipy.stats` / `statsmodels`. Wherever the brief
> called for statistics or clustering, it's implemented from first principles.
> Jump to [**⚙️ Built by hand**](#%EF%B8%8F-built-by-hand-not-imported) for the receipts.

<br/>

## 🌊 How data flows through it

```mermaid
%%{init: {'theme':'dark', 'themeVariables': {'primaryColor':'#16213e','primaryTextColor':'#eaeaea','lineColor':'#e94560','secondaryColor':'#0f3460','tertiaryColor':'#1a1a2e'}}}%%
flowchart LR
    subgraph GEN["🏗️ generation"]
        A[generate_data.py]
        B[generate_support_tickets.py]
    end

    subgraph CORE["📊 core analytics"]
        P1["Phase 1 — subscriptions"]
        P2["Phase 2 — engagement · retention · segments"]
        P3["Phase 3 — marketing · A/B tests"]
    end

    subgraph SUPPORT["🎧 support & CX"]
        P4["Phase 4 — support funnel · SLA"]
        P5["Phase 5 — issue · friction analysis"]
        P7["Phase 7 — customer experience"]
    end

    subgraph DECIDE["🎯 decision layer"]
        P8["Phase 8 — prioritisation P0–P3"]
    end

    A --> P1 --> P2 --> P3
    B --> P4 --> P5
    P2 -.behavioural features.-> P5
    P3 -.channel & segment.-> P5
    P5 --> P7 --> P8
    P1 -.churn ledger.-> P7
    P2 -.segments.-> P7
```

<sup>Phase 6 was cut mid-project and never rebuilt — Phase 7 picks up straight after
Phase 5. Called out here rather than quietly renumbered.</sup>

<br/>

## 📖 Phase by phase

<details open>
<summary><b>🏗️ Phase 0 — Synthetic data generation</b></summary>
<br/>

50,000 customers · 56K subscriptions · 2.3M product events · 720K transactions ·
28K support tickets — relationally consistent, seeded, fully reproducible.

`scripts/generate_data.py` · `scripts/generate_support_tickets.py`
</details>

<details>
<summary><b>1️⃣ Subscription performance</b></summary>
<br/>

**46.7%** conversion · **$592K** MRR · **27.9%** churn · full MRR/ARPU/plan-mix
trend over time.

📄 <a href="outputs/business_summary.md">business_summary.md</a>
</details>

<details>
<summary><b>2️⃣ Engagement, retention & segmentation</b></summary>
<br/>

High-engagement subscribers retain **85.7%** at Month 12 vs. **0.9%** for
Low-engagement — the strongest single signal in the whole project. Six
behavioural segments, produced via rule-based RFM plus a from-scratch NumPy
K-Means.

📄 <a href="outputs/phase2_insights.md">phase2_insights.md</a>
</details>

<details>
<summary><b>3️⃣ Marketing funnel & A/B testing</b></summary>
<br/>

Full funnel, 91K impressions down to 1.3K paying customers · CAC/ROI by
channel · five experiments classified significant/not, backed by a
hand-written pooled z-test and Welch's t-test.

📄 <a href="outputs/phase3_recommendations.md">phase3_recommendations.md</a>
</details>

<details>
<summary><b>4️⃣ Support funnel & SLA</b></summary>
<br/>

28,411 tickets → **94.4%** resolved · **82.4%** SLA compliance · **3.81**
baseline CSAT.

📄 <a href="outputs/phase4_findings.md">phase4_findings.md</a>
</details>

<details>
<summary><b>5️⃣ Issue & friction analysis</b></summary>
<br/>

Payroll has the lowest usage of any feature — and the *highest* ticket rate.
Friction-per-use, not raw volume, tells the real story here.

📄 <a href="outputs/phase5_findings.md">phase5_findings.md</a>
</details>

<details>
<summary><b>7️⃣ Customer experience</b></summary>
<br/>

SLA breaches correlate with CSAT **5× stronger** than raw resolution time
(r = −0.484 vs. −0.091) · 255 of 256 issues show churn above baseline.

📄 <a href="outputs/phase7_findings.md">phase7_findings.md</a>
</details>

<details>
<summary><b>8️⃣ Issue prioritisation & business impact</b></summary>
<br/>

256 issues scored across 8 dimensions → bucketed **P0–P3** → ranked Top 5,
with an honest volume-vs-severity caveat baked directly into the write-up
rather than smoothed over.

📄 <a href="outputs/phase8_prioritization_summary.md">phase8_prioritization_summary.md</a>
</details>

<br/>

## ⚙️ Built by hand, not imported

<div align="center">

| The brief said "just import a library" | What's actually running |
|:--|:--|
| Two-proportion significance test | Pooled z-test from the raw formula, `math.erf` for the normal CDF |
| Confidence intervals | Wald CI with a hand-coded inverse-normal (Acklam's approximation) |
| Welch's t-test | Computed straight from means/variances, large-*n* normal approximation |
| K-Means clustering | Pure-NumPy Lloyd's algorithm, centroids ranked and hand-labelled into segments |
| Correlation analysis | Pearson *r* derived from first principles — no `scipy.stats.pearsonr` |

</div>

<br/>

## 🗂️ Repo map

```text
subscription-product-analytics/
├── subscription_product_analytics_full_pipeline.ipynb   ← the entire project, one notebook
├── README.md
│
├── data/                          8 CSVs — generated, not hand-written
│   ├── customers.csv              ├── product_events.csv
│   ├── subscriptions.csv          ├── transactions.csv
│   ├── marketing_campaigns.csv    ├── customer_campaigns.csv
│   ├── experiments.csv            └── support_tickets.csv
│
├── outputs/
│   ├── charts/                    57 PNGs
│   ├── tables/                    98 CSVs
│   └── *.md                       one findings/recommendations doc per phase
│
└── scripts/                       source .py the notebook is assembled from
    ├── build_notebook.py          run after editing a script to rebuild the notebook
    └── ...                        one generation/analysis script per notebook section
```

> The notebook is the single entry point — every phase runs top to bottom in one
> file. `scripts/` holds the underlying source for editing or running a phase
> standalone; it isn't meant to be read as a separate deliverable.

<br/>

## 🚀 Quickstart

```bash
pip install polars numpy matplotlib seaborn nbformat nbclient ipykernel

# run the whole project end to end
# (generation cells auto-skip if data/ already exists)
jupyter nbconvert --to notebook --execute subscription_product_analytics_full_pipeline.ipynb

# or open it interactively
jupyter lab subscription_product_analytics_full_pipeline.ipynb
```

<br/>

## 🔎 A finding worth reading twice

> Across Phases 5, 7, and 8 the same tension keeps resurfacing: **raw ticket
> volume and genuine customer friction point to different issues.** The
> highest-volume tickets tend to be routine and well-rated; the worst
> experiences hide in low-volume, high-severity issues a volume-only view
> would never surface. Phase 8's Top-5 table keeps both readings visible
> instead of collapsing them into one misleadingly tidy ranking — see the
> honesty check in
> [`prioritization_summary.md`](outputs/phase8_prioritization_summary.md#top-5-ranked-product-issues).

<br/>

<div align="center">

**Phases 1–8 shipped** · Phase 9 (executive report) not yet started

<img src="https://capsule-render.vercel.app/api?type=soft&color=0:0f3460,50:16213e,100:1a1a2e&height=120&section=footer"/>

</div>
