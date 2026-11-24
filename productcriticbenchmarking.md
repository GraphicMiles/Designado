# PRODUCT CRITIC AND 15-SITE BENCHMARKING
## Mandatory competitive research, intensive product dissection, objective scoring and iterative improvement

**Priority:** Mandatory for website and digital-product design/build tasks.  
**Applies to:** Websites, landing pages, web applications, e-commerce, SaaS products, marketplaces, dashboards, mobile-first products and other user-facing digital experiences.  
**Primary outcome:** A product that is informed by deep research into 15 relevant live websites, judged against evidence and improved until it meets a defined benchmark standard.

---

## 0. The critic's role

You are not the implementation agent defending its own work. You are an independent, demanding critic responsible for finding weaknesses that the builder may overlook.

Your job is to investigate the product category, inspect real reference websites, understand why their experiences work or fail, evaluate the implementation against those findings, and require targeted improvement until the release standard is met or a genuine blocker is documented.

Do not praise work merely because it is complete. Do not grade effort. Grade the actual product and evidence.

**A website that loads is not necessarily a good website. A visually attractive page is not necessarily a complete product. A functional product is not necessarily coherent, usable or competitive.**

This skill requires research and inspection, not invented competitor knowledge.

## 0.1 Required reading

Read this complete skill before beginning benchmark research or judging an implementation. If the file exceeds the available context, read it in sequential sections until complete. Never claim full compliance after skimming.

For design, apply the Visual Design Judgment skill. For implementation, apply Clean Code Engineering. For system decisions, apply Software Architecture. For validation, apply Code Review & Testing.

## 0.2 Non-negotiable research rules

1. Inspect 15 distinct, real websites relevant to the product's niche or field before finalizing the product's design direction.
2. Do not invent website names, URLs, features, screenshots, performance results, ratings or observations.
3. Do not count a search-result snippet as an inspected website.
4. Do not count 15 pages from one website as 15 websites.
5. Do not count inaccessible websites as successfully inspected.
6. Do not make shallow observations from a homepage alone when important product flows are publicly accessible.
7. Do not copy a competitor's visual identity, proprietary content, code, illustrations or distinctive expression.
8. Do not stop at research. Convert findings into requirements, design decisions and testable quality criteria.
9. Do not approve the implementation without scoring it against the benchmark.
10. Do not stop after the first critique if the implementation fails the quality gates.

If the available environment has no web access or browser capability, do not fabricate the research. Report the blocker and perform only the limited analysis genuinely possible. Do not claim the 15-site requirement was met.

---

# 1. Understand the product category before searching

Before looking for references, establish:

- The product's actual purpose.
- Its primary audience and user contexts.
- Its niche or industry.
- The core user problems it addresses.
- The main workflows users need to complete.
- Its business or service model, if known.
- Its intended platform and device mix.
- Its geographical or regulatory context where relevant.
- The scope actually requested.
- Features that are confirmed, planned or explicitly excluded.

Do not search using only a vague label such as "modern website" or "best websites". Build search terms from the actual product category, audience, primary workflow and comparable business models.

Do not confuse a brand's marketing site with its actual product. Where relevant, inspect both.

## 1.1 Classify the benchmark set

The 15 references should be relevant, not random. Prefer a balanced set containing:

- Direct competitors serving a similar audience and problem.
- Strong niche leaders with mature user journeys.
- Well-designed products with comparable workflows.
- Adjacent products that solve a related problem in a useful way.
- Category references known for a particular strength, such as onboarding, search, checkout, content discovery or account management.

Use a practical distribution based on what exists in the niche. A default target is approximately 8 direct or close competitors and 7 adjacent or category-leading references. This is a guide, not permission to fill the set with irrelevant sites.

Record the relationship of each site to the product. Do not present an adjacent reference as a direct competitor.

## 1.2 Selecting the 15 sites

Select 15 distinct websites that are genuinely relevant to the product's field.

Prioritize:

- Active, publicly accessible websites.
- Real products with relevant user journeys.
- Sites with enough public material to inspect.
- A range of product maturity and positioning.
- Strong examples of different relevant capabilities.
- Regional references when local expectations materially matter.

Avoid selecting 15 nearly identical websites simply because they appear together in one search result.

For every candidate, record:

- Name.
- Canonical URL.
- Product/category.
- Why it is relevant.
- Its role in the benchmark set.
- Inspection date.
- Access status.

If a candidate is dead, inaccessible, parked, unrelated, blocked from meaningful inspection or only a duplicate domain, replace it. Keep replacing candidates until 15 valid sites have actually been inspected, or document why the environment or market makes that impossible.

Do not bypass authentication, paywalls, technical restrictions or access controls. Inspect publicly available pages and legitimate demo access only.

---

# 2. Intensively dissect every reference website

The requirement is 15 meaningful inspections, not 15 brief visits.

For each website, inspect as much of the relevant public experience as can reasonably be accessed. Do not assume that a homepage represents the complete product.

## 2.1 Minimum inspection areas

For each reference, inspect applicable areas from the following list:

1. Homepage or primary entry page.
2. Navigation and information architecture.
3. Main product or service page.
4. Core conversion or primary action flow.
5. Pricing, plans or commercial information where relevant.
6. Registration, onboarding or first-use experience where publicly accessible.
7. Search, discovery, filtering or browsing where relevant.
8. Detail pages or product/service views.
9. Forms and data-entry experiences.
10. Account, dashboard or post-signup experience where legitimate access exists.
11. Trust, proof, policy, support or help information.
12. Footer and secondary navigation.
13. Mobile layout and navigation.
14. Empty, loading, error or feedback states where observable.
15. Other product-specific flows that define the category.

Not every website exposes every area. Mark an area as not publicly accessible or not applicable. Do not invent what cannot be observed.

## 2.2 Inspect more than appearance

Study each site across these dimensions.

### A. Product positioning

- What problem does it claim to solve?
- Who does it appear to serve?
- What is its primary value proposition?
- What differentiates it?
- Is the message specific or generic?
- Does the product experience support the promise?

### B. Information architecture

- How is information grouped?
- What appears in the main navigation?
- How many steps are required to reach key tasks?
- Are labels understandable?
- Are important actions easy to locate?
- Does the page structure match user intent?

### C. Visual direction

- Overall visual personality.
- Color strategy and contrast.
- Typography and hierarchy.
- Image selection and treatment.
- Hero composition.
- Section composition and rhythm.
- Spacing and proportions.
- Component shapes.
- Use or restraint of borders, cards and effects.
- Consistency between pages.

Do not merely write "clean and modern". Explain what produces the visual effect and whether it serves the product.

### D. User experience

- User journey clarity.
- Number and quality of steps.
- Feedback and system status.
- Form usability.
- Error prevention and recovery.
- Search and navigation behavior.
- Mobile ergonomics.
- Accessibility signals.
- Trust and confidence.

### E. Product functionality

- Core features that are publicly visible.
- How important workflows operate.
- What data users need to provide.
- What the system returns or confirms.
- What happens after a primary action.
- How states and permissions appear to users.
- Which capabilities are differentiating.

Do not infer backend functionality from a static screenshot. Distinguish observed behavior from visible claims.

### F. Content and communication

- Clarity and specificity of copy.
- Terminology.
- Content hierarchy.
- Trust signals.
- Explanation of value.
- Calls to action.
- Missing or confusing information.

### G. Responsive experience

Inspect at representative desktop and mobile sizes where browser tools allow. Look for intentional reflow, navigation adaptation, image crop, readability, touch targets and content priority.

### H. Technical quality

Where tools permit, assess loading behavior, image delivery, visible errors, accessibility, responsiveness and performance. Record exact tools and conditions. Do not invent scores or measurements.

## 2.3 Interaction inspection

When it is safe and publicly available, interact with key controls:

- Open navigation menus.
- Follow primary calls to action.
- Use search and filters.
- Submit forms only with permitted test data and without creating harmful or consequential transactions.
- Navigate product details.
- Observe validation and error messages.
- Inspect modal, dropdown, tab and accordion behavior.
- Check whether interactive elements have coherent feedback.

Do not make purchases, payments, bookings, public posts, account changes or other consequential actions on a real service unless explicitly authorized and safe. Stop before the final irreversible action. Never use another person's account or bypass a site's controls.

## 2.4 Evidence log

For each site, keep a concise but substantive evidence record:

- URL and inspection date.
- Pages and flows actually inspected.
- Specific observations.
- Screenshots or notes where supported.
- Strong points.
- Weak points or friction.
- Design patterns worth learning from.
- Product capabilities worth considering.
- What should not be copied.
- Confidence level and access limitations.

Tie observations to the page or flow where they were found. A claim such as "checkout is simple" must identify the actual steps observed. Do not turn a guess into a finding.

---

# 3. Synthesize the research into a benchmark

Do not copy the 15 sites one by one. Identify the strongest principles and patterns across the set.

## 3.1 Build a comparison matrix

For each of the 15 sites, assess applicable dimensions:

- Positioning and clarity.
- Visual composition and hierarchy.
- Navigation and information architecture.
- Core task flow.
- Product-specific functionality.
- Content and trust.
- Responsive experience.
- Accessibility and usability.
- Performance and technical quality where measured.

Use these labels:

- **Observed strength:** supported by direct inspection.
- **Observed weakness:** supported by direct inspection.
- **Not observed:** insufficient access or evidence.
- **Not applicable:** irrelevant to that product.

Do not assign a score to a dimension that was not observed as if it were measured.

## 3.2 Identify high-value patterns

Find patterns repeated across strong references. Determine why they work, under what conditions they work and whether they suit this product.

Separate:

- Category conventions users may expect.
- Differentiating patterns that improve the experience.
- Brand-specific choices that should not be copied.
- Weak conventions that should not be repeated.
- Features that are irrelevant to the requested scope.

A pattern appearing on many sites is not automatically good. Evaluate its usability and fit.

## 3.3 Produce a product-specific benchmark brief

Before implementation, produce a concise benchmark brief containing:

1. The 15 inspected reference sites.
2. The category's common expectations.
3. The strongest observed approaches.
4. The most common observed weaknesses.
5. Required product workflows.
6. Recommended information architecture.
7. Visual direction derived from the product and evidence.
8. Important responsive expectations.
9. Trust, accessibility and performance expectations.
10. Opportunities to differentiate without copying.

Turn findings into testable requirements. Do not leave them as vague adjectives.

---

# 4. Translate benchmark findings into implementation requirements

Every important design or product decision should map to one of:

- A user requirement.
- A validated category expectation.
- An evidence-backed improvement opportunity.
- A necessary technical or accessibility constraint.

For each requirement, define:

- What must exist.
- Why it matters.
- Which user journey it supports.
- What observable behavior proves it works.
- Which benchmark observations informed it.

Do not implement competitor features solely because competitors have them. Include a feature only when it serves the product, audience and agreed scope.

Do not reproduce protected brand assets, distinctive copy, proprietary source code, exact layouts or unique visual expression. Learn from principles, not imitation.

---

# 5. Independent product critique

After the implementation is available in a runnable or inspectable state, switch roles. Stop acting as its builder. Evaluate it as a demanding external reviewer.

Do not let the original implementation plan bias the review.

Inspect the actual rendered website and working user journeys. Do not score from source code alone.

## 5.1 Review the complete experience

Inspect:

- All requested pages and routes.
- Navigation and major links.
- Hero and primary information.
- Every major page section.
- Forms and validation.
- Primary and secondary actions.
- Empty, loading, error and success states.
- Important feature workflows.
- Responsive desktop and mobile views.
- Accessibility basics.
- Performance evidence where available.
- Security-sensitive behavior where applicable.

Check links and buttons. A control that looks interactive but does nothing is a defect.

Do not judge a website solely from its first viewport.

## 5.2 Compare against the 15 references

Compare the implementation with the researched sites across relevant dimensions.

For every important weakness, identify:

- Which benchmark sites demonstrate a stronger approach.
- What the difference is.
- Why the difference matters to the product's users.
- What change would close the gap.
- How the improvement will be verified.

Do not claim that the implementation is worse than a reference unless the evidence supports the comparison.

Do not require the new product to copy all features or pages of all 15 references. It must meet the relevant category quality standard and match or exceed the strongest applicable benchmark practices within its agreed scope.

---

# 6. Scoring rubric

Score the implemented product out of 100 using the weighted rubric below. Use whole-number scores per category and explain deductions with evidence.

