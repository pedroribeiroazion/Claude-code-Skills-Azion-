---
name: writing-style-analyzer
description: "Analyze a creator's writing samples and reverse-engineer their style into a reusable Style Card. Use this skill whenever the user wants to capture a writing style, create a style guide from examples, analyze how someone writes, build a voice profile, or reproduce a creator's tone and structure. Also trigger when the user says 'analyze my writing style', 'create a style doc', 'capture this voice', or provides writing samples and wants to extract patterns from them."
---

# Writing Style Analyzer

## Overview

This skill takes 5-20 writing samples from a creator and reverse-engineers the patterns into a concise, reusable "Style Card." The Style Card captures voice, structure, mechanics, and rhetorical habits — everything needed to reproduce the style without copying phrases.

The output is a markdown file that can be uploaded into other content creation skills (like platform assembly skills or component skills) so Claude writes in that creator's voice.

This skill abstracts patterns. It never copies sentences from the examples.

## When to Use This Skill

Use this skill when:
- User wants to analyze their own writing style
- User wants to capture another creator's voice
- User provides writing samples and asks to extract style patterns
- User wants to create a style guide or voice profile
- User mentions reproducing a writing tone or style

## Input Required

### 1. Writing Samples (Required)
5-20 examples of the creator's writing. Can be:
- Pasted directly into the chat
- Uploaded as a file (doc, PDF, txt, md)
- A mix of both

More samples produce a more accurate Style Card. Fewer than 5 samples may miss patterns. If the user provides fewer than 5, note that the analysis may be less reliable and suggest they add more if possible.

The samples should represent the creator's typical writing — not their best or worst, but their consistent voice.

### 2. Style Name (Optional)
A name for the style (e.g., "Kieran's LinkedIn Voice", "Alex's Newsletter Tone"). If not provided, generate a descriptive name based on the patterns detected.

## Workflow

### Step 1: Load the Samples

Read all provided writing samples. If uploaded as a file, read from `/mnt/user-data/uploads/`. If pasted, use the text directly.

### Step 2: Detect Patterns

Scan all samples looking for consistent patterns across these dimensions:

**Voice & Tone**
- Attitude (confident, humble, irreverent, earnest, etc.)
- Formality level (casual, conversational, professional, academic)
- Point of view (first person, second person, collective "we")
- Energy (high-intensity, measured, calm, urgent)
- Emotional range (does the writer stay in one gear or shift between vulnerability, humour, authority?)

**Structure & Formatting**
- How do they open? (question, bold claim, story, data point, scene-setting)
- How do they pace content? (short paragraphs, long blocks, mixed)
- Line break habits (after every sentence? every 2-3 sentences? only between sections?)
- Use of bullets vs. paragraphs
- Section patterns (do they use headers, numbered lists, or just flow?)
- Scannability (is the writing designed to be skimmed or read deeply?)

**Hook Patterns**
- What types of hooks recur? (curiosity gap, contrarian statement, data lead, personal story, direct challenge)
- How long are their hooks typically? (one line, two lines, a short paragraph)
- Describe the patterns — do not generate example hooks

**Close Patterns**
- How do they end? (question to the reader, call to action, reflection, challenge, one-line punchline)
- Do they use a signature closing move?
- Describe the patterns — do not generate example closes

**Rhetorical Devices**
- Contrast and juxtaposition (before/after, old way/new way)
- Use of questions (rhetorical, direct to reader, Socratic)
- Data and specificity (do they cite numbers? how precise?)
- Personal anecdotes (frequent, rare, only as openers?)
- Analogies and metaphors (common, rare, what domains do they draw from?)
- Repetition and rhythm (do they use parallel structure, callbacks, rule of three?)

**Syntax & Mechanics**
- Average sentence length (short and punchy? long and flowing? mixed?)
- Punctuation habits (em dashes, ellipses, semicolons, exclamation marks)
- Emphasis style (bold, italics, ALL CAPS, none)
- Emoji usage (never, sparingly, frequently)
- How they handle numbers and data (spelled out, digits, percentages)
- Profanity/edge (clean, mild, sharp)

**Vocabulary**
- Signature words or phrases that recur across multiple samples
- Jargon level (insider language or accessible?)
- Words or patterns they clearly avoid

### Step 3: Handle Conflicts

If the samples show conflicting patterns (e.g., some posts are short and punchy while others are long and reflective), identify the dominant pattern and note the variation. The Style Card should reflect how the creator writes most of the time, with acceptable variations called out.

### Step 4: Build the Style Card

Synthesize all detected patterns into a concise Style Card. Every rule should be specific and measurable — avoid fuzzy advice like "be authentic" or "write naturally."

The Style Card should be 500-900 words. Dense and scannable, not padded.

## Output Format

Create a markdown file using this exact structure:

