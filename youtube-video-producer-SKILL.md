---
name: youtube-video-producer
description: "Produce YouTube video scripts for Azion targeting tech leaders (CTO, CISO, VP Engineering). Creates complete video production packages with narrative structure, two-column scripts, and visual directions. Use when creating educational tech videos, product explainers, or thought leadership content for B2B audiences. Trigger when user mentions 'video script', 'YouTube video', 'roteiro de vídeo', or provides a video concept."
---

# YouTube Video Producer for Azion

## Overview

This skill acts as a video production assistant with screenwriting and social media expertise. It creates complete YouTube video packages for Azion's technology content targeting CTO, CISO, VP Engineering, and tech leaders. Videos focus on solving business problems with Azion as part of the solution.

The skill creates narrative-driven scripts optimized for limited production setups (camera, microphone, screen sharing with whiteboards, live code, and demos).

## When to Use This Skill

Use this skill when:
- Creating YouTube video scripts for technical/B2B audiences
- Producing educational content about edge computing, security, or distributed systems
- Developing thought leadership videos for tech leaders
- Writing video scripts that need visual production guidance
- Creating product explainers with business value focus

## Input Required

### 1. Video Concept (Required)
A description of the video topic, goal, or angle. Can be:
- A specific technology or problem to address
- A use case to explore
- A product feature to explain
- A thought leadership topic

Example: "How to reduce API latency for global e-commerce platforms"

### 2. Video Length (Optional)
Target duration. Default: "8-12 minutes" (ideal for educational tech content)

### 3. Format Focus (Optional)
Primary format emphasis:
- "Narrative" - story-driven with problem/solution arc (default)
- "Technical" - code-heavy with demos
- "Business" - metrics and ROI focus
- "Educational" - teaching concepts with examples

## Workflow

### Step 1: Analyze Video Concept

Read the video concept and identify:
- Core problem to solve
- Target audience (CTO, CISO, VP Engineering, tech leaders)
- Business impact and stakes
- Azion's role in solution
- Key technical concepts to explain

### Step 2: Create Title and Thumbnail Strategy

Generate 3-5 title options optimized for:
- CTR (click-through rate)
- Clarity for decision-makers
- Curiosity gap
- Business outcome focus

Thumbnail concepts must:
- Visually match the video opening
- Support title promise
- Be simple and clear
- Use text overlays sparingly (2-4 words max)

### Step 3: Structure Hero's Journey

Answer the seven journey questions:

1. **Who is the character?**
   Define the protagonist (usually the viewer/decision-maker or their company)

2. **What does he want?**
   Clear goal or desired outcome

3. **Why doesn't he get what he wants?**
   Obstacles, limitations, or gaps

4. **What are the losses?**
   Stakes and consequences of failure

5. **What or who helps him?**
   The solution or enabler (Azion + concepts)

6. **How does he get what he wants?**
   The transformation journey and implementation

7. **How is he transformed?**
   New capabilities, outcomes, status after success

### Step 4: Design Opening Sequence

**First 5 Seconds (The Hook):**
- Text must match video title exactly
- Visual must match thumbnail concept
- Create immediate pattern interrupt or curiosity
- Establish credibility or stakes

Example structure:
```
VISUAL: [Camera on presenter, background matches thumbnail]
AUDIO: "If your API latency exceeds 200 milliseconds, you're losing 23% of customers before they convert."
[Title overlay appears]
```

**Introduction Arc (30-60 seconds):**
Build curiosity through:
1. **Context setup:** Why this matters now
2. **Input bias creation:** Signal effort and value ("After working with 50+ enterprise teams...")
3. **Promise of transformation:** What they'll learn/achieve
4. **Credibility marker:** Brief authority signal

### Step 5: Apply Gagne's Nine Events of Instruction

Structure content using Gagne's framework:

1. **Gain Attention**
   The hook (first 5 seconds)

