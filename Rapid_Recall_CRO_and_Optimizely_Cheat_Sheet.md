# Rapid Recall CRO & Optimizely Interview Cheat Sheet

A concise second-screen reference guide. Built with keywords, core definitions, and punchy explanations designed for rapid recall during technical interviews.

---

## 1. Executive Soundbites & Philosophy

* **Conversion Rate Optimization (CRO):** A structured risk-mitigation and revenue-expansion engine. It replaces subjective executive opinions with empirical customer evidence.
* **The Core Problem:** Human judgment fails between 70% and 80% of the time when predicting user behavior.
* **The 4-Act Case Walkthrough:**
  * 1. Diagnosis: Highlight broken ad scent and cognitive friction above the fold.
  * 2. Hidden Goldmine: Uncover high-value proof and pricing buried deep in the site.
  * 3. Architectural Solution: Wireframes with single-goal navigation and progressive disclosure.
  * 4. Validation: Statistically powered A/B testing with guardrail metrics.

---

## 2. Peep Laja's ResearchXL: The 6 Research Pillars

* **Technical Analysis:** Identify browser and device bugs. Look for conversion drops between adjacent browser versions or broken tablet layouts. Target interactive page load under 3.0 seconds.
* **Heuristic Analysis:** Expert walkthrough assessing Relevance, Clarity, Friction, and Distraction.
* **Digital Analytics (GA4):** Verify tracking integrity and detect funnel leaks across traffic segments and device categories.
* **Mouse Tracking:** Scroll maps to spot false bottoms, click maps to catch unlinked elements, and session replays for form drop-offs. Hover maps do not equal eye gaze.
* **Qualitative VoC (Voice of Customer):** Post-purchase email surveys sent within 48 hours to capture buying triggers and initial hesitations. On-site polls capture exit objections.
* **User Testing:** 5 to 7 real users performing realistic tasks to expose usability roadblocks.
* **The 5 Action Buckets:**
  * 1. Test: Meaningful behavioral changes that require validation.
  * 2. Instrument: Missing data or unconfigured analytics events.
  * 3. Hypothesize: Areas needing deeper discovery research.
  * 4. Just Do It: Obvious bugs or typo fixes that do not require testing.
  * 5. Investigate: Anomalies requiring technical or operational review.

---

## 3. Conversion Heuristics & Neuromarketing

* **MECLABS Formula:** C = 4m + 3v + 2(i - f) - 2a. Conversion probability equals 4 times user motivation, plus 3 times value proposition clarity, plus 2 times incentive minus friction, minus 2 times customer anxiety. Motivation is the most powerful variable.
* **Friction vs. Anxiety:** Friction is physical or cognitive effort (lengthy forms, clunky UI). Anxiety is psychological fear (hidden charges, credit card safety, privacy concerns).
* **Andre Morys 7E Framework:**
  * 1. Relevance: Answers visitor intent immediately.
  * 2. Trust: Verifiable social proof and security signals.
  * 3. Orientation: Visual hierarchy and directional guidance.
  * 4. Stimulation: Clear emotional and rational value drivers.
  * 5. Security: Guarantees, clear terms, and data safety.
  * 6. Convenience: Seamless checkout and form usability.
  * 7. Confirmation: Reassurance on the thank-you page to prevent buyer remorse.
* **LIFT Model (Chris Goward):** Value Proposition is the foundation. It is propelled by Relevance and Clarity, stimulated by Urgency, and dragged down by Anxiety and Distraction.
* **Dual-Process Theory (Daniel Kahneman):** System 1 is fast, emotional, and intuitive. System 2 is slow, analytical, and effortful. Great landing pages cater to System 1 within 50 milliseconds.
* **BJ Fogg Behavior Model:** B = MAP. Behavior requires Motivation, Ability, and a Prompt converging at the same moment.
* **Endowed Progress Effect:** Providing artificial progress toward a goal increases completion rates (for example, Step 1 already marked complete on a multi-step form).

---

## 4. Landing Page Anatomy & Wireframe Rules

