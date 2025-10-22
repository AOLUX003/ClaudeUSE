# Project Kickoff Workflow

**Multi-agent orchestration for new feature initialization with project-aware context**

## Overview

This workflow coordinates architecture, strategy, and research agents to kickstart new projects or major features with comprehensive planning and validated approach.

## Arguments

- `$FEATURE`: Feature/project description
- `$PROJECT`: Project context (luxenos|icip|sales-enablement|gap-analysis)

## Workflow Steps

### Step 1: Architecture Planning (15-20 min)

**Agents:** @emilio-architecture-agent + @database-architect

**Architecture Phase:**
```
@emilio-architecture-agent "Design system architecture for: $FEATURE"

Key outputs:
- High-level architecture diagram
- Component breakdown
- Technology recommendations with comparison matrix
- Integration patterns
- **Critical architectural decisions** (bolded)
- Confidence levels on each recommendation
- Assumptions and unknown unknowns
```

**Data Layer Design:**
```
@database-architect "Design database schema for: $FEATURE based on architecture"

Key outputs:
- Entity-relationship diagram
- Schema design with constraints
- Indexing strategy
- Migration approach
```

**Validation:**
- Architecture decisions documented in ADRs
- Trade-offs made explicit with rationale
- Unknown unknowns identified for validation

---

### Step 2: Strategy Definition (10-15 min)

**Agent:** @emilio-strategy-agent

```
@emilio-strategy-agent "Create phased roadmap for: $FEATURE"

Key outputs:
- Phase-gated plan (Crawl → Walk → Run)
- RICE/ICE prioritization of sub-features
- Success metrics per phase
- Resource requirements (budget, time, team)
- Risk assessment with mitigation strategies
- Kill criteria and pivot triggers
- **Strategic decisions** (bolded)
- Unknown unknowns and validation needs
```

**Validation:**
- Roadmap aligns with project constraints
- Riskiest assumptions identified for Phase 0 validation
- Clear gate criteria between phases

---

### Step 3: Research & Validation (15-20 min)

**Agent:** @emilio-research-agent

```
@emilio-research-agent "Research and validate: $FEATURE"

Focus areas:
1. **Competitive Analysis**: Similar products, differentiation opportunities
2. **Technical Feasibility**: Validate architecture assumptions
3. **Market Validation**: Customer need evidence, willingness to pay
4. **Technology Evaluation**: Confirm recommended stack choices
5. **Risk Assessment**: Validate identified risks, uncover new ones

Key outputs:
- Competitive positioning matrix
- Technology comparison with citations
- Market evidence (TAM/SAM, growth trends)
- Technical feasibility assessment
- **Key findings** (bolded)
- Confidence levels on all claims
- Sources cited (Author/Year or URL)
- Unknown unknowns requiring customer validation
```

**Validation:**
- All claims cited with sources
- Contradictory evidence surfaced
- Assumptions validated or flagged for testing

---

### Step 4: Integration & Synthesis (5-10 min)

**Agent:** @emilio-memory-agent

```
@emilio-memory-agent "Extract and consolidate project kickoff decisions"

Synthesize:
- Architecture decisions from Step 1
- Strategic roadmap from Step 2
- Research findings from Step 3

Output format:
- **Core Decisions** (what was decided + why)
- **Confidence Assessment** (High/Medium/Low per decision)
- **Assumptions** (explicit list)
- **Unknown Unknowns** (validation needs)
- **Action Items** (next steps with owners)
- **Open Questions** (unresolved issues)

Save to: memory-system/summaries/[PROJECT]-[FEATURE]-kickoff.md
```

---

## Success Criteria

- ✅ Architecture documented with ADRs and trade-offs explicit
- ✅ Database schema designed (or deferred to database-architect)
- ✅ Roadmap created with phase gates and kill criteria
- ✅ Research validates assumptions or flags for testing
- ✅ All decisions have confidence levels
- ✅ Unknown unknowns identified for each domain
- ✅ Memory artifact created for future reference

---

## Output Format

### PROJECT KICKOFF SUMMARY
**Project:** [Name]
**Feature:** [Description]
**Date:** [ISO format]

### ARCHITECTURE DECISIONS
1. **[Decision 1]** - [Rationale] | Confidence: [High/Medium/Low]
2. **[Decision 2]** - [Rationale] | Confidence: [High/Medium/Low]

### STRATEGIC ROADMAP
**Phase 0:** [Discovery] - [Timeline] - [Gate criteria]
**Phase 1:** [MVP] - [Timeline] - [Gate criteria]
**Phase 2:** [Validation] - [Timeline] - [Gate criteria]

### RESEARCH VALIDATION
**Competitive Position:** [Finding] | Confidence: [Level] | Source: [Citation]
**Technical Feasibility:** [Finding] | Confidence: [Level] | Source: [Citation]
**Market Evidence:** [Finding] | Confidence: [Level] | Source: [Citation]

### ASSUMPTIONS
- Assumption 1
- Assumption 2

### UNKNOWN UNKNOWNS
- **Architecture**: [Blind spot requiring validation]
- **Strategy**: [Risk requiring exploration]
- **Research**: [Gap requiring customer interviews]

### NEXT STEPS
- [ ] **Week 1**: [Action]
- [ ] **Week 2**: [Action]
- [ ] **Decision point**: [Date] - Proceed to Phase 1?

---

## Example Usage

```bash
# ICIP new feature
@emilio-project-kickoff "Multi-carrier comparison engine for ICIP" --project=icip

# LuxenOS capability
@emilio-project-kickoff "RAG-based memory retrieval for LuxenOS" --project=luxenos

# Sales content
@emilio-project-kickoff "ROI calculator for ICIP value demonstration" --project=sales-enablement
```

---

## Agent Coordination

**Sequential execution (dependencies):**
1. Architecture first (foundation for strategy and research)
2. Strategy second (roadmap depends on architecture complexity)
3. Research third (validates architecture and strategy assumptions)
4. Memory synthesis last (consolidates all prior outputs)

**Parallel opportunities:**
- Architecture + Database design (concurrent after architecture agent completes high-level)
- Strategy can start before database schema finalized

**Handoffs:**
- Architecture agent → Database architect (detailed schema)
- Architecture agent → Strategy agent (complexity informs timeline)
- Strategy agent → Research agent (roadmap assumptions to validate)
- All → Memory agent (synthesis and documentation)

---

## Project-Specific Customizations

### LuxenOS Projects
- Emphasize: RAG architecture, multi-agent orchestration, append-only logging
- Default agents: llm-application-architect, rag-specialist, agent-orchestrator
- Success metric: Sovereign memory with causal reasoning preservation

### ICIP Projects
- Emphasize: Client-side calc + server validation, JSONB flexibility, scenario versioning
- Default agents: database-architect, backend-architect, react-expert
- Success metric: Accurate forecasting with manual override support

### Sales Enablement Projects
- Emphasize: Value quantification, competitive positioning, objection handling
- Default agents: sales-engineer, business-analyst, content-strategist
- Success metric: ROI-driven collateral enabling customer conversations

---

## Troubleshooting

**Q: Agents produce conflicting recommendations**
- Resolution: Memory agent synthesizes, flags conflicts explicitly, defers to specialist (e.g., database-architect over emilio-architecture-agent for schema)

**Q: Workflow takes longer than estimated**
- Mitigation: Time-box each phase, use "quick pass" for initial kickoff, deep dive later

**Q: Unknown unknowns section empty**
- Action: Prompt agents explicitly: "What assumptions are we making? What blind spots exist?"

---

**Last Updated:** 2025-10-22
