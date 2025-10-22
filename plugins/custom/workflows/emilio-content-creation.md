# Content Creation Workflow

**Multi-agent orchestration for research-driven, strategically-positioned content creation**

## Overview

This workflow coordinates research, strategy, and sales agents to create high-quality content (blog posts, sales collateral, documentation) that is well-researched, strategically positioned, and conversion-optimized.

## Arguments

- `$CONTENT_TYPE`: blog-post|one-pager|case-study|whitepaper|demo-script|battlecard
- `$TOPIC`: Content topic or feature focus
- `$AUDIENCE`: Target persona (technical-buyer|executive|end-user)

## Workflow Steps

### Step 1: Research & Intelligence Gathering (10-15 min)

**Agent:** @emilio-research-agent

```
@emilio-research-agent "Research for content: $TOPIC targeting $AUDIENCE"

Gather intelligence on:
1. **Competitive landscape**: How competitors message similar topics
2. **Customer pain points**: Evidence of problems this addresses
3. **Market trends**: Industry direction, emerging patterns
4. **Proof points**: Case studies, metrics, testimonials
5. **Technical depth**: Level appropriate for $AUDIENCE
6. **SEO keywords**: Search terms and intent (for blog posts)

Key outputs:
- Competitive messaging analysis
- Customer pain quotes with sources
- Market data with citations
- **Key insights** (bolded)
- Confidence levels on claims
- Gaps in competitive content (opportunity)
```

**Validation:**
- All claims cited with sources
- Customer evidence (not just assumptions)
- Competitive differentiation identified

---

### Step 2: Strategic Positioning (10 min)

**Agent:** @emilio-strategy-agent OR @emilio-sales-agent (content-type dependent)

**For Strategic Content (Strategy Agent):**
```
@emilio-strategy-agent "Position content on $TOPIC for $AUDIENCE"

Define:
1. **Core message**: Single takeaway for reader
2. **Value proposition**: What reader gains from content
3. **Competitive angle**: How we're different/better
4. **Call-to-action**: What reader should do next
5. **Success metric**: How to measure content effectiveness

Key outputs:
- One-sentence core message
- Value prop with quantification
- Differentiation themes
- CTA strategy (awareness/consideration/decision stage)
```

**For Sales Content (Sales Agent):**
```
@emilio-sales-agent "Position sales content for $TOPIC targeting $AUDIENCE"

Define:
1. **Customer pain**: Quantified problem statement
2. **Value proposition**: ROI-driven messaging
3. **Proof points**: Case studies, metrics, testimonials
4. **Objection handling**: Pre-empt common concerns
5. **Competitive positioning**: Win themes vs alternatives

Key outputs:
- Pain-agitate-solve narrative
- ROI calculator or quantified value
- Comparison table (us vs alternatives)
- Objection handling responses
```

**Validation:**
- Clear, differentiated positioning
- Quantified value where possible
- Competitive advantage explicit

---

### Step 3: Content Creation (15-20 min)

**Agent:** @technical-writer OR @seo-writer OR @emilio-sales-agent (content-type dependent)

**For Blog Posts (SEO Writer):**
```
@seo-writer "Write blog post on $TOPIC"

Using inputs from Steps 1-2:
- Core message and value prop
- Research findings with citations
- Competitive differentiation
- Target SEO keywords

Structure:
1. **Hook**: Compelling opening (problem or stat)
2. **Problem**: Customer pain with evidence
3. **Solution**: Our approach (differentiated)
4. **Proof**: Case study, metrics, quotes
5. **Conclusion**: Recap + CTA

Optimization:
- SEO keywords naturally integrated
- Meta description optimized
- Internal/external links
- Scannable (H2/H3, bullets, **bold**)
```

**For Sales One-Pagers (Sales Agent):**
```
@emilio-sales-agent "Create one-pager for $TOPIC"

Structure:
1. **Problem**: Customer pain (quantified)
2. **Solution**: How we solve (3 key capabilities)
3. **Value**: ROI calculator or quantified benefit
4. **Proof**: Case study or customer quote
5. **Differentiation**: Why us vs alternatives
6. **CTA**: Trial, demo, or next step

Format:
- Single page, scannable
- **Bold value propositions**
- Comparison table for competitive positioning
- Confidence levels on ROI projections
```

**For Technical Documentation (Technical Writer):**
```
@technical-writer "Document $TOPIC for $AUDIENCE"

Structure:
1. **Overview**: What this is and why it matters
2. **How it works**: Step-by-step or conceptual
3. **Examples**: Code samples, screenshots, use cases
4. **Best practices**: Recommendations and patterns
5. **Troubleshooting**: Common issues and solutions

Format:
- Progressive disclosure (simple → complex)
- Code examples tested and working
- Diagrams for complex concepts
- Cross-references to related docs
```

**Validation:**
- Content matches positioning from Step 2
- Claims supported by research from Step 1
- CTA clear and appropriate for content type

---

### Step 4: Review & Synthesis (5 min)

**Agent:** @emilio-memory-agent

```
@emilio-memory-agent "Extract key insights from content creation process"

Document:
- **Core message** (what was communicated)
- **Positioning** (how we differentiated)
- **Proof points** (evidence used)
- **Performance** (if tracked: views, conversions)
- **Learnings** (what worked, what to improve)

Save to: memory-system/content/[CONTENT_TYPE]-[TOPIC]-[DATE].md
```

---

## Success Criteria

- ✅ Research supports all major claims with citations
- ✅ Positioning clearly differentiated from competitors
- ✅ Value quantified where possible (ROI, time saved, etc.)
- ✅ Content scannable (**bold** key points, bullets, headers)
- ✅ Appropriate technical depth for audience
- ✅ Clear CTA matched to buyer stage
- ✅ Confidence levels on projections/claims
- ✅ Unknown unknowns flagged (e.g., need customer validation)