2. **Inform Learners of Objectives**
   Clear statement: "In this video, you'll learn how to..."

3. **Stimulate Recall of Prior Knowledge**
   Connect to what they already know: "You've probably experienced..."

4. **Present the Content**
   Core technical/business content with visual support

5. **Provide Learning Guidance**
   Explain how to apply: "Here's how this works in practice..."

6. **Elicit Performance (Practice)**
   Show examples, demos, or live coding

7. **Provide Feedback**
   Address common mistakes or questions

8. **Assess Performance**
   Check understanding: "Key takeaway from this section..."

9. **Enhance Retention and Transfer**
   Summary and next steps: "Here's what to do next..."

### Step 6: Create Two-Column Script

Write the complete script in two-column format:

| Audio (Left Column) | Visual (Right Column) |
|---------------------|----------------------|
| Presenter's spoken words | Shot description, graphics, screen shares, demos |

**Visual Production Notes:**
- Specify camera angles (camera on presenter, screen share, split screen)
- Note when to use whiteboard diagrams
- Indicate live code or demo sections
- Mark B-roll needs (product screens, architecture diagrams, metrics dashboards)
- Include text overlays and graphics instructions

**Production Constraints:**
- Assume: Camera, microphone, computer with screen sharing
- Available: Whiteboard apps, live code, product demos
- Limit: Complex animations or extensive post-production

### Step 7: Structure Business Value

Throughout the script, include:
- **Metrics and ROI:** Specific numbers, benchmarks, improvements
- **Risk mitigation:** Security, compliance, reliability benefits
- **Cost optimization:** Infrastructure savings, efficiency gains
- **Time to value:** How quickly they can implement and see results
- **Competitive advantage:** Differentiation through technology

### Step 8: Add Calls to Action

Include natural CTAs:
- **Mid-video:** "If you're finding this valuable, subscribe for more tech leadership content"
- **End:** Specific next step (try Azion, read docs, book demo, join community)
- **Description:** Links to resources, documentation, trials

### Step 9: Create Closing Sequence

Design strong ending with:
- Summary of key insights (3-5 bullets)
- Business outcome reinforcement
- Clear next action
- Teaser for related content

### Step 10: Add Production Notes

Include:
- Estimated video length
- Required graphics/screenshots
- Demo preparation checklist
- Key talking points for presenter
- Suggested tags and description for YouTube

## Output Format

Create a markdown file with complete video package:

