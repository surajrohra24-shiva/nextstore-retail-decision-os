# NEXTSTORE — Model Specification

## 1. Decision objective

Select the expansion location that creates the strongest **incremental value for the overall network**, not merely the highest gross sales or raw footfall.

## 2. Core model blocks

### A. Qualified demand

`Qualified Demand = Daily Footfall × (Avg Household Income / Candidate-set Median Income)`

This deliberately avoids treating footfall as a standalone proxy for demand quality.

### B. Estimated annual sales

`Estimated Sales = Qualified Demand × Conversion Rate × Average Basket × 365`

The prototype uses illustrative values of 4.0% conversion and ₹470 average basket.

### C. MCDA opportunity score

The directional score combines:

- Demand quality — 30%
- Unit economics — 25%
- Competition — 15%
- Accessibility — 15%
- Network protection — 15%

The UI normalizes these weights automatically when sliders are changed.

### D. Competition score

Competition is approximated from competitor count and nearest-competitor distance.

### E. Accessibility score

`Accessibility = 45% road/access + 30% transit + 10% parking + 15% visibility`

### F. Cannibalisation proxy

The prototype uses a **simplified distance-decay proxy inspired by gravity/Huff logic**. Candidate proximity to existing stores and existing-store sales scale the overlap signal.

The coefficient is illustrative and must be calibrated against real customer substitution / catchment data before production use.

### G. Gross incremental contribution

`Gross Contribution = Estimated Sales × Contribution Margin − Annual Rent`

### H. Cannibalised contribution loss

`Cannibalised Loss = Estimated Sales × Cannibalisation Rate × Cannibalised Contribution-Loss %`

The prototype uses an illustrative 18% contribution loss on displaced sales.

### I. Net Incremental Value

`Net Incremental Value = Gross Contribution − Cannibalised Loss`

This is the prototype's **north-star KPI**.

### J. ROI

`ROI = Net Incremental Value / Setup Capex`

### K. Decision confidence

A directional prototype signal based on modelled competition, rent pressure and network-overlap conditions. It is not a statistical probability or forecast interval.

## 3. Decision logic

Base-case labels:

- **OPEN** — Net Incremental Value ≥ ₹0.95 Cr and ROI ≥ 25%
- **VALIDATE** — Net Incremental Value ≥ ₹0.55 Cr but does not meet both OPEN conditions
- **REJECT** — below the VALIDATE threshold

These thresholds are illustrative and should be configured by the retailer in production.

## 4. Decision breaker

For the selected top site, the prototype sweeps footfall and rent assumptions until the runner-up overtakes it. This creates an **assumption breakpoint** rather than pretending the base-case recommendation is certain.

## 5. AI layer

AI is a synthesis and challenge layer:

1. Receive structured deterministic outputs.
2. Explain the main business drivers.
3. Highlight the largest watch-out.
4. Suggest what should be validated next.
5. Never invent or override model numbers.

## 6. Production validation

Before a live investment tool is used, calibrate:

- conversion rates by store archetype
- basket value by category / catchment
- contribution margins
- rent and occupancy economics
- competitor attractiveness
- catchment boundaries
- observed substitution / cannibalisation
- seasonality
- retailer-specific capital hurdle rates
