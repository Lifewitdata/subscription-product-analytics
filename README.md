<div align="center">

<img src="https://capsule-render.vercel.app/api?type=soft&color=0:1a1a2e,50:16213e,100:0f3460&height=200&section=header&text=Subscription%20Analytics%20%E2%80%94%20Simple%20Walkthrough&fontSize=32&fontColor=e94560&animation=twinkling&fontAlignY=40&desc=One%20notebook.%20One%20small%20step%20per%20cell.%20No%20fancy%20stuff.&descAlignY=62&descSize=15&descColor=eaeaea" width="100%"/>

<br/>

<img src="https://readme-typing-svg.demolab.com?font=JetBrains+Mono&weight=500&size=18&duration=3000&pause=1000&color=E94560&center=true&vCenter=true&multiline=true&repeat=true&width=850&height=90&lines=50%2C000+customers+%C2%B7+56%2C097+subscription+rows+%C2%B7+2.27M+events;46.7%25+conversion+%C2%B7+30.4%25+churn+%C2%B7+%24564%2C527+MRR;read+CSVs+%E2%86%92+print+stuff+%E2%86%92+make+a+chart+%E2%86%92+repeat" alt="Typing SVG" />

<br/><br/>

<img src="https://img.shields.io/badge/Python-3.12-1a1a2e?style=for-the-badge&logo=python&logoColor=E94560&labelColor=0f3460">
<img src="https://img.shields.io/badge/Polars-only-1a1a2e?style=for-the-badge&logo=polars&logoColor=E94560&labelColor=0f3460">
<img src="https://img.shields.io/badge/NumPy-corrcoef%20only-1a1a2e?style=for-the-badge&logo=numpy&logoColor=E94560&labelColor=0f3460">
<img src="https://img.shields.io/badge/Matplotlib%20%2B%20Seaborn-charts-1a1a2e?style=for-the-badge&labelColor=0f3460&color=E94560">
<img src="https://img.shields.io/badge/Style-junior%20analyst-1a1a2e?style=for-the-badge&labelColor=0f3460&color=E94560">

</div>

<br/>

## 🧭 What this actually is

**One notebook** — `simple_analyst_walkthrough.ipynb` — written the way a
first-time product analyst would really type it: one small step per cell,
plain variable names, printing things out to look at them before doing the
next step. No functions, no classes, no clever one-liners.

> [!IMPORTANT]
> This notebook does **not** generate any data. The CSVs already exist in
> `data/` — this notebook only reads and explores them. It's also the
> *simple* pass: churn here counts every customer who ever cancelled (even
> ones who later came back), and the A/B test section is eyeballed with bar
> charts rather than an actual significance test. Both are called out
> in-notebook rather than quietly glossed over.

<br/>

## 📓 The six steps

| Step | Question | Headline number(s) |
|:--|:--|:--|
| **0 — Setup** | Load libraries, point at `data/` | 8 CSVs available |
| **1 — Subscriptions** | How's the business doing? | 50,000 customers · **46.7%** conversion · **30.4%** churn · **$564,527** MRR · **$34.65** ARPU |
| **2 — Engagement vs. retention** | Do heavier users stick around? | 2.27M product events, bucketed into Low / Medium / High usage (~17K each) |
| **3 — Marketing & A/B tests** | Is spend working, did the tests move anything? | **19.5%** click-through · **1.43%** impression → paid · 5 experiments eyeballed |
| **4 — Support tickets** | What's support telling us? | **94.4%** resolved · **17.6%** SLA breach · **3.81** avg CSAT · **11.8%** reopen rate |
| **5 — What drives CSAT?** | SLA breach or resolution time? | SLA breach correlation **−0.484** vs. resolution time **−0.091** — breaching SLA hurts CSAT far more |
| **6 — What to fix first** | Which issues are actually worth prioritising? | **17 of 72** issue types flagged "high priority" (above-average volume *and* above-average SLA breach) |

<br/>

## 📊 Chart gallery

Every step ends in a plot, and no two use the same chart type — deliberately,
so the notebook doubles as a quick tour of "which chart for which question":

<div align="center">

| Chart | Where | Why this one |
|:--|:--|:--|
| 🍩 Donut | Active subscribers by plan | Simple part-of-whole mix |
| 📈 Line | Retention by engagement level | Shows the Low → Medium → High trend directly |
| 🍭 Lollipop | Cost per paying customer by channel | Less ink than a bar, same ranking |
| 🏋️ Dumbbell | A/B test control vs. treatment | One line per experiment beats five side-by-side subplots |
| 📊 Pareto (bar + line) | Ticket volume by product area | Bars *and* the cumulative % in one view |
| 🍭 Lollipop + reference line | SLA breach by product area | Dot plot against the overall average |
| ↔️ Diverging bar | CSAT by product area | Red/green relative to the average, not absolute values |
| 📦 Box plot | CSAT: open vs. resolved | Shows the full spread, not just the mean |
| 🫧 Bubble | High-priority issues | Breach rate × CSAT × ticket volume in one plot |

</div>

<br/>

## 🗂️ What's in this repo

```text
.
├── simple_analyst_walkthrough.ipynb   ← the whole thing, top to bottom
└── data/
    ├── customers.csv
    ├── subscriptions.csv
    ├── product_events.csv
    ├── transactions.csv
    ├── marketing_campaigns.csv
    ├── customer_campaigns.csv
    ├── experiments.csv
    └── support_tickets.csv
```

No `scripts/`, no `outputs/` folder, no separate findings docs — this version
is the notebook and the notebook is the deliverable. The wrap-up cell points
toward a fuller, production-style pipeline (proper significance tests, a
hand-written K-Means, a weighted prioritisation score) as a *next* step, not
something already sitting in this repo.

<br/>

## 🚀 Quickstart

```bash
pip install polars numpy matplotlib seaborn jupyter

jupyter lab simple_analyst_walkthrough.ipynb
# run top to bottom — each cell depends on the ones before it
```

<br/>

## 🔎 The one finding worth remembering

> Whether a ticket breaches its SLA target predicts CSAT roughly **5× more
> strongly** than how long the ticket actually took to resolve (r = −0.484
> vs. −0.091). Customers seem to care more about a promise being kept than
> about raw speed — a simple `numpy.corrcoef`, no modelling required.

<br/>

<div align="center">

<img src="https://capsule-render.vercel.app/api?type=soft&color=0:0f3460,50:16213e,100:1a1a2e&height=100&section=footer"/>

</div>