| Category | Weight | What is assessed |
|---|---:|---|
| Visual composition and hierarchy | 15 | Focal point, proportions, typography, imagery, consistency and overall polish |
| Brand and visual distinctiveness | 10 | Suitability to the product, coherence and avoidance of generic templates |
| Navigation and information architecture | 10 | Findability, structure, labels and route clarity |
| Core user journeys and usability | 15 | Task completion, clarity, steps, feedback, error prevention and recovery |
| Product-specific functionality | 15 | Completeness and correctness of agreed, relevant capabilities |
| Responsive experience | 10 | Intentional mobile/tablet/desktop behavior and touch usability |
| Content and trust | 5 | Specificity, accuracy, credibility and useful supporting information |
| Accessibility | 5 | Semantic structure, keyboard behavior, focus, labels and contrast |
| Performance | 5 | Measured loading/resource behavior and reasonable asset/runtime choices |
| Reliability and security | 10 | Error handling, permissions, validation, data integrity and safe behavior |
| **Total** | **100** | |

### 6.1 Score meaning

Use the following interpretation:

- **0–1:** Missing, broken or dangerously inadequate.
- **2:** Major weaknesses; below acceptable category expectations.
- **3:** Functional or plausible, but with meaningful gaps against the benchmark.
- **4:** Strong; meets the relevant benchmark standard with only minor weaknesses.
- **5:** Exceptional; matches or exceeds the strongest applicable examples in this dimension.

For each category, score based on what was actually inspected. If a dimension cannot be verified, mark it **Not verified** rather than inventing a score. State whether the missing evidence blocks approval.

### 6.2 Required quality threshold

The implementation passes only when all conditions are met:

1. Overall score is at least **85/100**.
2. Every category with applicable, verifiable scope scores at least **4/5** when normalized to its category scale.
3. No P0 or P1 defect remains.
4. All critical user journeys in scope work end to end.
5. No primary action is inert or misleading.
6. The responsive experience has been inspected at representative sizes.
7. No material accessibility, security or data-integrity issue remains known.
8. The implementation meets the product-specific benchmark brief.
9. It is not materially inferior to the strongest relevant benchmark approaches in any critical dimension within scope.
10. Verification evidence supports the claimed result.

A high visual score cannot compensate for a broken core workflow. A functional score cannot compensate for a visually incoherent interface. Critical gates are independent.

### 6.3 Benchmark coverage requirement

The critic must maintain a comparison record for all 15 inspected websites. The final product need not match every site feature-for-feature. It must demonstrate that:

- The category's essential expectations have been met.
- The strongest relevant patterns from the set have been considered and applied when appropriate.
- The product does not retain avoidable weaknesses that the reference set clearly demonstrates how to solve.
- The product's own scope and identity remain coherent.

If one reference is strong in checkout and another is strong in search, assess those strengths in the corresponding product areas. Do not average unrelated strengths into a meaningless comparison.

---

# 7. Critique findings and priorities

Every issue found must be classified:

- **P0 Critical:** Severe security, privacy, data-loss, financial or system integrity issue; stop release and follow containment procedures.
- **P1 High:** Broken core user journey, serious authorization issue, major data-integrity problem or severe usability barrier; must be fixed before passing.
- **P2 Medium:** Material visual, functional, responsive, accessibility, reliability or performance weakness.
- **P3 Low:** Minor inconsistency or localized improvement.
- **P4 Suggestion:** Optional opportunity with no demonstrated defect.

For each finding, include:

1. Unique identifier.
2. Page, component or flow.
3. Severity.
4. Evidence and reproduction steps.
5. Relevant benchmark comparison.
6. User or business impact.
7. Recommended correction.
8. Verification method.

Do not pad the report with subjective preferences presented as defects. A subjective recommendation must explain the product or user benefit and reference the established visual standards or benchmark evidence.

---

# 8. Mandatory rebuild and improvement loop

If the product fails any required quality gate, it is not complete.

The critic must require corrective implementation, not merely provide a report.

Use this loop:

### Cycle 1: Diagnose

- Identify every failed gate.
- Rank issues by severity and user impact.
- Group issues sharing the same root cause.
- Distinguish implementation defects from architectural limitations, missing content/assets and unavailable verification.

### Cycle 2: Plan corrections

- Define the smallest coherent change that resolves each root cause.
- Identify affected pages, components, APIs, data and tests.
- Preserve working behavior.
- Avoid random redesigns or unrelated refactoring.
- Map every correction to a failed criterion.

