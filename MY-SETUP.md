# MY SETUP GUIDE

**How to customize this agent library for your personal workflow**

---

## TABLE OF CONTENTS

1. [Adding Custom Agents](#adding-custom-agents)
2. [Modifying Existing Agents](#modifying-existing-agents)
3. [Creating Project-Specific Configs](#creating-project-specific-configs)
4. [Integration Patterns](#integration-patterns)
5. [Best Practices](#best-practices)

---

## ADDING CUSTOM AGENTS

### Step 1: Choose the Right Location

**Option A: Create New Plugin (Recommended for domain-specific agents)**
```bash
mkdir -p plugins/my-custom-plugin/agents
mkdir -p plugins/my-custom-plugin/commands
mkdir -p plugins/my-custom-plugin/skills
```

**Option B: Add to Existing Plugin (For extensions of existing domains)**
```bash
# Add to existing plugin directory
cd plugins/python-development/agents
# Create your custom agent file
```

**Option C: Use Custom Directory (Easiest for personal agents)**
```bash
# Already created in this repo:
plugins/custom/agents/
plugins/custom/workflows/
```

### Step 2: Follow the Agent Template Pattern

**Frontmatter Structure (YAML):**
```yaml
---
name: agent-name
description: Brief one-line description. Use PROACTIVELY when [activation criteria].
model: sonnet  # or opus, haiku
---
```

**Full Agent Template:**
```markdown
---
name: my-custom-agent
description: Expert in [domain] specializing in [capabilities]. Masters [key skills]. Use PROACTIVELY when [trigger condition].
model: sonnet
---

You are a [role description] specializing in [domain].

## Purpose
[Detailed purpose statement - what this agent does and why it exists]

## Core Philosophy
[Guiding principles this agent follows]

## Capabilities

### Category 1
- **Skill 1**: Description, use cases, patterns
- **Skill 2**: Description, tools, frameworks
- **Skill 3**: Description, best practices

### Category 2
[Continue organizing capabilities into logical categories]

## Behavioral Traits
- [How agent approaches problems]
- [Key decision-making patterns]
- [What agent prioritizes]
- [When agent defers to other specialists]

## Workflow Position
- **After**: [which agents should run before this one]
- **Complements**: [which agents work alongside this one]
- **Enables**: [what this agent makes possible]

## Knowledge Base
- [Domain knowledge area 1]
- [Domain knowledge area 2]
- [Domain knowledge area 3]

## Response Approach
1. **Step 1**: [First action]
2. **Step 2**: [Second action]
3. **Step 3**: [Third action]
[Continue with numbered workflow steps]

## Example Interactions
- "Example user request 1"
- "Example user request 2"
- "Example user request 3"

## Key Distinctions
- **vs other-agent**: [How this agent differs]
- **vs another-agent**: [Specialization boundaries]

## Output Examples
When [doing task], provide:
- [Output element 1]
- [Output element 2]
- [Output element 3]
```

### Step 3: Choose the Right Model Tier

**Opus (Advanced/Expensive):**
- Complex architectural decisions
- Strategic planning
- Critical incident response
- Data modeling from scratch

**Sonnet (Balanced/Recommended for most agents):**
- Core development tasks
- Code review and analysis
- Implementation and refactoring
- 90% of use cases

**Haiku (Fast/Cheap):**
- Test generation
- Quick validation
- Deterministic tasks
- Batch operations

### Step 4: Write Clear Activation Criteria

**Good Activation Descriptions:**
✅ "Use PROACTIVELY when creating new backend services or APIs"
✅ "Use when designing database schemas from scratch"
✅ "Use PROACTIVELY for code review before merging"

**Bad Activation Descriptions:**
❌ "Use when you need help" (too vague)
❌ "General purpose agent" (no clear trigger)
❌ "Can help with anything" (not specific)

### Step 5: Register Agent in Marketplace (Optional)

**Edit `.claude-plugin/marketplace.json`:**
```json
{
  "my-custom-plugin": {
    "name": "My Custom Plugin",
    "description": "Personal agents for [domain]",
    "version": "1.0.0",
    "agents": ["my-custom-agent"],
    "commands": [],
    "skills": []
  }
}
```

---

## MODIFYING EXISTING AGENTS

### Option 1: Fork and Customize (Recommended)

**Preserve originals, create custom versions:**
```bash
# Copy existing agent
cp plugins/backend-development/agents/backend-architect.md \
   plugins/custom/agents/emilio-backend-architect.md

# Modify your copy
vim plugins/custom/agents/emilio-backend-architect.md
```

**Add your preferences to the copy:**
- Custom output format (tables, hierarchies)
- Confidence levels on recommendations
- Explicit assumptions section
- "Unknown unknowns" awareness
- Bold key insights

### Option 2: Override via Project Config (Advanced)

**Create project-specific agent behavior:**
```yaml
# config/projects/my-project.yaml
agents:
  backend-architect:
    additional_instructions: |
      When responding:
      - Use tables for comparisons
      - Add confidence levels (High/Medium/Low)
      - List explicit assumptions
      - Highlight unknown unknowns
      - **Bold** key insights

    output_format:
      structure: "hierarchical"
      use_tables: true
      confidence_scoring: true
```

### Option 3: Agent Skills Override

**Create custom skill to modify behavior:**
```markdown
# plugins/custom/skills/emilio-output-format/SKILL.md
---
name: emilio-output-format
description: Personal output formatting preferences
tier: metadata
---

# Output Format Preferences

## Structure
- Use hierarchical organization
- Compress information into tables
- Add visual hierarchy with markdown

## Confidence Levels
- Add confidence: High/Medium/Low
- Flag uncertain recommendations
- Separate "known" from "assumed"

## Key Insights
- **Bold** critical insights
- Use `inline code` for technical terms
- Add 🎯 emoji for action items

## Unknown Unknowns
Always include "Potential blind spots:" section
```

---

## CREATING PROJECT-SPECIFIC CONFIGS

### Config File Structure

```yaml
# config/projects/my-project.yaml
project:
  name: "My Project Name"
  description: "Project description"
  domain: "backend|frontend|fullstack|data|infrastructure"

# Default agents for this project
default_agents:
  - backend-architect
  - database-architect
  - python-pro
  - test-automator

# Agent behavior overrides
agents:
  backend-architect:
    additional_instructions: |
      Specific instructions for this project context
    preferred_frameworks:
      - FastAPI
      - PostgreSQL
      - Redis

  database-architect:
    constraints:
      - Must use PostgreSQL
      - Must support multi-tenancy
      - Must handle 10K+ concurrent users

# Project-specific workflows
workflows:
  feature-development:
    steps:
      - agent: database-architect
        action: "design schema changes"
      - agent: backend-architect
        action: "implement API endpoints"
      - agent: test-automator
        action: "generate integration tests"
      - agent: security-auditor
        action: "security review"

# Context preferences
context:
  max_tokens: 8000
  include_files:
    - "src/**/*.py"
    - "tests/**/*.py"
  exclude_patterns:
    - "*/migrations/*"
    - "*/venv/*"

# Output preferences (applied to all agents)
output:
  format: "structured"
  use_tables: true
  confidence_levels: true
  bold_insights: true
  unknown_unknowns_section: true
```

### Project Config Examples

**LuxenOS Config (`config/projects/luxenos.yaml`):**
```yaml
project:
  name: "LuxenOS"
  description: "Personal AI memory and orchestration system"
  domain: "ai-infrastructure"

default_agents:
  - llm-application-architect
  - python-pro
  - rag-specialist
  - agent-orchestrator
  - database-architect

agents:
  llm-application-architect:
    focus_areas:
      - Sovereign memory architecture
      - Multi-agent orchestration
      - RAG with vector databases
      - Append-only logging patterns

  python-pro:
    preferred_patterns:
      - async/await for all I/O
      - Pydantic for data validation
      - FastAPI for APIs
      - pytest for testing

workflows:
  memory_integration:
    steps:
      - agent: rag-specialist
        action: "design vector database schema"
      - agent: python-pro
        action: "implement embedding pipeline"
      - agent: llm-application-architect
        action: "design retrieval strategy"
      - agent: test-automator
        action: "generate tests"

output:
  format: "compressed_hierarchical"
  confidence_levels: true
  unknown_unknowns: true
  bold_insights: true
```

**ICIP Config (`config/projects/icip.yaml`):**
```yaml
project:
  name: "ICIP"
  description: "IoT Cost Intelligence Platform"
  domain: "fullstack-saas"

default_agents:
  - backend-architect
  - database-architect
  - frontend-developer
  - react-expert
  - test-automator

agents:
  database-architect:
    constraints:
      - PostgreSQL with JSONB for pricing flexibility
      - Client-side calculation + server validation
      - Scenario versioning for iterations

  backend-architect:
    focus_areas:
      - RESTful API design
      - JSONB for flexible pricing data
      - Manual override support
      - CSV export functionality

workflows:
  feature_development:
    steps:
      - agent: database-architect
        action: "design schema"
      - agent: backend-architect
        action: "implement API"
      - agent: react-expert
        action: "build UI components"
      - agent: test-automator
        action: "generate tests"
      - agent: security-auditor
        action: "security audit"

context:
  key_files:
    - "src/components/**/*.tsx"
    - "src/api/**/*.ts"
    - "prisma/schema.prisma"

output:
  format: "structured_with_tables"
  confidence_levels: true
  alternatives_section: true  # Show rejected alternatives
```

---

## INTEGRATION PATTERNS

### Pattern 1: Session Start with Project Load

**Create session initialization command:**
```bash
# .claude/commands/load-project.md
Load project configuration for $ARGS and activate default agents.

Steps:
1. Read config/projects/$ARGS.yaml
2. Load default_agents list
3. Apply agent behavior overrides
4. Set output preferences
5. Display loaded configuration
```

**Usage:**
```bash
/load-project luxenos
# → Loads LuxenOS config, activates agents, applies preferences
```

### Pattern 2: Agent Chaining with Project Context

**Create workflow that uses project config:**
```bash
# workflows/custom/emilio-project-kickoff.md
---
name: emilio-project-kickoff
description: Initialize new feature with project-aware agents
---

# Project Kickoff Workflow

## Steps

1. **Load Project Config**
   - Read current project configuration
   - Identify relevant agents
   - Apply context preferences

2. **Architecture Planning** (@database-architect + @backend-architect)
   - Design data layer (database-architect)
   - Design API layer (backend-architect)
   - Consider project constraints

3. **Strategy Definition** (@emilio-strategy-agent)
   - Define success metrics
   - Identify risks
   - Create roadmap

4. **Research Phase** (@emilio-research-agent)
   - Technical feasibility analysis
   - Competitive analysis
   - Technology recommendations
```

### Pattern 3: Context-Aware Agent Activation

**Project-specific agent routing:**
```yaml
# config/projects/luxenos.yaml
agent_routing:
  # When user mentions "memory", auto-activate these agents
  keywords:
    memory:
      - rag-specialist
      - database-architect
      - llm-application-architect

    orchestration:
      - agent-orchestrator
      - python-pro

    api:
      - backend-architect
      - fastapi-pro
```

### Pattern 4: Workflow Orchestration with Configs

**Use project configs in workflows:**
```bash
/custom:emilio-decision-framework "Should we use PostgreSQL or MongoDB?"
```

**Workflow reads project config:**
```markdown
# workflows/custom/emilio-decision-framework.md
1. **Research** (@emilio-research-agent)
   - Gather pros/cons for each option
   - Consider project constraints from config

2. **Analysis** (@backend-architect + @database-architect)
   - Technical evaluation
   - Scale/performance considerations
   - Apply project-specific requirements

3. **Recommendation** (@emilio-strategy-agent)
   - Confidence level: High/Medium/Low
   - Explicit assumptions
   - Unknown unknowns
   - **Key insight** with rationale
```

---

## BEST PRACTICES

### ✅ DO

1. **Preserve Originals**
   - Never modify original agent files
   - Create copies in `plugins/custom/` for modifications
   - Use git to track your customizations

2. **Clear Activation Criteria**
   - Be specific about when agent should activate
   - Use "PROACTIVELY" for auto-activation
   - Define clear boundaries with other agents

3. **Model Selection**
   - Use Sonnet for 90% of agents (balanced performance)
   - Use Opus only for complex reasoning (expensive)
   - Use Haiku for fast, deterministic tasks

4. **Progressive Disclosure**
   - Put frequently used info in main agent file
   - Move detailed examples to skills
   - Use three-tier structure: metadata → instructions → resources

5. **Project Configs**
   - One config per major project
   - Include default agents list
   - Define output preferences centrally
   - Version control your configs

6. **Agent Deference**
   - Make agents defer to specialists
   - Clear workflow position (before/after/complements)
   - Avoid overlapping responsibilities

### ❌ DON'T

1. **Don't Modify Original Files**
   - You'll lose changes on updates
   - Hard to track what you customized
   - Use custom directory instead

2. **Don't Create Generic Agents**
   - "Helper agent" or "utility agent" → too vague
   - Single responsibility principle
   - Specific domain focus

3. **Don't Overuse Opus Model**
   - Expensive and slower
   - Reserve for complex decisions only
   - Sonnet handles 90% of tasks well

4. **Don't Duplicate Existing Agents**
   - Check catalog first
   - Extend existing agents via skills
   - Use project configs to modify behavior

5. **Don't Forget Output Preferences**
   - Add your formatting preferences
   - Specify confidence levels
   - Request unknown unknowns section

---

## MAINTENANCE & UPDATES

### Keeping Custom Agents in Sync

```bash
# Update original repository
cd ~/.claude/plugins/repos/agents
git pull origin main

# Your custom agents are preserved (not tracked by git)
ls plugins/custom/agents/  # Your files safe
ls config/projects/        # Your configs safe
```

### Version Control Your Customizations

```bash
# Create separate git repo for your customizations
cd ~/.claude/plugins/repos/agents
git init custom-repo
git add plugins/custom/
git add config/projects/
git add agents-catalog.md agents-cheatsheet.md MY-SETUP.md
git commit -m "My personal agent library setup"
```

### Testing Custom Agents

**Test activation:**
```bash
# Test your agent activates correctly
"[trigger phrase from description]"
# Should invoke your custom agent

# Test explicit call
@my-custom-agent "task description"
```

**Test workflows:**
```bash
/custom:my-workflow "input"
# Verify agent sequence
# Check output format
```

---

## ADVANCED: AGENT SKILLS CREATION

### When to Create a Skill

**Create a skill when:**
- ✅ Knowledge is reusable across multiple agents
- ✅ Content is large (>500 lines)
- ✅ Information is specialized (not always needed)
- ✅ You want progressive disclosure

### Skill Template

```markdown
# plugins/custom/skills/my-skill/SKILL.md
---
name: my-skill-name
description: What this skill provides
tier: metadata|instructions|resources
---

# Skill Name

## When to Use
[Activation criteria]

## Core Knowledge

### Section 1
[Organized knowledge]

### Section 2
[Practical patterns]

## Examples
[Code examples, templates, patterns]

## Best Practices
[Guidelines and recommendations]
```

### Skill Tiers

**Tier 1 - Metadata (~50 lines, always loaded):**
- Skill name and activation criteria
- Quick reference, cheatsheet

**Tier 2 - Instructions (~200 lines, loaded when activated):**
- Core guidance and patterns
- Implementation details

**Tier 3 - Resources (loaded on-demand):**
- Detailed examples
- Templates and boilerplate
- Extended documentation

---

## QUICK START CHECKLIST

- [ ] Clone wshobson/agents repository
- [ ] Review agents-catalog.md for available agents
- [ ] Install essential plugins for your domain
- [ ] Create custom agents in `plugins/custom/agents/`
- [ ] Create workflows in `plugins/custom/workflows/`
- [ ] Create project configs in `config/projects/`
- [ ] Test custom agents and workflows
- [ ] Version control your customizations
- [ ] Update MY-SETUP.md with your learnings

---

## TROUBLESHOOTING

**Q: My custom agent doesn't activate**
- Check frontmatter is valid YAML
- Verify "description" has clear activation criteria
- Test with explicit call: `@my-agent "task"`

**Q: Agent uses wrong model tier**
- Check `model:` field in frontmatter
- Options: opus, sonnet, haiku (lowercase)

**Q: Project config not loading**
- Verify YAML syntax (use YAML validator)
- Check file location: `config/projects/[name].yaml`
- Test with explicit load command

**Q: Workflow doesn't chain agents correctly**
- Check agent names match exactly
- Verify agent dependencies (before/after/complements)
- Test each agent individually first

---

**Last Updated:** 2025-10-22

**Next:** Create your first custom agent using the template above!
