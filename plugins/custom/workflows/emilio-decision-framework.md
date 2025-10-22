# Decision Framework Workflow

**Multi-agent orchestration for strategic decisions with research, analysis, and recommendation**

## Overview

This workflow coordinates research, architecture/strategy analysis, and synthesis to make evidence-based strategic decisions with explicit trade-offs and confidence levels.

## Arguments

- `$DECISION`: Decision to be made (e.g., "PostgreSQL vs MongoDB for ICIP")
- `$CONTEXT`: Project or domain context
- `$CRITERIA`: Optional - specific evaluation criteria

## Workflow Steps

### Step 1: Research & Evidence Gathering (15-20 min)

**Agent:** @emilio-research-agent

```
@emilio-research-agent "Research options for decision: $DECISION"

Gather evidence on:
1. **Option comparison**: Feature matrix, pros/cons
2. **Use cases**: When each option excels
3. **Performance data**: Benchmarks, scalability characteristics
4. **Ecosystem**: Community, docs, library support, hiring
5. **Cost analysis**: Licensing, infrastructure, operational costs
6. **Real-world usage**: Case studies, experience reports, gotchas

Key outputs:
- Comparison matrix with sources
- **Key findings** (bolded)
- Confidence levels (High/Medium/Low)
- Citations for all claims (Author/Year or URL)
- Contradictory evidence flagged
- Unknown unknowns requiring validation
```

**Validation:**
- All claims have citations
- Multiple viewpoints considered
- Source quality assessed (Tier-1/2/3)

---

### Step 2: Technical/Strategic Analysis (10-15 min)

**Agents:** @emilio-architecture-agent OR @emilio-strategy-agent (context-dependent)

**For Technical Decisions (Architecture Agent):**
```
@emilio-architecture-agent "Evaluate $DECISION for $CONTEXT"

Analyze:
1. **Fit with architecture**: How each option integrates
2. **Scalability**: Growth path and limitations
3. **Complexity**: Development and operational overhead
4. **Risk assessment**: Technical risks per option
5. **Migration path**: If we choose A, can we switch to B later?

Key outputs:
- Technology comparison matrix with weighted scoring
- **Critical trade-offs** (bolded)
- Architectural implications per option
- Confidence levels on recommendations
- Assumptions explicit
- Unknown unknowns and POC recommendations
```

**For Strategic Decisions (Strategy Agent):**
```
@emilio-strategy-agent "Evaluate $DECISION for $CONTEXT"

Analyze:
1. **Strategic alignment**: How each option supports goals
2. **Resource implications**: Cost, time, team requirements
3. **Risk/reward**: Upside vs downside per option
4. **Timing**: When to decide, cost of delay
5. **Reversibility**: Can we change course later?

Key outputs:
- RICE/ICE scoring matrix
- **Strategic trade-offs** (bolded)
- Resource requirements per option
- Risk assessment with mitigation
- Phase-gated rollout if applicable
- Kill criteria per path
```

**Validation:**
- Trade-offs made explicit
- Assumptions documented
- Risks identified with mitigation strategies

---

### Step 3: Synthesis & Recommendation (5-10 min)

**Agent:** @emilio-memory-agent

```
@emilio-memory-agent "Synthesize decision analysis for: $DECISION"

Integrate:
- Research findings (Step 1)
- Technical/strategic analysis (Step 2)
- Project context and constraints

Output format:
- **Recommendation** (what to choose + why)
- **Confidence Level** (High/Medium/Low)
- **Rationale** (decision logic)
- **Trade-offs** (what we gain/lose)
- **Assumptions** (what we're taking as given)
- **Unknown Unknowns** (validation needs)
- **Alternatives** (backup options if recommendation fails)
- **Next Steps** (actions to de-risk)

Save to: memory-system/decisions/[DECISION]-[DATE].md
```

---

## Success Criteria

- ✅ Options researched with cited evidence
- ✅ Technical/strategic implications analyzed
- ✅ Recommendation made with explicit confidence level
- ✅ Trade-offs documented (gain/loss per option)
- ✅ Assumptions and unknown unknowns flagged
- ✅ Alternative paths identified if recommendation fails
- ✅ Next steps defined to de-risk decision

---

## Output Format

### DECISION ANALYSIS
**Decision:** [Question being decided]
**Date:** [ISO format]
**Context:** [Project/domain]

### OPTIONS EVALUATED

| Option | Pros | Cons | Use Cases | Sources |
|--------|------|------|-----------|---------|
| **Option A** | ✓ Pro 1<br>✓ Pro 2 | ✗ Con 1 | Best when [X] | Author, 2024 |
| Option B | ✓ Pro 1 | ✗ Con 1<br>✗ Con 2 | Best when [Y] | URL |

### TECHNICAL/STRATEGIC ANALYSIS

#### Weighted Evaluation Matrix

