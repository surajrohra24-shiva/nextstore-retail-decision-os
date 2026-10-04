# NEXTSTORE — Retail Expansion Decision OS

## Assessment prototype

**Purpose:** A fast, explainable prototype for the "Where Should the Next Store Open?" business case.

### Core proposition
NEXTSTORE does not stop at ranking locations. It connects **market demand → unit economics → network impact → investment decision → stress test → next validation action**.

### Why this design
The prototype is built around a practical consulting workflow: deterministic business logic first, interactive decision support second, and AI-style executive synthesis last. The numerical engine is transparent so that a client can inspect the assumptions rather than treating an AI output as a black box.

### Signature feature — Decision Breaker
Instead of only saying which site is #1, NEXTSTORE shows the modeled assumption shock that would make the recommendation flip to the next-best site. This reframes the problem from **"Which site wins?"** to **"What could make our decision wrong?"**.

### What is interactive
- Portfolio ranking by **Net Incremental Value**
- Candidate / existing-store / competitor network view
- Location deep dive
- Strategic priority sliders that reweight the MCDA score without rebuilding the controls
- Decision stress test for footfall, rent and cannibalisation sensitivity
- Persistent scenario settings when changing the selected site
- "Decision Breaker" showing an illustrative breakpoint where the recommendation changes
- AI Decision Brief (simulated LLM synthesis layer for the static assessment prototype)
- CSV upload with same-file re-upload support

### AI architecture
The static prototype deliberately does **not** fabricate calculations with an LLM. The deterministic engine creates the numeric outputs. The AI Decision Brief is a **simulated LLM layer** that demonstrates where an LLM would summarize, challenge and recommend a validation action in a production workflow. In the presentation, this should be stated explicitly rather than represented as a live API integration.

### Synthetic-data note
All location, market, competitor, rent and store-performance data is synthetic and illustrative. It is designed to demonstrate the analytical journey, not to represent a real retailer or real neighbourhoods.

### Productionization path
Calibrate the model using actual:
1. Store P&Ls and lease terms
2. Transaction / conversion data
3. Mobility / footfall data
4. Competitor mapping and catchment boundaries
5. Observed store-to-store substitution
6. Business-specific expansion objectives and weights

## Files

- `index.html` — self-contained interactive browser prototype
- `candidates.csv` — synthetic candidate-site data
- `existing_stores.csv` — synthetic existing-store network
- `competitors.csv` — synthetic competitor points
- `data.json` — model-ready dataset and assumptions
- `NEXTSTORE_Model.xlsx` — transparent support workbook with formulas, inputs, ranking and scenario sheet
- `MODEL_SPEC.md` — analytical methodology and formulas
- `DEMO_SCRIPT.md` — 1.5-minute recording script
- `GEMINI_REVIEW_PROMPT.md` — independent second-opinion prompt for Gemini
- `SUBMISSION_CHECKLIST.md` — final packaging/deployment checklist

## Quick local use

Open `index.html` in a modern browser. No package installation is required for the self-contained prototype.

## Public deployment

The assessment requires a link that can be opened without examiner sign-in. Upload the contents of this folder to a **public GitHub repository** and enable **GitHub Pages** for the repository root so that `index.html` is served as the live prototype.

## Interview / presentation message

> "The important part of the prototype is not the score. It is the decision workflow. NEXTSTORE identifies the highest incremental value, exposes the assumptions that can break the decision, and tells management what to validate next."