---

## Output Format (Content-Type Specific)

### BLOG POST STRUCTURE

**Title:** [SEO-optimized, 60 chars]
**Meta Description:** [155 chars, CTA included]
**Target Keyword:** [Primary SEO term]
**Audience:** [Persona]

#### Hook (100 words)
[Compelling opening - stat, problem, or question]

#### The Problem (200 words)
**[Customer pain with quantification]**
- Pain point 1 (with evidence)
- Pain point 2 (with source: Author, 2024)

#### Our Solution (300 words)
**[How we solve differently]**
- Capability 1 → Outcome
- Capability 2 → Outcome
- **Key differentiator** (bolded)

#### Proof & Results (200 words)
Case study: [Customer name]
- Metric 1: [Improvement]
- Metric 2: [Result]
> "Customer quote" - Name, Title, Company

#### Conclusion & CTA (100 words)
[Recap key points]
**Call-to-action:** [Try, demo, download, read more]

---

### ONE-PAGER STRUCTURE

#### PROBLEM (Top third)
**[Customer pain in 2-3 sentences]**
- Pain point 1 (quantified: costs $X/year)
- Pain point 2 (quantified: wastes Y hours/week)

#### SOLUTION (Middle third)
**How [Product] Solves It:**
- **Capability 1** → Outcome
- **Capability 2** → Outcome
- **Capability 3** → Outcome

**Value:**
- **ROI:** [Metric] | Confidence: Medium
- **Time savings:** [Metric]
- **Risk reduction:** [Metric]

#### DIFFERENTIATION (Bottom third)

| | Us | Competitor A | Competitor B |
|---|----|--------------|--------------
| **Key Feature** | ✓ Revolutionary | ✗ Not supported | △ Basic |
| Price | $X/mo | $Y/mo | $Z/mo |
| **Winner** | **Us (unique capability)** | - | - |

**Proof:** "[Customer quote or metric]"

**CTA:** [Start trial | Book demo | Download whitepaper]

---

### BATTLECARD STRUCTURE

**Competitor:** [Name]

**Overview:**
- Target customer: [Segment]
- Strengths: [What they do well]
- Weaknesses: [Gaps we exploit]

**Win Themes:**
1. **[Our advantage 1]** vs [Their limitation]
2. **[Our advantage 2]** vs [Their limitation]

**Trap-Setting Questions:**
- "How do you handle [scenario we excel at]?"
- "Can your solution [capability they lack]?"

**Objection Handling:**
- **"They're cheaper"** → Response: [Total cost comparison]
- **"They're more established"** → Response: [Innovation advantage]

**Competitive Intelligence:**
- Pricing: [Their model]
- Recent moves: [Product launches, acquisitions]
- Customer sentiment: [Review analysis]

---

## Example Usage

```bash
# Blog post for technical audience
@emilio-content-creation blog-post "How ICIP saves IoT companies $50K/year" technical-buyer

# Sales one-pager for executives
@emilio-content-creation one-pager "ICIP ROI Calculator" executive

# Competitive battlecard
@emilio-content-creation battlecard "ICIP vs Manual Spreadsheets" technical-buyer

# Case study
@emilio-content-creation case-study "Customer X reduced costs 30% with ICIP" executive

# Demo script
@emilio-content-creation demo-script "ICIP forecasting engine walkthrough" technical-buyer
```

---

## Agent Coordination

**Sequential execution:**
1. Research agent (evidence and intelligence)
2. Strategy/Sales agent (positioning and messaging)
3. Content agent (actual writing)
4. Memory agent (synthesis and tracking)

**No parallel execution** - each phase depends on prior

**Handoffs:**
- Research → provides evidence → Strategy/Sales
- Strategy/Sales → provides positioning → Content writer
- Content writer → produces draft → Memory agent

---

## Content Type Matrix

| Content Type | Research | Strategy/Sales | Writer | Audience |
|--------------|----------|----------------|--------|----------|
| **Blog Post** | Yes | Strategy | SEO Writer | All |
| **One-Pager** | Yes | Sales | Sales Agent | Executive |
| **Battlecard** | Yes (competitive) | Sales | Sales Agent | Sales team |
| **Case Study** | Yes (customer) | Sales | Technical Writer | All |
| **Demo Script** | Yes (features) | Sales | Sales Agent | Technical |
| **Whitepaper** | Yes (deep) | Strategy | Technical Writer | Technical |

---

## Quality Checklist

### Research Quality
- [ ] All claims cited with sources
- [ ] Competitive analysis included
- [ ] Customer evidence (not assumptions)
- [ ] Market data current (<6 months old)

### Positioning Quality
- [ ] Clear value proposition
- [ ] Quantified value where possible
- [ ] Competitive differentiation explicit
- [ ] Objection handling prepared

### Content Quality
- [ ] Scannable (bullets, **bold**, headers)
- [ ] Appropriate technical depth for audience
- [ ] CTA clear and contextual
- [ ] Confidence levels on claims
- [ ] SEO optimized (if blog post)
- [ ] Visually structured (tables, comparisons)

---

## Troubleshooting

**Q: Research doesn't find competitive differentiation**
- Action: Deeper research on alternatives, or reframe problem definition

**Q: Value hard to quantify**
- Action: Use time savings, risk reduction, or qualitative benefits

**Q: Content too technical for audience**
- Action: Add analogies, simplify language, focus on outcomes over mechanisms

**Q: CTA unclear for content type**
- Action: Match CTA to buyer stage (awareness → consideration → decision)

---

**Last Updated:** 2025-10-22
