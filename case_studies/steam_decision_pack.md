# Steam Decision Pack — Pricing, Positioning, and Launch Timing Recommendation

![Python](https://img.shields.io/badge/Python-3.10-3776AB?style=flat&logo=python&logoColor=white)
![SQL](https://img.shields.io/badge/SQL-PostgreSQL-336791?style=flat&logo=postgresql&logoColor=white)
![Market Analytics](https://img.shields.io/badge/Domain-Market_Analytics-7C4DFF?style=flat)

## TL;DR
- Built a decision pack to evaluate Steam launch strategy across pricing, market positioning, and timing.
- Combined segmentation and benchmark-style analysis to support a practical ship-plan recommendation.
- Framed outputs for stakeholders as a concise recommendation memo with assumptions, risks, and next-step checks.

## Business Question
What pricing and release strategy should be prioritized to maximize launch potential while reducing downside risk on Steam?

## Stakeholder + Use Case
- **Primary audience:** Product, Marketing, and Growth stakeholders.
- **Decision supported:** Recommend launch price band, positioning strategy, and timing window.
- **Operating cadence:** Pre-launch planning with post-launch review checkpoints.

## KPI Framework
| KPI | Why it matters |
| --- | --- |
| Wishlist-to-sales conversion proxy | Early indicator of launch efficiency |
| Review sentiment signal | Quality and satisfaction feedback loop |
| Price band competitiveness | Positioning against category alternatives |
| Release-window density | Competitive pressure around launch timing |

## Analytical Approach
1. Segment comparable Steam titles by genre/positioning.
2. Benchmark price bands and outcome signals across comparable groups.
3. Identify scenarios with favorable upside vs. manageable risk.
4. Convert findings into a decision memo with explicit assumptions and follow-up validation checks.

## Key Findings
- Mid-range pricing bands in comparable segments appear to offer a stronger balance of conversion potential and review risk than edge-case premium pricing.
- Competitive launch density can materially affect visibility, suggesting that timing is nearly as important as pricing.
- Positioning clarity (audience + value proposition) improves decision confidence more than isolated metric movement.

## Recommended Actions
### 1) Pricing strategy
- Start in the recommended price band from benchmark analysis.
- Define guardrails for promotional testing without devaluing positioning.

### 2) Launch timing
- Avoid high-density release windows where discoverability risk spikes.
- Sequence outreach and content updates around launch-week visibility windows.

### 3) Decision governance
- Track core KPIs weekly after launch and predefine thresholds for strategy adjustments.
- Maintain a short assumptions log to connect observed outcomes to prior decisions.

## Quantified Impact Plan (implementation-ready)
To close the “directional insight → measurable business delta” gap, this case study now includes a repeatable impact model.

| Metric | Baseline | Target delta | Translation to business value |
| --- | --- | --- | --- |
| Wishlist-to-sales conversion proxy | pre-launch benchmark for closest comps | +10% to +25% versus low-fit baseline scenario | `(wishlist volume × conversion uplift × net price)` |
| Review sentiment (first 30 days) | comp median by genre/price band | +3 to +8 sentiment points | sentiment lift used as a leading indicator for conversion/visibility durability |
| Launch-window visibility risk | baseline release-density index | avoid top-density windows; target 20%+ lower congestion bands | lower congestion translated to reach/discoverability opportunity |

**30/60/90 validation plan**
- **30 days:** validate launch-week conversion vs benchmark assumptions and price-band expectations.
- **60 days:** monitor review trajectory and discount sensitivity to confirm positioning fit.
- **90 days:** update pricing and promo strategy based on realized conversion + sentiment profile.

## Business Impact (Portfolio Context)
- Demonstrates cross-functional decision support outside healthcare while keeping a structured analytics workflow.
- Shows ability to translate market analytics into actionable recommendation packs with clear risk framing.

## Artifacts
- Repo: https://github.com/stalcup-dev/steam-decision-pack
- Project README and outputs: https://github.com/stalcup-dev/steam-decision-pack#readme
- Portfolio README reference: [Main portfolio README](../README.md)

## Tech + Skills Demonstrated
- Python + SQL for market segmentation and benchmark analysis
- Decision-pack communication: recommendation memo, assumptions, and risk framing
- Product/market analytics for pricing and launch strategy