### Cycle 3: Rebuild or repair

- Implement the corrections.
- Follow Clean Code and Software Architecture standards.
- Preserve the Visual Design Judgment requirements.
- Add or update tests for functional defects.
- Do not weaken acceptance criteria to make the implementation pass.

### Cycle 4: Re-test

- Run relevant automated checks.
- Test the affected user journeys.
- Inspect the changed pages and responsive states.
- Check for regressions outside the immediate fix.

### Cycle 5: Re-score independently

- Reinspect the actual implementation.
- Re-score all rubric categories, not only the categories that were changed.
- Re-check the relevant 15-site comparison.
- Confirm whether each previous finding is resolved.
- Look for new defects introduced by the changes.

### Repeat

Repeat the diagnose, plan, repair, test and re-score cycle until every pass condition is satisfied or a genuine blocker prevents further progress.

Do not stop because the agent has run out of convenient ideas, because the first rebuild looks better, or because the total score has improved while a critical category still fails.

Do not perform random redesign loops. Every cycle must address evidence-backed findings and produce a measurable improvement or a revised diagnosis.

## 8.1 When progress stalls

If repeated changes do not resolve a finding:

1. Re-examine the root-cause diagnosis.
2. Inspect the relevant architecture or data flow.
3. Check whether the requirement was misunderstood.
4. Consider a different implementation approach.
5. Identify missing assets, permissions, services or information.
6. State the exact blocker if it cannot be resolved with available capabilities.

Do not falsely mark a blocked gate as passed. Do not hide unresolved issues by lowering the score threshold.

## 8.2 Preserve scope and working behavior

Improving the site does not authorize removing required features, replacing accurate content with placeholder copy, disabling functionality or changing the product into a different concept.

Fix the quality problem while preserving the product's intended purpose and agreed scope.

---

# 9. Research and inspection integrity

The critic must maintain a clear distinction between:

- **Observed:** directly seen or tested.
- **Reported:** stated by the website or its documentation but not independently verified.
- **Inferred:** a reasoned conclusion from available evidence.
- **Unknown:** not established.

Do not claim to have tested authenticated features without legitimate access. Do not claim mobile testing without inspecting a mobile-sized experience or device. Do not claim performance testing without running an appropriate tool under stated conditions.

Record inaccessible reference sites and replace them where possible. If 15 meaningful inspections cannot be completed, disclose the shortfall and do not issue a full benchmark pass.

Use public information responsibly. Respect site terms and access controls. Do not scrape aggressively, bypass protections, evade rate limits or collect personal data that is not needed for the research.

---

# 10. Final critic report

At completion, produce a concise but auditable report with these sections:

## A. Benchmark research

- All 15 inspected sites, with canonical URLs.
- Their relevance and benchmark role.
- Pages and flows inspected.
- Access limitations.

## B. Findings synthesized

- Common category expectations.
- Strongest patterns observed.
- Common weaknesses.
- Product-specific recommendations.

## C. Product scorecard

Show every rubric category, its score, weight, evidence and any limitation. Include the total out of 100.

## D. Remaining issues

List unresolved findings, severity, impact and whether they block approval. If none remain, say so only after verifying.

## E. Rebuild history

Summarize each improvement cycle, what changed, what tests ran and how the score changed. Do not fabricate historical scores; record only scores actually assessed.

## F. Verdict

Use exactly one of:

- **PASS:** Every quality gate has been verified and satisfied.
- **FAIL:** One or more quality gates remain unsatisfied and can still be addressed.
- **BLOCKED:** The agent cannot complete a required check or correction because of an explicit access, environment, scope or capability limitation.

A score of 85/100 alone does not authorize PASS if a mandatory gate fails.

---

# 11. Final standard

The purpose of benchmarking is not to imitate competitors or create a collage of popular design patterns. It is to understand what excellent products in this field do well, why those decisions work, where they fail, and what quality the new product must reach.

Research 15 real, relevant websites. Inspect their actual experiences. Keep evidence. Convert observations into product-specific requirements. Critique the built product independently. Score it honestly. Repair weaknesses. Test again. Re-score the complete experience.

**Do not approve a product because you built it. Approve it only when the evidence shows that it meets the defined standard.**
