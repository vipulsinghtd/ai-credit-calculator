# Treasure AI Credit Calculator

Standalone calculator for **AI Suite credits** (`ai-credit-calculator.html`) plus the source workbook (`ai-credit-calculator.xlsx`). It estimates monthly and annual AI credits, adds a headroom buffer, and maps the result to an AI Suite tier (A–AF). **Finalize & Download Excel** exports the estimate.

For the combined CDP (P+B) + AI credits estimator with sheet submission, see [pricing-calculator](https://github.com/vipulsinghtd/pricing-calculator).

## Credit rates (1 credit =)

| Product | Metric | Units per credit |
|---|---|---|
| AI Foundry | Conversations | 600 |
| Agentic Engage | Email Messages | 1 Million |
| Agentic Engage | Email Clicks | 20 Thousand |
| Agentic Engage | SMS Messages | 10 Thousand |
| Agentic Engage | Mobile Push Messages | 10 Million |
| RT Personalization / RT Triggers | RT Profiles (incurred monthly) | 1 Million |
| RT Personalization | Personalization Calls | 10 Million |
| RT Triggers | Incoming RT Trigger Events | 15 Million |
| RT Triggers | Outgoing RT Trigger Activations | 25 Million |
| AI Signals | Predictions – ML Models | 40 Million |
| AI Signals | Predictions – RFM Model | 100 Million |

In the HTML the rates live in the `RATES` object; in the workbook they're in cells `H7:H17`.

## Rules

- **RT Profiles are charged once.** If both RT Personalization and RT Triggers are used, Triggers only pays for profiles above the RT Personalization count.
- **AI Signals is included with AEP.** No package selections; credits come from predictions only.
- **Tier** = annual credits × (1 + buffer). Buffer: None / 5% / 10% (default 10%).
- **Room left in tier** = tier maximum − annual credits incl. buffer.
- Above Tier AF (59,999.99) the calculator shows "contact Deal Desk".
- No list prices or discount floors are shown or stored in this project.
