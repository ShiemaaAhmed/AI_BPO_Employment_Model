# AI and the Future of BPO Employment in Africa

An interactive, single-file dashboard that projects **net employment in Africa's BPO/GBS sector to 2031** under different AI-adoption, market-share and growth scenarios. It is a scenario-exploration tool — not a forecast — built to make the assumptions visible and the trade-offs explorable.

`AI_BPO_employment_model.html` · self-contained · no build step · opens in any modern browser

---

## What it does

The dashboard turns a task-level employment model into something you can interrogate. You set three scenario levers and every chart, total and breakdown updates live, so you can see how the 2031 jobs picture shifts — for the sector as a whole, for each sub-sector, and for women and young workers.

It distinguishes **net employment** (jobs remaining after automation, augmentation, market growth and AI-driven demand) from raw task exposure, and it is explicit about uncertainty rather than presenting a single number as fact.

## Scenario levers

- **AI adoption** — Conservative / Moderate / High (how fast AI is taken up through 2031)
- **Africa's share of the global market** — Decrease / Resilient / Increase
- **Global market growth** — Slow / Moderate / Fast

## Tabs

- **Overview** — headline 2031 net employment, the AI effect vs a no-AI counterfactual, and the range of likely outcomes
- **Sub-sectors** — Customer Experience, IT-Enabled Services, Finance/Accounting & HR, and AI Data Services, each with its own path
- **Inclusion** — women's and youth headcount and share by scenario, share-by-adoption table, and evolution charts for each AI-adoption path
- **Methodology** — a step-by-step explanation of the model, the key assumptions and their sources, and the uncertainty analysis

## How the model works (in brief)

Each role is split into tasks that AI can **automate**, tasks AI **augments** (made faster, partly retained as productivity rises), and tasks that are **resilient**. As AI adoption rises, automatable work shrinks and augmentable work is partly saved. The surviving work is scaled by global market growth and Africa's share of the market, then adjusted for an AI **demand effect** — cheaper, AI-enabled delivery expands demand, with each sub-sector responding differently.

```
Net jobs = ( Automatable×(1−A) + Augmentable×(1−g×A) + Resilient )
           × Market index
           × (1 + Demand effect + δ)
```

where `A` is the AI-adoption rate for the selected scenario, `g` is each sub-sector's productivity gain, and `δ` is its own demand response.

## Uncertainty

The "range of outcomes" view runs a **Monte Carlo** conditional on the selected scenario: 5,000 runs that vary the seven behavioural inputs (price elasticity, cost pass-through, labour share, and the four sub-sector demand responses) across plausible ranges, with the scenario held fixed. It reports a central estimate and a P10–P90 band so the firmness of each number is visible.

## Data and sources

Baseline workforce, sub-sector and role mix, task composition, and female/youth shares come from Caribou Digital & Genesis Analytics (2025) for the Mastercard Foundation. Structural assumptions and AI-adoption ranges draw on published work from the WEF, IMF, ILO, McKinsey, Goldman Sachs, Acemoglu (NBER), Brynjolfsson et al. (NBER), the Anthropic Economic Index, MIT NANDA, and Everest Group / NelsonHall. Qualitative evidence comes from Key Informant Interviews with operators, investors, industry bodies and ecosystem partners across the African GBS sector. Full citations and links are in the **Methodology** tab.

## Usage

Open `AI_BPO_employment_model.html` in a browser. There is no install, server or build step — all logic, styling and data are contained in the single file, and nothing is sent anywhere.

## Technical notes

- Single self-contained HTML file; React is bundled inline (no external requests, works offline)
- Pure client-side; no data leaves the browser and no storage is used
- Charts and tables are rendered as inline SVG/HTML

## Disclaimer

These are **modelled projections under a set of assumptions, not forecasts**. Outputs are intended to support discussion and decision-making, not to predict actual employment levels.