| Criteria | Option A | Option B | Option C | Weight | Winner |
|----------|----------|----------|----------|--------|--------|
| Performance | 9/10 | 7/10 | 8/10 | 30% | A |
| Scalability | 7/10 | 9/10 | 8/10 | 25% | B |
| Developer Experience | 8/10 | 7/10 | 9/10 | 20% | C |
| Cost | 6/10 | 8/10 | 9/10 | 15% | C |
| Maturity | 9/10 | 7/10 | 6/10 | 10% | A |
| **Weighted Score** | **7.9** | **7.8** | **8.3** | | **C** |

### RECOMMENDATION

**Choice:** [Selected option]

**Rationale:**
[Why this choice makes sense given context and constraints]

**Confidence:** [High | Medium | Low]

**Trade-offs:**
- ✅ **Gains**: What we get
  - Benefit 1
  - Benefit 2
- ❌ **Losses**: What we give up
  - Limitation 1
  - Limitation 2

### ASSUMPTIONS
1. Assumption 1: [What we're taking as given]
2. Assumption 2: [Dependency or constraint]
3. **Validate by:** [How to test these assumptions]

### UNKNOWN UNKNOWNS
- **Technical blind spot**: [Area requiring POC or research]
- **Operational blind spot**: [Concern needing validation]
- **Cost blind spot**: [Hidden expense to investigate]

### ALTERNATIVE PATHS

**If recommendation fails:**
- **Pivot to Option B** if [trigger condition]
- **Fallback to Option C** if [fallback condition]

**Decision reversibility:**
- Can switch from A → B: [Yes/No + migration cost]
- Lock-in risks: [Vendor, data format, team expertise]

### RISK ASSESSMENT

| Risk | Probability | Impact | Mitigation |
|------|-------------|--------|------------|
| Technical risk 1 | Med | High | POC validation before commit |
| Operational risk 2 | Low | Med | Gradual rollout with monitoring |
| Cost risk 3 | High | Low | Set budget alert at $X |

### NEXT STEPS

#### Immediate (This Week)
- [ ] **Validate assumption X** via [method]
- [ ] **Build POC** for [risky component]
- [ ] **Get quote/pricing** for [cost uncertainty]

#### Decision Gate (Week 2)
- [ ] **Review POC results** - Proceed or pivot?
- [ ] **Final sign-off** from [stakeholder]
- [ ] **Implementation kickoff** if validated

### DECISION LOG (ADR)

**ADR-XXX:** [Decision title]
- **Date:** [ISO format]
- **Status:** Accepted
- **Context:** [Why this decision needed]
- **Decision:** [What was decided]
- **Consequences:** [Positive and negative impacts]
- **Confidence:** [Level]

---

## Example Usage

```bash
# Technical decision
@emilio-decision-framework "PostgreSQL vs MongoDB for ICIP pricing storage" --context=icip

# Strategic decision
@emilio-decision-framework "Should ICIP launch as standalone or Soracom-first?" --context=icip

# Tool/framework choice
@emilio-decision-framework "LangChain vs LlamaIndex for LuxenOS RAG" --context=luxenos

# Pricing strategy
@emilio-decision-framework "Freemium vs paid-only for ICIP go-to-market" --context=icip
```

---

## Agent Coordination

**Sequential execution:**
1. Research agent (evidence gathering)
2. Architecture/Strategy agent (analysis based on evidence)
3. Memory agent (synthesis and documentation)

**No parallel execution** - each phase depends on prior outputs

**Handoffs:**
- Research agent → provides evidence → Architecture/Strategy agent
- Architecture/Strategy agent → provides analysis → Memory agent
- Memory agent → synthesizes → produces decision artifact

---

## Decision Types & Agent Selection

| Decision Type | Primary Analyst | Focus |
|---------------|-----------------|-------|
| **Technical architecture** | emilio-architecture-agent | System design, integrations, scalability |
| **Strategic direction** | emilio-strategy-agent | Roadmap, prioritization, resource allocation |
| **Market/competitive** | emilio-research-agent alone | Evidence gathering without analysis agent |
| **Hybrid (tech + strategy)** | Both agents sequentially | Full analysis from both perspectives |

---

## Confidence Level Guide

### High Confidence (80%+ certainty)
- Multiple credible sources agree
- Similar use case validated in production
- Team has expertise with technology
- Low technical risk, proven approach

### Medium Confidence (50-80% certainty)
- Limited evidence or conflicting sources
- Novel use case, some unknowns
- Team learning curve moderate
- Medium technical risk with mitigation

### Low Confidence (<50% certainty)
- Weak evidence or no precedent
- Bleeding-edge technology
- Team has no experience
- High technical risk, needs POC first

---

## Troubleshooting

**Q: Research finds contradictory evidence**
- Action: Present both viewpoints, recommend POC to validate

**Q: Analysis reveals no clear winner**
- Action: Default to simplest/cheapest option, plan reversibility

**Q: Stakeholders disagree with recommendation**
- Action: Document their perspective, revisit assumptions, flag confidence level

**Q: Unknown unknowns dominate analysis**
- Action: Recommend time-boxed POC before final decision

---

**Last Updated:** 2025-10-22