* **The 7 Above-the-Fold Essentials (50 Millisecond Impression):**
  * 1. Trust Strip: Top banner displaying ratings or member count.
  * 2. Single-Goal Header: Logo, phone number, and primary action only. No distracting menu links.
  * 3. Clear Headline: Identifies the target audience and core benefit.
  * 4. Benefit Subheadline: Clarifies the offering and mentions starting pricing.
  * 5. Primary CTA: Action verb plus specific benefit (for example, Calculate My Price).
  * 6. Key Value Icons: 3 to 4 distinct icons highlighting core guarantees.
  * 7. Visual Hero Proof: Authentic product or service imagery showing the actual outcome.
* **The ATIDFA Page Flow:** Attention (Hero), Trust (Logos and Reviews), Interest (Feature benefits), Desire (Comparison tables), FUDs (FAQ accordion for fears and doubts), Action (Sticky mobile CTA and closing banner).
* **Dual-Path Navigation:** High-intent visitors take the direct pricing shortcut. Low-intent visitors take the educational path down the page.
* **Form Optimization:** 2-step progressive disclosure. Collect basic non-sensitive inputs on step 1 (Zip code, property type). Collect contact details on step 2 after psychological commitment.

---

## 5. Strategy, ROAR & Prioritization

* **Ton Wesseling's ROAR Model:**
  * Risk Phase (Under 1,000 conversions per month): Too little data to run A/B tests. Focus on user testing, surveys, and direct site improvements.
  * Optimization Phase (1,000 to 10,000 conversions per month): Run 10 to 30 strategic tests per year on high-traffic steps.
  * Automation & Re-think Phase (Over 10,000 conversions per month): Run high-velocity tests and major page overhauls.
* **Ton Wesseling's 6V Research Canvas:** Value, Versus, View, Voice, Verified, Validated.
* **CXL PXL Prioritization Matrix:** 13 objective binary questions scoring page location, data support, expected impact, and development ease. Prevents executive bias.
* **PIPE Framework:** Problem, Impact, Potential, Ease.

---

## 6. Optimizely Web & Full-Stack Architecture

* **Optimizely Web vs. Feature Experimentation:** Optimizely Web runs client-side JavaScript in the browser to modify the DOM. Feature Experimentation runs server-side via SDKs using feature flags and variables.
* **The Flicker Problem (FOOC):** Flash of Original Content occurs when the original page renders before the Optimizely script applies variations.
* **Synchronous Snippet:** The standard solution. Placed at the very top of the `<head>` tag before tag managers or analytics.
* **Page-Hiding Snippet:** A temporary CSS safeguard that hides page elements until Optimizely loads, with a 1,000 millisecond timeout to prevent blank screens.
* **Single Page Application (SPA) Activation:** When the URL changes without a page refresh, fire manual activation via `window.optimizely.push({ type: "activatePage", pageId: "12345" })`.
* **Stats Engine (mSPRT):** Mixture Sequential Probability Ratio Test. Replaces classical fixed-horizon testing. It continuously controls False Discovery Rate and provides always-valid p-values, solving the peeking problem.
* **Multi-Armed Bandit (MAB):** Uses Thompson Sampling to dynamically shift traffic toward winning variations. Use for short-term events (holiday sales) where maximizing immediate revenue matters more than statistical learning.
* **Optimizely Console Commands:**
  * Check active tests: `window.optimizely.get("state").getExperimentStates()`
  * View visitor ID and segments: `window.optimizely.get("visitor")`
  * Force variation in URL: `?optimizely_x=EXPERIMENT_ID&optimizely_token=VARIATION_ID`

---

## 7. Statistics & Quality Checks

* **Sample Size Rule:** Inverse-square relationship. If you cut the Minimum Detectable Effect (MDE) in half, you need 4 times more traffic.
* **Statistical Standard:** 80% statistical power (1 - beta) and 95% confidence level (alpha = 0.05).
* **Sample Ratio Mismatch (SRM):** When actual visitor split deviates from intended ratio (for example, expecting 50/50 but getting 52/48 on 10,000 visits). Tested via Chi-Square goodness-of-fit. If p is less than 0.001, the test is invalid due to tracking errors or redirects.
* **False Discovery Rate (Ioannidis Math):** If only 20% of your hypotheses are truly effective, a 95% confidence test still yields an effective 16.7% false positive rate across your program.
* **Test Runtime Rules:** Always run tests for at least 2 full business cycles (14 days minimum) and never longer than 4 weeks to avoid cookie churn.

