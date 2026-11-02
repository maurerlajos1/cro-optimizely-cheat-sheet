# CRO and Optimizely Experimentation Interview Defense Cheat Sheets

Comprehensive, battle-tested reference guides and cheat sheets for **Conversion Rate Optimization (CRO)**, **Landing Page Architecture**, and **Optimizely Web and Feature Experimentation**.

Built for Senior CRO Strategists, Experimentation Leads, Growth Product Managers, and UX Researchers.

---

## Deliverables Included

| Deliverable | Format | Best Used For | Direct Links |
| :--- | :--- | :--- | :--- |
| **Rapid Recall Cheat Sheet** | Markdown, PDF (4 pages), Word | Dual-screen rapid recall during live interviews, fast keyword lookups, and one-sentence defense answers. | [Markdown](Rapid_Recall_CRO_and_Optimizely_Cheat_Sheet.md) / [PDF](Rapid_Recall_CRO_and_Optimizely_Cheat_Sheet.pdf) / [Word](Rapid_Recall_CRO_and_Optimizely_Cheat_Sheet.docx) |
| **Master Cheat Sheet** | Markdown, PDF (17 pages), Word | Exhaustive technical study, deep statistical equations, Optimizely architecture, and detailed framework breakdowns. | [Markdown](Master_CRO_and_Optimizely_Experimentation_Cheat_Sheet.md) / [PDF](Master_CRO_and_Optimizely_Experimentation_Cheat_Sheet.pdf) / [Word](Master_CRO_and_Optimizely_Experimentation_Cheat_Sheet.docx) |

---

## Core Frameworks and Methodologies

* **Peep Laja ResearchXL (6 Pillars):**
  * Technical Analysis (Cross-browser, cross-device, interactive time under 3.0 seconds)
  * Heuristic Analysis (Relevance, Clarity, Friction, Distraction)
  * Digital Analytics (GA4 funnel audit, tracking integrity check)
  * Mouse Tracking (Scroll depth false bottoms, click maps, rage clicks)
  * Qualitative VoC (Post-purchase 48-hour surveys, on-site exit polls)
  * User Testing (5 to 7 task-based observational usability tests)
* **Conversion Sequence Heuristics:**
  * MECLABS: C = 4m + 3v + 2(i - f) - 2a (Motivation is 4x weighted)
  * Andre Morys 7 Levels of Conversion (7E): Relevance, Trust, Orientation, Stimulation, Security, Convenience, Confirmation
  * Chris Goward LIFT Model: Value Proposition, Relevance, Clarity, Urgency, Anxiety, Distraction
* **Experimentation Strategy and Traffic Sufficiency:**
  * Ton Wesseling ROAR Model (Risk, Optimization, Automation and Re-think thresholds)
  * Ton Wesseling 6V Research Canvas (Value, Versus, View, Voice, Verified, Validated)
  * CXL PXL Matrix (13-point objective binary scoring to eliminate HIPPO bias)
  * PIPE Framework (Problem, Impact, Potential, Ease)
* **Optimizely Architecture and Stats Engine:**
  * Client-side Web vs. Server-side Feature Experimentation (SDKs)
  * Anti-Flicker Architecture and Page-Hiding Snippet (1,000 millisecond timeout safeguard)
  * SPA Manual Activation (window.optimizely.push activatePage)
  * Stats Engine mSPRT (Mixture Sequential Probability Ratio Test, always-valid p-values, peeking problem solved)
  * Multi-Armed Bandits (Thompson Sampling for short-term promotion exploitation)
  * Browser Console QA Commands (getExperimentStates, getVariationMap, visitor)
* **Statistical Rigor:**
  * Inverse-Square Law (Halving Minimum Detectable Effect requires 4x sample size)
  * Pearson Chi-Square Sample Ratio Mismatch (SRM) detection (p < 0.001)
  * False Discovery Rate (FDR) / Ioannidis Bayesian program ROI math
  * Standard: 80% Statistical Power, 95% Confidence (alpha = 0.05), 14-day minimum runtime (2 full business cycles)

---

## Top 10 Interview Pushback Defenses (Quick Answers)

1. **Why not put the form in the Hero above the fold?**  
   Asking for sensitive personal details before visitors understand the product value creates high anxiety and reduces conversion rates.
2. **If we show pricing upfront, will lead volume drop?**  
   Concealing pricing attracts low-intent leads that waste sales time, whereas transparent price anchoring filters for qualified buyers and increases revenue per visitor.
3. **Can we test 8 changes at once using a Multivariate Test (MVT)?**  
   An MVT requires multiplicative traffic across all factor combinations; running a high-impact radical A/B redesign is significantly faster and statistically safer.
4. **The test is significant on Day 3. Can we stop it?**  
   Stopping early causes severe false-positive bias due to day-of-week seasonality; every test must run for at least two full business cycles.
5. **How does Optimizely Stats Engine differ from classical testing tools?**  
   Optimizely uses mSPRT sequential testing to provide always-valid p-values that allow continuous monitoring without peeking penalties.
6. **What do you do if you detect a Sample Ratio Mismatch (SRM)?**  
   An SRM completely invalidates the statistical test; immediately halt the test and debug redirect latencies, bot filters, and tag firing order.
7. **An executive wants to copy Amazon 1-click checkout. What do you say?**  
   Amazon has unmatched brand trust and stored cards; copying high-familiarity UI onto a consideration purchase spikes customer anxiety.
8. **When should we use a Multi-Armed Bandit instead of an A/B test?**  
   Use Multi-Armed Bandits when the campaign duration is too short for fixed-sample tests and the goal is maximizing revenue rather than causal learning.
9. **How do you calculate the true financial contribution of CRO?**  
   Multiply incremental revenue per visitor by annual validated traffic, discounted by the program false discovery rate.
10. **If a test ends flat with no winner, was it a waste of time?**  
    Flat tests prevent expensive engineering rollouts of ineffective features, protecting the baseline and providing clear behavioral learning for the next iteration.

---

## Optimizely Developer QA Console Commands

`javascript
// 1. Check all active experiments and variation assignments
window.optimizely.get('state').getExperimentStates();

// 2. View current visitor ID and targeted audiences
window.optimizely.get('visitor');

// 3. Get variation mapping
window.optimizely.get('state').getVariationMap();

// 4. SPA manual activation on URL/route change
window.optimizely.push({
  type: 'activatePage',
  pageId: 'PAGE_ID_HERE'
});

// 5. Track custom conversion event
window.optimizely.push({
  type: 'event',
  eventName: 'form_completed_step1'
});
`

---

## Repository Structure

`
.
|-- README.md
|-- Rapid_Recall_CRO_and_Optimizely_Cheat_Sheet.md
|-- Rapid_Recall_CRO_and_Optimizely_Cheat_Sheet.pdf
|-- Rapid_Recall_CRO_and_Optimizely_Cheat_Sheet.docx
|-- Master_CRO_and_Optimizely_Experimentation_Cheat_Sheet.md
|-- Master_CRO_and_Optimizely_Experimentation_Cheat_Sheet.pdf
-- Master_CRO_and_Optimizely_Experimentation_Cheat_Sheet.docx
`

---

## License and Attribution

Author: Maurer Lajos (maurerlajos1@gmail.com)  
Framework references: Peep Laja (CXL / ResearchXL), Flint McGlaughlin (MECLABS), Andre Morys (7E / konversionsKRAFT), Chris Goward (WiderFunnel / LIFT), Ton Wesseling (Online Dialogue / ROAR).
