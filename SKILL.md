---
name: ai-writing-detector
description: "Identify and fix AI-generated writing patterns in text. Detects verbose structures, promotional language, superficial analyses, and AI vocabulary. Provides specific improvements with before/after examples. Use when you need to clean up text that sounds robotic, overly promotional, or statistically generic."
---

# AI Writing Detector & Improver

## Overview

This skill identifies and fixes common AI-generated writing patterns that make text sound robotic, verbose, or statistically generic. It focuses on practical improvements rather than mere detection.

## Core Principle

AI writing tends to **regress to the mean** — smoothing specific facts into generic statements that could apply to many topics. The result: less specific, more exaggerated prose that sounds impressive but says little.

## Pattern Categories

### 1. Undue Emphasis on Significance & Legacy

**What to detect:**
- Phrases: "stands as a testament," "serves as a reminder," "underscores the importance," "reflects broader trends," "symbolizing its enduring legacy"
- Pattern: Connecting mundane topics to grand narratives unnecessarily
- Example: "This etymology highlights the enduring legacy of the community's resistance"

**How to fix:**
- Remove the grandiose framing
- State the fact directly
- Let the significance emerge from specifics, not assertions

**Before:** "The founding represented a significant shift toward regional independence, enabling Catalonia to develop a statistical system tailored to its unique socio-economic context."

**After:** "Catalonia gained control over its own statistics, allowing data collection specific to the region."

---

### 2. Superficial Analyses

**What to detect:**
- Present participle phrases attached to ends of sentences: "highlighting...", "underscoring...", "emphasizing...", "contributing to..."
- Vague significance claims without concrete details
- Pattern: Analysis that sounds insightful but lacks specifics

**How to fix:**
- Delete the superficial analysis entirely
- OR replace with concrete facts
- OR move analysis to its own sentence with specific examples

**Before:** "As of the April 2008 census, the population stood at approximately 56,998 inhabitants, creating a lively community within its borders."

**After:** "The April 2008 census recorded 56,998 inhabitants."

---

### 3. Promotional Language

**What to detect:**
- Words: "boasts a," "vibrant," "rich," "profound," "showcasing," "exemplifies," "nestled in the heart of"
- Travel guide tone for non-travel topics
- Excessive positivity without substance
- Pattern: Sound like marketing copy for Wikipedia

**How to fix:**
- Neutralize the tone
- Replace emotive adjectives with specific facts
- Cut marketing language entirely

**Before:** "Nestled within the breathtaking region of Gonder, Alamata Raya Kobo stands as a vibrant town with a rich cultural heritage."

**After:** "Alamata Raya Kobo is a town in the Gonder region of Ethiopia."

---

### 4. AI Vocabulary Overload

**What to detect:**
High-density clusters of AI-favored words:

**2023-2024 (GPT-4 era):**
- Additionally, boasts, bolstered, crucial, delve, emphasizing, enduring, garner, intricate, interplay, key, landscape, meticulous, pivotal, underscore, tapestry, testament, valuable, vibrant

**2024-2025 (GPT-4o era):**
- align with, bolstered, crucial, emphasizing, enhance, enduring, fostering, highlighting, pivotal, showcasing, underscore, vibrant

**2025+ (GPT-5 era):**
- emphasizing, enhance, highlighting, showcasing

**How to fix:**
- Replace with simpler alternatives: "use" not "utilize," "shows" not "showcases"
- Reduce frequency — max 1-2 per paragraph
- Check if the word adds meaning or just length

**Before:** "This pivotal moment underscores the crucial role that meticulous planning plays in fostering sustainable development and enhancing the vibrant tapestry of community life."

**After:** "This shows how planning affects community development."

---

### 5. Negative Parallelisms

**What to detect:**
- "Not just X, but also Y"
- "Not X, but Y"
- "It's not X, it's Y"
- Pattern: Artificially creating contrast where none exists

**How to fix:**
- Remove the parallel structure
- State the point directly
- OR use simple conjunctions

**Before:** "Self-Portrait constitutes not only a work of self-representation, but a visual document of her obsessions."

**After:** "Self-Portrait is both a self-representation and a record of the artist's obsessions."

---

### 6. Avoidance of Basic Copulatives

**What to detect:**
- Substituting "is/are" with "serves as," "stands as," "marks," "represents"
- Using "features," "offers," "boasts" instead of "has"

**How to fix:**
- Use "is," "are," "has" directly
- Only vary when it adds genuine meaning

**Before:** "Gallery 825 serves as LAAA's exhibition space for contemporary art. The gallery features four separate spaces."

**After:** "Gallery 825 is LAAA's contemporary art exhibition space. It has four galleries."

---

### 7. Rule of Three Overuse

**What to detect:**
- Adjective, adjective, adjective
- Short phrase, short phrase, and short phrase
- Pattern: Three-item lists used to appear comprehensive

**How to fix:**
- Keep only if all three items add unique value
- Reduce to one or two items when redundant
- Break into separate sentences if complex

**Before:** "The conference brings together global SEO professionals, marketing experts, and growth hackers to discuss trends, share insights, and build connections."

**After:** "The conference connects SEO and marketing professionals."

---

### 8. Elegant Variation

**What to detect:**
- Avoiding word repetition by using synonyms
- Pattern: "The protagonist... the main character... the key player... the lead figure"

**How to fix:**
- Use the same term consistently
- Reader clarity > stylistic variation

**Before:** "Yankilevsky joined other non-conformist artists. The painters faced obstacles expressing their creativity. The artists found a community of like-minded creators."