---

## 8. Frontend Technical Tokens

* **Form Autofill Tokens:** Always use official HTML5 attributes: `autocomplete="given-name"`, `family-name`, `email`, `tel`, `postal-code`.
* **Mobile Keypads:** Always set `inputmode="tel"` for phone numbers and `inputmode="numeric"` with `pattern="[0-9]*"` for zip codes.

---

## 9. Top 10 Pushbacks: One-Sentence Answers

* **Q1: Why not put the lead form above the fold?**  
  *Answer:* Asking for sensitive personal details before visitors understand the product value creates high anxiety and reduces conversion rates.
* **Q2: If we show pricing upfront, won't lead volume drop?**  
  *Answer:* Concealing pricing attracts low-intent leads that waste sales time, whereas transparent price anchoring filters for qualified buyers and increases revenue per visitor.
* **Q3: Can we test 8 changes at once using a Multivariate Test (MVT)?**  
  *Answer:* An MVT requires multiplicative traffic across all factor combinations; running a high-impact radical A/B redesign is significantly faster and statistically safer.
* **Q4: The test is significant on Day 3. Can we stop it?**  
  *Answer:* Stopping early causes severe false-positive bias due to day-of-week seasonality; every test must run for at least two full business cycles.
* **Q5: How does Optimizely's Stats Engine differ from Google Optimize or VWO?**  
  *Answer:* Optimizely uses mSPRT sequential testing to provide always-valid p-values that allow continuous monitoring without peeking penalties.
* **Q6: What do you do if you detect an SRM?**  
  *Answer:* An SRM completely invalidates the statistical test; I immediately halt the test and debug redirect latencies, bot filters, and tag firing order.
* **Q7: An executive wants to copy Amazon's 1-click checkout. What do you say?**  
  *Answer:* Amazon has trillions of saved credit cards and unmatched trust; copying high-familiarity UI onto a consideration purchase spikes customer anxiety.
* **Q8: When should we use a Multi-Armed Bandit instead of an A/B test?**  
  *Answer:* Use Multi-Armed Bandits when the campaign duration is too short for fixed-sample tests and our goal is maximizing revenue rather than causal learning.
* **Q9: How do you calculate the true financial contribution of CRO?**  
  *Answer:* Multiply incremental revenue per visitor by annual validated traffic, discounted by our program false discovery rate.
* **Q10: If a test ends flat with no winner, was it a waste of time?**  
  *Answer:* Flat tests prevent expensive engineering rollouts of ineffective features, protecting the baseline and providing clear behavioral learning for the next iteration.

---

## 10. Quick Reference Tables

### A. Core Statistical Benchmarks

| Metric | Target Standard | Interview Explanation |
| :--- | :--- | :--- |
| **Statistical Power (1 - beta)** | 80% | Probability of detecting a true effect when one actually exists. |
| **Significance Level (alpha)** | 95% (p < 0.05) | 5% risk of a false positive on a single test. |
| **Minimum Runtime** | 14 Days (2 cycles) | Captures day-of-week purchasing patterns and eliminates novelty bias. |
| **Maximum Runtime** | 28 to 30 Days | Avoids cookie deletion distortion and sample pollution. |
| **Sample Ratio Mismatch** | p < 0.001 | Chi-Square test indicating broken sample allocation. |

### B. Optimizely Developer Quick Commands

| Purpose | Console Command |
| :--- | :--- |
| **List Active Experiments** | `window.optimizely.get("state").getExperimentStates()` |
| **Inspect Visitor Profile** | `window.optimizely.get("visitor")` |
| **Get Active Variation Map** | `window.optimizely.get("state").getVariationMap()` |
| **Manual Page Activation (SPA)** | `window.optimizely.push({ type: "activatePage", pageId: "PAGE_ID" })` |
| **Track Custom Event** | `window.optimizely.push({ type: "event", eventName: "EVENT_NAME" })` |
| **Force Variation via URL** | `?optimizely_x=EXPERIMENT_ID&optimizely_token=VARIATION_ID` |
