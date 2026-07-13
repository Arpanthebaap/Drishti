# Drishti — Predictive Risk Intelligence for MSME Lending
**IDBI Innovate 2026 · Track 04: MSME Credit, Predictive AI, Risk Management**

Drishti predicts MSME loan stress 12 months in advance by modelling the buyer-supplier network a borrower actually lives inside, not just the borrower's own financials. Most real MSME defaults are contagion events — a stressed anchor buyer, not a quietly rotting balance sheet — and that's exactly what structured-data-only models are structurally blind to.

## The problem
Current default-prediction capability sits at 16–22% accuracy, dependent solely on structured data, with fragmented methodologies across loan types and borrower segments. The brief calls for a robust solution estimating probability of default 12 months in advance, improving accuracy to 90%, using both structured and unstructured data, with a common interpretation framework across all MSME loans.

## The solution — three things that make it different
1. **A supply chain contagion graph, not just a single-entity scorecard.** Built from GST e-invoice and e-way bill data, Drishti models every borrower as a node connected to its real buyers and suppliers. When a major buyer shows payment-delay patterns, that risk propagates through the graph — catching stress 12 months before it reaches the borrower's own books. This is the single biggest reason structured-only models cap out at 16–22%: they cannot see the trigger, only the eventual symptom.
2. **A multi-modal expert ensemble, segment-weighted.** Four specialized models — structured financials, unstructured text (RM visit notes, litigation, news), the supply-chain graph, and behavioral time-series (EPFO contribution trend, utility payment trend) — each contribute, weighted differently by loan type and borrower segment.
3. **One common interpretation framework regardless of loan type.** Every loan gets the same standardized output: a unified Early Warning Score, a risk band, and the top 3 plain-language stress drivers — directly solving the brief's "fragmented methodologies" complaint.

## What this prototype demonstrates
Three interactive views:
- **Portfolio Early Warning** — a headline comparison of the current 16–22% accuracy ceiling vs. Drishti's 90% target, plus a live portfolio list of MSME loans with unified scores, risk bands, and trend direction.
- **Supply Chain Contagion Graph** — an animated simulation showing how stress at a borrower's major buyer (Metro Retail Chain) propagates through the network to the borrower (Sundar Textiles) — 12 months before it would show up in the borrower's own bank statement.
- **Multi-Modal Score Breakdown** — a single loan's four expert sub-scores combined into one unified score, with standardized top-3 stress drivers and a recommended risk-band action.

## How to use the demo
Open `index.html` → try all three tabs → on the Contagion Graph tab, click "Simulate Buyer Stress" and watch the propagation animate through the network.

## Tech (this prototype)
- Frontend: HTML5, CSS3, vanilla JavaScript — fully client-side, no backend or API keys required
- All scenarios are scripted simulations over a synthetic MSME portfolio, built to demonstrate the ensemble logic and interpretation framework of each layer

## Path to production
| Layer | Demo (this build) | Production (IDBI sandbox) |
|---|---|---|
| Structured model | Rule-based weighted scoring | XGBoost/LightGBM on financial ratios + bureau |
| Unstructured / NLP model | Scripted text signals | Transformer-based risk-phrase extraction on RM notes/news/litigation |
| Supply chain graph | Simulated network | Graph Neural Network on GST e-invoice/e-way bill data |
| Behavioral time-series | Scripted trend data | Sequence model on EPFO/utility payment trends |
| Ensemble & scoring | Static weighting demo | Segment-weighted mixture-of-experts service |
| Infrastructure | Client-side only | Cloud-native, IDBI sandbox integration |

## Rollout plan
- **Phase 1 — Pilot (8–10 weeks):** Single segment (e.g. textile/auto-parts working capital loans), structured + graph models only.
- **Phase 2 — Integration (4–6 months):** Add NLP + behavioral models, full ensemble, RM workflow triggers.
- **Phase 3 — Scale (ongoing):** Full portfolio coverage across all loan types, continuous retraining.

## Team
Arpan Ghosh (Solo Participant), Contact: arpanghosh984@gmail.com | https://arpanghosh.in/ 

## License
Built for IDBI Innovate 2026 submission purposes. MIT LICENSE: https://github.com/Arpanthebaap/Drishti/blob/main/LICENSE 