**After:** "Yankilevsky joined other non-conformist artists who faced obstacles to free expression."

---

### 9. Vague Attributions

**What to detect:**
- "Experts argue," "Observers have cited," "Industry reports show"
- "Several sources," "Some critics"
- Pattern: Claiming broad support without specific attribution

**How to fix:**
- Cite specific sources
- OR remove the attribution wrapper
- OR attribute to the actual source you have

**Before:** "Due to its unique characteristics, the river is of interest to researchers and conservationists."

**After:** "Researchers from the Chinese Academy of Sciences study the river's ecosystem."

---

### 10. Knowledge-Cutoff Disclaimers

**What to detect:**
- "As of my last knowledge update..."
- "While specific details are limited..."
- "Not widely documented..."
- "Keeps personal details private"

**How to fix:**
- Remove the disclaimer
- State only what's known
- OR delete the entire speculative section

**Before:** "While specific details about Kumarapediya's history are not extensively documented in readily available sources..."

**After:** "Kumarapediya's early history has not been studied."

---

## Detection Workflow

### Step 1: Scan for AI Vocabulary

Count these words per paragraph:
- Additionally, crucial, delve, emphasizing, enhance, fostering, highlighting, intricate, key, landscape, pivotal, showcasing, underscore, tapestry, testament, vibrant

**Threshold:** 3+ per paragraph = likely AI

### Step 2: Check Sentence Openings

Look for:
- Sentences starting with "Additionally," "Moreover," "Furthermore"
- Present participle phrases at sentence ends (", highlighting...")
- Grandiose significance claims in first/last sentences of paragraphs

### Step 3: Assess Specificity

For each paragraph, ask:
- Could this apply to 10 different topics? (AI tendency)
- Does it contain unique, specific facts? (human tendency)
- Are there concrete numbers, names, dates? (specificity check)

### Step 4: Evaluate Tone

Check for:
- Promotional positivity ("vibrant," "rich," "profound")
- Travel guide language ("nestled," "breathtaking")
- Marketing copy style ("boasts," "features," "showcases")

### Step 5: Identify Structural Patterns

- Negative parallelisms ("Not just X, but Y")
- Rule of three overuse
- Elegant variation
- Avoidance of "is/are"

---

## Improvement Workflow

### Step 1: Remove Verbal Filler

Delete:
- Superficial analyses (present participle phrases at sentence ends)
- Grandiose significance claims
- Knowledge-cutoff disclaimers
- Vague attributions

### Step 2: Replace AI Vocabulary

Common replacements:
- "showcase" → "show" or "display"
- "underscore" → "show" or "demonstrate"
- "pivotal" → "important" (or delete)
- "crucial" → "important" (or delete)
- "delve" → "examine" or "study"
- "tapestry" → "mix" or "combination" (or delete metaphor)
- "testament" → "evidence" or "sign"
- "vibrant" → delete or specify

### Step 3: Neutralize Tone

- Replace promotional adjectives with neutral terms
- Remove travel guide language
- Cut excessive positivity

### Step 4: Restore Specificity

- Add concrete facts, numbers, names, dates
- Replace generic claims with specific examples
- Ensure each paragraph contains unique information

### Step 5: Simplify Structure

- Use "is/are" and "has" directly
- Reduce parallel structures
- Cut rule-of-three lists to essentials
- Use consistent terminology (no elegant variation)

---

## Output Format

### Detection Report

```markdown
## AI Writing Detection Report

**Overall Score:** [Low/Medium/High likelihood]

### Patterns Detected

**Category:** [Pattern Name]
- **Location:** [Quote from text]
- **Issue:** [Why it's problematic]
- **Fix:** [Specific improvement]

**AI Vocabulary Count:**
- Paragraph 1: X occurrences
- Paragraph 2: Y occurrences
- Threshold exceeded: Yes/No

**Specificity Score:** [1-5]
- Concrete facts present: [List]
- Generic claims: [List]

**Tone Assessment:** [Neutral/Promotional/Mixed]
- Promotional language: [Examples]
- Travel guide style: [Examples]
```

### Improved Version

Provide a fully rewritten version with:
- All AI patterns removed
- Specificity restored
- Neutral tone
- Concrete facts prioritized

---

## Quality Checklist

- [ ] AI vocabulary reduced to 1-2 per paragraph max
- [ ] No superficial analyses (no ", highlighting..." at sentence ends)
- [ ] No grandiose significance claims
- [ ] No promotional language ("vibrant," "rich," "boasts")
- [ ] No vague attributions ("experts argue")
- [ ] No negative parallelisms ("not just X, but Y")
- [ ] Basic copulatives used ("is/are" not "serves as")
- [ ] Rule of three reduced to essentials
- [ ] Consistent terminology (no elegant variation)
- [ ] Concrete facts, numbers, names, dates present
- [ ] Neutral, encyclopedic tone

---

## Common Mistakes to Avoid

❌ **Overcorrecting** — Removing all adjectives makes text dry
✅ **Selective improvement** — Keep specific adjectives, cut generic ones

❌ **Losing meaning** — Simplifying so much that information is lost
✅ **Preserving content** — Keep facts, cut fluff

❌ **False positives** — Flagging all formal writing as AI
✅ **Context awareness** — Some academic/formal writing legitimately uses these patterns

❌ **Mechanical fixes** — Find-replace without considering flow
✅ **Natural improvements** — Rewrite for clarity, not just shorter words
