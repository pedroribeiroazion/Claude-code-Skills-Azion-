---
name: newsletter-generator
description: "Learn a newsletter author's unique style from past editions and generate new newsletters in that exact voice. Use when you want to analyze writing style from examples, create newsletters matching an existing style, or automate newsletter production. Trigger when user mentions 'analyze my newsletter style', 'generate newsletter', 'write newsletter in my voice', or provides past newsletters and wants new ones."
---

# Newsletter Generator

## Overview

This skill automates newsletter writing by learning an author's unique style from past editions, then generating new newsletters on any topic in that same voice. It performs two main functions:

1. **Style Analysis** — Reads past newsletters and extracts voice, structure, vocabulary, themes, and rhetorical devices into a reusable style profile
2. **Newsletter Generation** — Writes new newsletters matching the extracted style exactly

## When to Use This Skill

Use this skill when:
- You have past newsletters and want to analyze writing style
- You want to generate new newsletters in an existing author's voice
- You need to automate newsletter production at scale
- You're creating a newsletter style guide from examples
- You want to maintain consistent voice across multiple editions

## Input Required

### For Style Analysis:
**Past Newsletters** (Required)
5-20 past newsletter editions. Can be:
- Files uploaded to `/mnt/user-data/uploads/`
- Pasted text directly in the chat
- Mix of formats (.txt, .md, .html)

More samples = more accurate style profile. Fewer than 5 samples may miss patterns.

### For Newsletter Generation:
**Style Profile** (Required)
A completed `style_profile.md` (can be created by this skill or provided by user)

**Topic** (Required)
The subject/angle for the new newsletter

**Additional Context** (Optional)
- Target audience details
- Specific points to include
- Tone adjustments (e.g., "more urgent than usual")

## Workflow

### PHASE 1: Style Analysis

Use this phase when user asks to "analyze my style" or "create style profile" or provides past newsletters for analysis.

#### Step 1: Load Past Newsletters

Read all provided newsletter files. If uploaded, read from `/mnt/user-data/uploads/`. If pasted, use text directly.

#### Step 2: Analyze Writing Style

Scan all newsletters for patterns across 7 dimensions:

**1. Voice & Tone**
- Formal or informal register?
- First person, second person, or both?
- Humor, sarcasm, warmth, authority — what emotional tone dominates?
- How does the author build trust with the reader?
- Any signature attitude or stance? (contrarian, optimistic, pragmatic)

**2. Typical Structure**
- How does each newsletter open? (hook, question, anecdote, data point, industry context?)
- How is the body organized? (sections, numbered lists, flowing prose?)
- How does it close? (CTA, reflection, question for reader, signature sign-off?)
- Is there a recurring signature element? (e.g., a quote, a P.S., a tagline, a specific section name)
- Any recurring section patterns? (e.g., "SUCCESS STORY", "PRODUCT UPDATES", "WEBINAR")

**3. Sentence & Paragraph Patterns**
- Average sentence length (short and punchy vs. long and layered?)
- Average paragraph length (1-liner breaks vs. dense blocks?)
- Transition style between ideas
- Punctuation habits (em-dashes, parentheses, ellipses?)

**4. Vocabulary & Expressions**
- Common words and phrases the author repeats
- Industry jargon or terms they avoid/prefer
- Any catchphrases or recurring expressions
- Words they never seem to use
- How they handle technical terms (explained, assumed knowledge, defined inline?)

**5. Recurring Themes & Worldview**
- What topics does the author come back to?
- What beliefs or values show up consistently?
- What is their typical stance? (contrarian, optimistic, pragmatic, solution-oriented)
- What lens do they apply to new topics?

**6. Rhetorical Devices**
- Do they use questions to engage the reader? How often? What type?
- Metaphors, analogies, or storytelling?
- Do they use bullet points, bold text, or headers? How?
- Numbers and metrics — how do they quantify claims?
- Social proof patterns (customer quotes, case studies, awards)?

