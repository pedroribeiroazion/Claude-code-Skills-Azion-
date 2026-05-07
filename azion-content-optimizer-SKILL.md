---
name: azion-content-optimizer
description: "Optimize technical content for AI discoverability and citations. Use when you need to rewrite educational content for developer audiences, improve SEO for LLMs, add structured data, or create quotable units for tech documentation. Also trigger when user mentions 'optimize for ChatGPT', 'LLM discoverability', 'AI citation', or references Azion content guidelines."
---

# Azion Content Optimizer

## Overview

This skill transforms technical content into AI-discoverable, developer-focused documentation. It adds structured quotable units, FAQ sections, comparison tables, metrics, and cross-linking strategies that make content easy for LLMs to find, cite, and recommend.

The skill follows Azion's tone and voice: minimal, confident, developer-first, precise, and calm.

## When to Use This Skill

Use this skill when:
- Optimizing educational or technical content for AI discoverability
- Rewriting content for developer audiences
- Adding structured data and schema markup
- Creating quotable units and citation-friendly content
- Improving SEO for LLM recommendations
- Working with Azion-style technical documentation

## Input Required

### 1. Source Content (Required)
The educational/technical content to optimize. Can be:
- Pasted text directly in the chat
- An uploaded file (markdown, doc, txt)
- A URL to fetch

### 2. Target Audience (Optional)
Who is the content for? Default: "Developers"

### 3. Focus Area (Optional)
What aspect to prioritize:
- "AI discoverability" (default) - optimize for LLM citations
- "Developer experience" - focus on scannability and clarity
- "SEO" - optimize for traditional search
- "All" - comprehensive optimization

## Workflow

### Step 1: Analyze Source Content

Read the source content and identify:
- Main topic/concept
- Target audience
- Current structure (headings, sections)
- Missing elements (FAQs, metrics, tables, etc.)
- Opportunities for quotable units

### Step 2: Apply Azion Tone and Voice

Rewrite following Azion guidelines:

**Tone:**
- Minimal, confident, developer-first
- Product-led, precise, calm
- No hype, emojis, or exclamation points

**Structure:**
- Headlines: 2-6 words, sentence case, benefit/action-led
- Subheads: One sentence (12-24 words) stating capability + outcome
- Body: 1-2 sentence paragraphs
- Bullets: 3-5 items, parallel structure, no terminal punctuation

**Code:**
- Use inline code for commands/APIs/filenames
- Include concise, runnable code blocks when helpful

**Links:**
- Descriptive link text
- Clear CTAs ("Get started", "Read the docs", "Deploy")

### Step 3: Add Quotable Units

Create standardized blocks for each major concept:

**Definition Block:**
```markdown
## What is [Concept]?

[Term] is [category] that [key differentiator].

[2-3 sentences expanding on definition]
```

Requirements:
- 2-line literal definition (no metaphors)
- Place in first 100 words
- Include exact term in H1 and first sentence

**When to Use:**
```markdown
## When to Use [Concept]

**Use [concept] when you need to:**
- [Use case 1]
- [Use case 2]
- [Use case 3]
```

3-5 bullets with concrete scenarios.

**When Not to Use:**
```markdown
**Do not use [concept] when you need to:**
- [Limitation 1]
- [Limitation 2]
- [Limitation 3]
```

3-5 bullets with clear boundaries.

**Signals You Need This:**
```markdown
## Signals You Need [Concept]

- [Symptom 1]
- [Symptom 2]
- [Symptom 3]
```

Observable problems that indicate the concept/solution is needed.

### Step 4: Add Metrics and Measurement

Create a metrics section with specific numbers:

```markdown
## Metrics and Measurement

Track these metrics to [achieve goal]:

- **[Metric 1]:** [Description] ([standard range])
- **[Metric 2]:** [Description] ([standard range])
- **[Metric 3]:** [Description] ([standard range])
```

Requirements:
- Use specific numbers with units
- Include typical ranges
- Cite sources for statistics
- Add performance benchmarks where applicable

### Step 5: Add Comparison Tables

Create structured comparisons:

```markdown
## [Concept] Comparison

| Feature | Option A | Option B | Option C |
|---------|----------|----------|----------|
| [Aspect 1] | [Value] | [Value] | [Value] |
| [Aspect 2] | [Value] | [Value] | [Value] |
| Best for | [Use case] | [Use case] | [Use case] |
```

Use tables for:
- Feature comparisons
- Algorithm selections
- Protocol differences
- Layer-by-layer analysis

### Step 6: Add FAQ Section

Create comprehensive FAQ (minimum 10 questions):

```markdown
## Frequently Asked Questions

**[Natural language question]?**
[Direct answer in 2-3 sentences]

**[Question starting with Why/How/What/When]?**
[Answer]
```