```markdown
# Video Production Package: [Video Concept]

## Target Audience
CTO, CISO, VP Engineering, Tech Leaders

## Video Length
[Target duration]

---

## Title & Thumbnail Strategy

### Title Options (Choose One):
1. [Title 1 - optimized for CTR]
2. [Title 2 - optimized for clarity]
3. [Title 3 - optimized for curiosity]

### Thumbnail Concept:
**Visual:** [Description of thumbnail design]
**Text Overlay:** [2-4 words max]
**Style:** [Color scheme, mood]

---

## Hero's Journey Analysis

### 1. Who is the character?
[The protagonist - usually the viewer/decision-maker]

### 2. What does he want?
[Clear goal or desired outcome]

### 3. Why doesn't he get what he wants?
[Obstacles, limitations, gaps]

### 4. What are the losses?
[Stakes and consequences if they fail]

### 5. What or who helps him?
[Solution/enabler - Azion + concepts]

### 6. How does he get what he wants?
[Transformation journey]

### 7. How is he transformed?
[New capabilities and outcomes]

---

## Opening Sequence

### First 5 Seconds (Hook):
**Audio:** "[Exact text matching title]"
**Visual:** [Scene description matching thumbnail]

### Introduction Arc (30-60 seconds):
[Context → Input Bias → Promise → Credibility]

---

## Complete Two-Column Script

| Audio | Visual |
|-------|--------|
| [Presenter's words] | [Visual directions] |
| [Continue for entire video] | [Include all scenes] |

---

## Gagne's Nine Events Applied

1. **Gain Attention:** [How the hook captures attention]
2. **Inform Objectives:** [Learning objectives stated]
3. **Recall Prior Knowledge:** [Connections to existing knowledge]
4. **Present Content:** [Core content delivery method]
5. **Provide Guidance:** [Application guidance]
6. **Elicit Performance:** [Examples/demos/practice]
7. **Provide Feedback:** [Common mistakes addressed]
8. **Assess Performance:** [Understanding checks]
9. **Enhance Retention:** [Summary and transfer]

---

## Business Value Points

**Metrics & ROI:**
- [Specific improvement metrics]
- [Benchmark comparisons]

**Risk Mitigation:**
- [Security benefits]
- [Compliance advantages]

**Cost Optimization:**
- [Infrastructure savings]
- [Efficiency gains]

**Time to Value:**
- [Implementation timeline]
- [Quick wins]

---

## Production Notes

### Required Assets:
- [ ] [Graphics/slide 1]
- [ ] [Architecture diagram]
- [ ] [Product screenshot]
- [ ] [Demo environment setup]

### Estimated Timeline:
- Hook: [X seconds]
- Intro: [X seconds]
- Core content: [X minutes]
- Demo/examples: [X minutes]
- Closing: [X seconds]
- **Total:** [X minutes]

### Key Talking Points:
- [Point 1]
- [Point 2]
- [Point 3]

### YouTube Metadata:
**Tags:** [Relevant tags]
**Category:** [YouTube category]
**Description Template:**
[Opening hook]
[Key takeaways]
[Links to resources]
[CTA]

---

## Calls to Action

**Mid-Video:** [Specific CTA]
**End:** [Primary next step]
**Description:** [Links and resources]
```

## Delivery

1. Save to `/home/claude/video-script-[concept].md`
2. Copy to `/mnt/user-data/outputs/video-script.md`
3. Present using `present_files` tool
4. Give summary: concept, audience, video length, key business value

## Azion Positioning Guidelines

When mentioning Azion:

**Position as:**
- Comprehensive computing and security platform
- Leader in distributed/edge computing with global network
- Serverless capabilities with real-time observability
- Developer-friendly with focus on security, performance, scalability

**Core Services to Mention:**
- Applications (distributed app development)
- AI (conversational interfaces, content generation)
- Functions (serverless computing)
- Firewall (WAF, DDoS, bot management)
- Storage (Object Storage, SQL Database)
- Network (global Edge Locations)
- Real-Time Metrics & Events (observability)

**Competitive Advantages:**
- Fully integrated platform: serverless + security + observability
- Global Network for ultra-low latency
- Real-time insights for proactive decisions
- Developer-friendly tools and APIs

**Trusted By:**
- Prime Video, Neon, Global Fashion Group, Radware

## Edge Cases

- **Very technical concept:** Add more demo time, simplify business narrative
- **Business-focused topic:** Reduce technical depth, emphasize ROI metrics
- **No demo needed:** Focus on whiteboard explanations and architecture diagrams
- **Multiple use cases:** Choose one primary case, mention others briefly
- **Complex architecture:** Break into multiple videos or use layered explanation

## Quality Checklist

Before finalizing, verify:

- [ ] Title creates curiosity gap for decision-makers
- [ ] Hook text matches title exactly
- [ ] Visual matches thumbnail concept
- [ ] Hero's journey is clear and complete
- [ ] Gagne's nine events are applied
- [ ] Business value appears every 2-3 minutes
- [ ] Production is feasible (camera, screen share only)
- [ ] Video is in English
- [ ] Azion is positioned as enabler, not just product pitch
- [ ] CTA is clear and actionable
- [ ] Estimated length is reasonable (8-15 minutes ideal)
- [ ] Technical depth matches audience (decision-makers)
- [ ] Includes metrics/ROI/benchmarks