**7. Reader Relationship**
- How does the author address the reader? (you, your, we, community, friends?)
- Is there a sense of community or insider language?
- How personal or vulnerable does the author get?
- Signature sign-off format

#### Step 3: Extract Examples

For each section, include at least 2 real examples quoted directly from the newsletters to support the analysis.

#### Step 4: Create Style Profile

Synthesize all findings into a structured `style_profile.md` file.

### PHASE 2: Newsletter Generation

Use this phase when user asks to "generate newsletter about [topic]" and a style profile exists.

#### Step 1: Verify Style Profile Exists

Check if `style_profile.md` exists. If not:
- Ask user to provide past newsletters for analysis, OR
- Ask if they have an existing style profile to upload

#### Step 2: Read Style Profile

Read the complete `style_profile.md` carefully before writing anything. Internalize:
- Voice and tone
- Structure patterns
- Vocabulary and expressions
- Recurring themes and worldview
- Rhetorical devices

#### Step 3: Understand Topic

Analyze the requested topic and:
- Identify the core problem or angle
- Determine how it connects to the author's recurring themes/worldview
- Find the natural stance or lens the author would apply

#### Step 4: Plan Structure

Based on the style profile's "Typical Structure" section, plan:
- Opening format (will match their pattern)
- Body organization (sections, headers, bullet style)
- Closing format (including signature elements)
- Any recurring section names to include

#### Step 5: Write Newsletter

Write the complete newsletter following these critical rules:

**1. STYLE FIRST — mirror the voice, tone, and structure from the style profile**
Do not default to generic newsletter formats. Write like the author, not like a bot.

**2. STRUCTURE — follow the author's typical opening, body, and closing patterns**
If they use a P.S., include one. If they open with a question, open with a question. If they have "SUCCESS STORY" sections, include one.

**3. LENGTH — match the average length of the existing newsletters**
Count approximate words from samples and match that range.

**4. VOCABULARY — use the expressions, phrases, and register from the profile**
Avoid words and patterns the author doesn't use. Lean into their common phrases.

**5. THEME CONNECTION — apply the author's recurring worldview/stance to the new topic**
See the topic through their lens. Use their typical framing.

**6. NO TEMPLATES — no filler phrases**
Do not use:
- "In today's newsletter..."
- "I hope this finds you well"
- "Before we dive in..."
- Generic intros that the author doesn't use

**7. SPECIFICITY — include the types of details the author uses**
If they cite metrics, include metrics. If they use customer quotes, include customer context. If they reference industry reports, add that style of social proof.

#### Step 6: Apply Rhetorical Devices

Use the devices identified in the profile:
- Questions at the same frequency and placement
- Numbers and metrics in the same style
- Bullet point formatting matching their patterns
- Same level of technical depth

#### Step 7: Match Reader Relationship

Use the same:
- Address style (you/we/community/friends)
- Sign-off format
- Level of personal vulnerability
- Community references

#### Step 8: Save Newsletter

Save with clear naming: `newsletter-[date]-[topic-slug].md`

## Output Format

### Style Profile Output:

```markdown
# Style Profile — [Author/Newsletter Name]

## 1. Voice & Tone

**Register:** [Formal/informal/technical approachable/etc.]

**Person:** [First person/second person/mix]

**Emotional tone:** [Dominant tone description]

**Examples:**
- "[Quote 1 from newsletters]"
- "[Quote 2 from newsletters]"

---

## 2. Typical Structure

**Opening:** [How they open, with example]

**Body:** [How they organize content, with example]

**Closing:** [How they close, with example]

**Recurring elements:** [Signature sections, CTAs, sign-offs]

**Examples:**
- "[Quote showing opening pattern]"
- "[Quote showing structure]"

---

## 3. Sentence & Paragraph Patterns

**Sentence length:** [Description with examples]

**Paragraph length:** [Description with examples]

**Transitions:** [How they move between ideas]

**Examples:**
- "[Quote showing sentence patterns]"

---

## 4. Vocabulary & Expressions

**Common phrases:**
- [Phrase 1]
- [Phrase 2]
- [Phrase 3]

**Technical terms:** [How they use industry language]

**Words avoided:** [What they don't use]

**Examples:**
- "[Quote showing vocabulary choices]"

---

## 5. Recurring Themes & Worldview

**Core themes:**
- [Theme 1]
- [Theme 2]
- [Theme 3]

**Worldview:** [Description of their perspective]

**Stance:** [Contrarian/pragmatic/optimistic/etc.]

**Examples:**
- "[Quote showing worldview]"

---

## 6. Rhetorical Devices

**Questions:** [How and when they use them]

**Numbers and metrics:** [How they quantify]

**Problem-solution framing:** [How they structure]

**Social proof:** [What type of proof they use]

**Examples:**
- "[Quote showing devices]"

---

## 7. Reader Relationship

**Address style:** [How they talk to readers]

**Community sense:** [How they build community]

**Personal touches:** [Signature elements]

**Examples:**
- "[Quote showing reader relationship]"
```

### Newsletter Output:

```markdown
# [Newsletter Title Matching Author's Style]

[Opening following author's typical pattern]

[Body organized per author's structure]

[Sections with headers if author uses them]

[Bullet points if author uses them]

[Metrics and examples matching author's style]

[Closing following author's pattern]

[Signature sign-off if author has one]
```

## Delivery

### Style Profile:
1. Save to `/home/claude/style_profile.md`
2. Copy to `/mnt/user-data/outputs/style_profile.md`
3. Present using `present_files` tool
4. Give summary: key voice attributes, structure patterns, 3 most distinctive elements

### Newsletter:
1. Save to `/home/claude/newsletter-[date]-[topic-slug].md`
2. Copy to `/mnt/user-data/outputs/newsletter.md`
3. Present using `present_files` tool
4. Give summary: topic, how it applies the style, length, key sections

## Edge Cases

### Style Analysis:
- **Fewer than 5 samples:** Proceed but flag that analysis may miss patterns. Recommend adding more.
- **Samples from different contexts:** Ask if user wants unified profile or separate ones.
- **Very short samples:** Note that short-form may not reveal structure patterns.
- **Multiple authors:** Ask if blended style is intentional.
- **Inconsistent styles across samples:** Identify dominant pattern and note variations.

### Newsletter Generation:
- **No style profile:** Ask to run analysis first or upload existing profile.
- **Topic conflicts with worldview:** Apply author's typical stance even if unusual.
- **Topic requires different structure:** Explain how adapting while maintaining voice.
- **Length significantly different:** Match author's typical length even if topic seems to need more/less.

## Quality Checklist

### Style Profile:
- [ ] Each section has 2+ real quotes from samples
- [ ] Voice description is specific (not just "professional")
- [ ] Structure includes opening, body, and closing patterns
- [ ] Vocabulary lists both what they use AND what they avoid
- [ ] Worldview describes their lens/stance
- [ ] Reader relationship includes sign-off format

### Newsletter:
- [ ] Matches author's voice (not generic newsletter template)
- [ ] Structure mirrors their typical pattern
- [ ] Length matches their average
- [ ] Uses their common phrases and vocabulary
- [ ] Applies their worldview to the new topic
- [ ] No filler phrases ("In today's newsletter...")
- [ ] Includes their signature elements (P.S., specific sections, etc.)
- [ ] Sign-off matches their format

## Common Mistakes to Avoid

❌ **Generic templates** — "In this newsletter we'll explore..."
✅ **Author's patterns** — Match their opening style exactly

❌ **Wrong register** — Too formal or too casual for the author
✅ **Matched register** — Same level of formality as samples

❌ **Missing signature elements** — Forgot their P.S. or recurring section
✅ **Complete style match** — Include all recurring elements

❌ **Different worldview** — Applied wrong lens to topic
✅ **Consistent stance** — See topic through author's perspective

❌ **Wrong length** — Significantly shorter/longer than typical
✅ **Matched length** — Same word count range as samples