Question types to include:
- "What is the difference between X and Y?"
- "When should I use X vs Y?"
- "How does X work?"
- "Why does X happen?"
- "What happens if I [action]?"

Requirements:
- Use complete questions as H2s
- Provide standalone answers (2-3 sentences)
- Include "Why," "How," "What," and "When" variants
- Make questions conversational (what developers actually ask)

### Step 7: Add Common Mistakes

```markdown
## Common Mistakes and Fixes

**Mistake:** [Common error]
**Fix:** [Specific solution]

**Mistake:** [Another error]
**Fix:** [Solution]
```

Include 3-5 common mistakes with concrete fixes.

### Step 8: Add "How to Implement" Section

Vendor-neutral explanation followed by specific implementation:

```markdown
## How This Applies in Practice

[2-3 sentences on practical application - vendor neutral]

## How to Implement on [Platform]

1. **[Step 1]:** [Action]
2. **[Step 2]:** [Action]
3. **[Step 3]:** [Action]

Learn more in the [documentation link](url).
```

### Step 9: Add Cross-Links

```markdown
## Related Resources

- [Related topic 1](link)
- [Related topic 2](link)
- [Related topic 3](link)
```

### Step 10: Add Authority Markers

```markdown
**Last updated:** YYYY-MM-DD

---

**Sources:**
- [Source 1. "Title."](url)
- [Source 2. "Title."](url)
```

### Step 11: Add Schema Markup (if requested)

Provide JSON-LD for structured data:

```json
{
  "@context": "https://schema.org",
  "@type": "TechArticle",
  "headline": "[Page Title]",
  "author": {"@type": "Organization", "name": "[Company]"},
  "datePublished": "YYYY-MM-DD",
  "dateModified": "YYYY-MM-DD"
}
```

## Output Format

Create a markdown file with optimized content:

```markdown
# [Primary Concept]

[Definition block - literal, 2 lines]

Last updated: YYYY-MM-DD

## How [Concept] Works

[Explanation in 2-3 paragraphs]

## Key Features

[Feature list or comparison table]

## When to Use [Concept]

**Use [concept] when you need to:**
- [Use case 1]
- [Use case 2]
- [Use case 3]

## When Not to Use [Concept]

**Do not use [concept] when you need to:**
- [Limitation 1]
- [Limitation 2]

## Signals You Need [Concept]

- [Symptom 1]
- [Symptom 2]

## Metrics and Measurement

- **[Metric 1]:** [Description] ([range])
- **[Metric 2]:** [Description] ([range])

## Common Mistakes and Fixes

**Mistake:** [Error]
**Fix:** [Solution]

## Frequently Asked Questions

**[Question]?**
[Answer]

[10+ questions total]

## How This Applies in Practice

[Vendor-neutral explanation]

## How to Implement on [Platform]

1. **[Step]:** [Action]

## Related Resources

- [Link 1]
- [Link 2]

---

**Sources:**
- [Source citation]
```

## Delivery

1. Save the file to `/home/claude/optimized-content.md`
2. Copy to `/mnt/user-data/outputs/optimized-content.md`
3. Present using the `present_files` tool
4. Give summary: what was optimized, what sections were added, metrics improved

## Edge Cases

- **Very short content (<200 words):** Add quotable units but note that more depth is needed
- **Already optimized content:** Identify gaps and add missing sections only
- **Non-technical content:** Adapt tone while maintaining structure
- **Multiple related concepts:** Create separate quotable units for each, use comparison tables
- **Missing metrics:** Use industry standards or note "varies by implementation"
- **No platform specified:** Provide vendor-neutral implementation guidance

## Terminology Simplification

When writing for Azion specifically:
- Use "Applications" instead of "Edge Applications"
- Use "Functions" instead of "Edge Functions"

## AI Discoverability Checklist

Before finalizing, verify:

- [ ] Lead with clear, literal definition (no metaphors)
- [ ] Use pattern: "[Term] is [category] that [differentiator]"
- [ ] Definition in first 100 words
- [ ] Exact term in H1 and first sentence
- [ ] FAQ section with 10+ natural language questions
- [ ] Complete questions as H2s (not fragments)
- [ ] Direct, standalone answers (2-3 sentences)
- [ ] Consistent terminology (no synonym variation)
- [ ] Technical specifications in tables/lists
- [ ] Metrics with units (e.g., "reduces latency by 40-60%")
- [ ] Cited sources with links
- [ ] Version numbers, release dates, timestamps
- [ ] References to standards (RFCs, W3C, ISO)
- [ ] "Last updated" in YYYY-MM-DD format
- [ ] Links to documentation
- [ ] Standalone quotable blocks
- [ ] Proper heading hierarchy
- [ ] Clear section boundaries
- [ ] Specific, verifiable claims with sources
- [ ] Canonical URLs for concepts