```markdown
# Style Card: [Style Name]

**Vibe:** [One-line description of the overall feel]

## TL;DR

- [Bullet 1 — captures the most distinctive aspect of the style]
- [Bullet 2 — captures the structural signature]
- [Bullet 3 — captures the tonal signature]

## Key Principles

- [Rule 1 — specific, testable]
- [Rule 2]
- [Rule 3]
- [Rule 4]
- [Rule 5]
- [Rule 6 — optional]
- [Rule 7 — optional]

## Voice & Tone

[2-4 sentences covering POV, cadence, attitude, emotional range. Be specific — not "confident tone" but "writes like they're explaining something to a smart peer over coffee — direct, no hedging, occasional dry humour."]

## Structure & Formatting

[2-4 sentences covering how posts are built: opening patterns, paragraph length, line breaks, use of bullets, scannability. Include measurable norms where possible — e.g., "paragraphs rarely exceed 3 sentences."]

## Hook Patterns

[Describe 4-6 recurring hook patterns as brief labelled descriptions. These are patterns, not generated examples.]

- **[Pattern name]:** [1-sentence description of how this hook works]
- **[Pattern name]:** [description]
- **[Pattern name]:** [description]
- **[Pattern name]:** [description]

## Close Patterns

[Describe 4-6 recurring close patterns as brief labelled descriptions.]

- **[Pattern name]:** [1-sentence description]
- **[Pattern name]:** [description]
- **[Pattern name]:** [description]
- **[Pattern name]:** [description]

## Devices & Patterns

[2-4 sentences on rhetorical moves: how and when the creator uses contrast, questions, data, anecdotes, analogies, repetition. Focus on the moves that most define the style.]

## Syntax & Mechanics

- **Sentence length:** [e.g., "Averages ≤15 words. Mixes 3-word fragments with occasional 25-word setups."]
- **Punctuation:** [e.g., "Heavy use of em dashes. No semicolons. Rare exclamation marks."]
- **Emphasis:** [e.g., "Bold for key phrases. No ALL CAPS. Minimal italics."]
- **Emoji:** [e.g., "None" or "1-2 per post, only as bullet markers"]
- **Numbers:** [e.g., "Always digits, never spelled out. Percentages frequent."]
- **Edge:** [e.g., "Clean language, no profanity. Occasional sharp phrasing."]

## Vocab & Phrases

**Lean into:**
- [Word/phrase 1]
- [Word/phrase 2]
- [Word/phrase 3]
- [Word/phrase 4]
- [Word/phrase 5]

**Avoid:**
- [Word/phrase 1]
- [Word/phrase 2]
- [Word/phrase 3]
- [Word/phrase 4]
- [Word/phrase 5]

## Do / Don't

| Do | Don't |
|---|---|
| [Specific, measurable guidance] | [Specific, measurable anti-pattern] |
| [Do 2] | [Don't 2] |
| [Do 3] | [Don't 3] |
| [Do 4] | [Don't 4] |
| [Do 5] | [Don't 5] |
| [Do 6] | [Don't 6] |

---

*This Style Card is designed to be used as context input for AI-powered content creation tools. Upload this file alongside your audience profile and talking points to generate content in this voice.*
```

### Writing Guidelines for the Style Card

- **Be specific, not vague.** "Writes with energy" is useless. "Opens 80% of posts with a single-sentence bold claim, followed by a line break" is useful.
- **Make rules testable.** Someone reading the Style Card should be able to check a draft against it and say "yes, this follows the rules" or "no, this breaks rule 3."
- **Abstract the pattern, never copy the words.** The Style Card describes *how* the creator writes, not *what* they write. No sentences lifted from the samples.
- **Prioritise what's distinctive.** Every creator uses paragraphs. Not every creator opens with a one-word sentence followed by an em dash. Focus on the patterns that make this voice recognisable.
- **Note variations honestly.** If the creator shifts between styles depending on topic or mood, say so. A Style Card that pretends the creator is perfectly consistent will produce rigid, unnatural content.

## Delivery

1. Save the file to `/home/claude/writing-style.md`
2. Copy it to `/mnt/user-data/outputs/writing-style.md`
3. Present it using the `present_files` tool
4. Give a brief summary: the style name, 2-3 sentences on what's most distinctive about this voice, and any areas where the samples showed conflicting patterns

## Edge Cases

- **Fewer than 5 samples:** Proceed but flag that the analysis may miss patterns. Recommend the user add more samples for a more reliable Style Card.
- **Samples from very different contexts (e.g., formal reports mixed with casual tweets):** Ask the user if they want one unified Style Card or separate ones per context. If unified, note the contextual variations.
- **Samples are very short (e.g., all tweets):** Work with what's available but note that short-form samples may not reveal structure and pacing patterns. Recommend adding longer-form samples if they exist.
- **User provides samples from multiple creators:** Ask the user to confirm — do they want a blended style or did they accidentally mix sources?
- **User asks to name the style:** Use their suggested name. If none provided, create a descriptive name that captures the vibe (e.g., "Sharp Operator" or "Calm Authority").
