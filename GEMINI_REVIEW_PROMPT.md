# Gemini — Independent Review Prompt

You are the independent reviewer of a business-analysis prototype called NEXTSTORE, submitted for an Illuminati Consulting Business Analyst assessment.

## Case
A retail chain can invest in only a few new stores. Candidate neighbourhoods differ in customer demand, competition, rent and accessibility. High footfall does not always mean profitable sales, and a new store may cannibalise an existing store. The challenge is to build a working prototype that compares shortlisted locations, recommends where to open next, and explains trade-offs.

## Current concept
NEXTSTORE is an interactive Retail Expansion Decision OS.

Workflow:
`Data → Economics → Network impact → Decision → Decision Breaker → Validation Action → AI Brief`

Core metrics:
- Qualified demand: footfall adjusted by household income
- Unit economics
- Competition
- Accessibility
- Simplified distance-decay cannibalisation proxy
- Net Incremental Value
- ROI
- Decision confidence
- Scenario sensitivity

Signature features:
1. Decision Breaker — what assumption could overturn the recommendation?
2. Open / Validate / Reject — prioritises actions rather than merely ranking sites.
3. Highest-value missing information — suggests what to validate before committing capital.
4. AI Decision Brief — explains deterministic results, does not invent numbers.
5. Interactive weight and scenario controls.

## Review task
Please be critical and specific. Do not simply agree.

1. What would an experienced consulting / BA evaluator still find generic?
2. Which one feature would make this genuinely memorable?
3. Is Net Incremental Value the right north-star metric for this case? What caveats should we disclose?
4. Is the simplified cannibalisation proxy defensible for a one-day prototype? What wording should we use?
5. Is the AI layer credible, or does it look like AI for decoration?
6. What UI/UX detail should be changed to look more like an actual client prototype?
7. What should be cut to reduce scope risk?
8. What should the 90-second demo emphasize?
9. Give 3 likely evaluator questions and strong factual responses.
10. Give a final "keep / change / cut" list.

Focus on practicality for a solo MBA candidate building a submission quickly. Avoid suggesting a major new architecture unless it can be built rapidly.
