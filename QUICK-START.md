# QUICK START GUIDE

**Get productive with this agent library in under 10 minutes**

---

## STEP 1: ADD THE MARKETPLACE (30 seconds)

```bash
/plugin marketplace add wshobson/agents
```

This makes all 63 plugins + your custom agents available (but doesn't load anything yet).

---

## STEP 2: INSTALL ESSENTIAL PLUGINS (2 minutes)

**Choose your primary domain:**

### For Backend Development
```bash
/plugin install python-development
/plugin install backend-development
/plugin install database-design
```
**Loaded:** python-pro, backend-architect, database-architect + 5 Python skills

### For Frontend Development
```bash
/plugin install javascript-typescript
/plugin install multi-platform-apps
/plugin install application-performance
```
**Loaded:** typescript-pro, react-expert, frontend-developer + 4 JS/TS skills

### For Full-Stack Development
```bash
/plugin install full-stack-orchestration
/plugin install backend-development
/plugin install javascript-typescript
```
**Loaded:** backend-architect, frontend-developer, database-architect + workflow orchestrators

### For DevOps & Infrastructure
```bash
/plugin install kubernetes-operations
/plugin install cloud-infrastructure
/plugin install cicd-automation
```
**Loaded:** kubernetes-architect, cloud-architect, deployment-engineer + 4 K8s skills

---

## STEP 3: VERIFY INSTALLATION (30 seconds)

```bash
/plugin
```

You should see your installed plugins listed. Each plugin shows its agents, commands, and skills.

---

## STEP 4: TEST AGENT INVOCATION (1 minute)

### Explicit Agent Call
```bash
@python-pro "Create async FastAPI endpoint for user authentication"
```

### Natural Language (Agent Auto-Activates)
```bash
"I need to design a microservices architecture for e-commerce platform"
```
→ backend-architect auto-activates

### Workflow Orchestration
```bash
/full-stack-orchestration:full-stack-feature "user authentication with OAuth2"
```
→ Coordinates 7+ agents automatically

---

## STEP 5: USE CUSTOM AGENTS (1 minute)

Your custom agents are already available! Test them:

```bash
@emilio-memory-agent "Extract strategic insights from this conversation about LuxenOS"
```

```bash
@emilio-research-agent "Competitive analysis: ICIP vs existing IoT cost tools"
```

```bash
@emilio-strategy-agent "Create phased roadmap for multi-carrier ICIP expansion"
```

---

## STEP 6: LOAD PROJECT CONTEXT (Optional, 2 minutes)

Create a command to load your project configuration:

**Create:** `.claude/commands/load-project.md`
```markdown
Load project configuration for $ARGS.

Steps:
1. Read config/projects/$ARGS.yaml
2. Activate default agents
3. Apply output preferences
4. Show loaded configuration
```

**Usage:**
```bash
/load-project luxenos
# Loads LuxenOS context, activates llm-application-architect, python-pro, etc.
```

---

## COMMON USAGE PATTERNS

### Pattern 1: New Feature Development

```bash
# Step 1: Architecture
@database-architect "Design schema for user authentication system"

# Step 2: Backend
@backend-architect "Design RESTful API for auth based on schema"

# Step 3: Frontend
@react-expert "Create login/signup components with form validation"

# Step 4: Testing
@test-automator "Generate integration tests for auth flow"

# Step 5: Security
@security-auditor "Security review of authentication implementation"
```

### Pattern 2: Code Review

```bash
# Parallel review (all run simultaneously)
"Review this code for quality, security, and performance"
→ code-reviewer + security-auditor + performance-engineer
```

### Pattern 3: Research & Decision

```bash
# Sequential workflow
@emilio-research-agent "Research PostgreSQL vs MongoDB for flexible pricing data"
@emilio-architecture-agent "Evaluate options based on ICIP requirements"
@emilio-strategy-agent "Recommend choice with confidence level and trade-offs"
```

### Pattern 4: Production Issue

```bash
@incident-responder "Production down: 500 errors on /api/users endpoint"
# Follow up with:
@devops-troubleshooter "Analyze logs for root cause"
@observability-engineer "Add monitoring to prevent recurrence"
```

---

## CUSTOM WORKFLOWS

### Project Kickoff
```bash
@emilio-project-kickoff "RAG-based memory retrieval for LuxenOS" --project=luxenos
```
→ Coordinates: architecture-agent → strategy-agent → research-agent → memory-agent

### Decision Framework
```bash
@emilio-decision-framework "PostgreSQL vs MongoDB for ICIP" --context=icip
```
→ Coordinates: research-agent → architecture-agent → memory-agent (synthesis)

### Content Creation
```bash
@emilio-content-creation blog-post "How ICIP saves IoT companies $50K/year" technical-buyer
```
→ Coordinates: research-agent → sales-agent → seo-writer → memory-agent

---

## NAVIGATION SHORTCUTS

### Find Agents by Domain
```bash
# See agents-catalog.md for full list organized by category
```

| Domain | Key Agents | Use Case |
|--------|------------|----------|
| **Architecture** | backend-architect, database-architect, cloud-architect | System design |
| **Development** | python-pro, typescript-pro, react-expert | Core coding |
| **Quality** | code-reviewer, security-auditor, test-automator | Code quality |
| **DevOps** | deployment-engineer, kubernetes-architect | Infrastructure |
| **Custom** | emilio-memory-agent, emilio-research-agent, emilio-strategy-agent | Personal workflow |

### Find by Use Case
```bash
# See agents-cheatsheet.md for top 20 agents + quick invocations
```

**Common scenarios:**
- New backend API → @backend-architect
- Database design → @database-architect (before backend-architect)
- Code review → @code-reviewer
- Production incident → @incident-responder
- Competitive research → @emilio-research-agent
- Strategic planning → @emilio-strategy-agent

---

## OUTPUT FORMAT CUSTOMIZATION

All custom agents include Emilio's preferences by default:

✅ **Compressed hierarchical structure** - Maximum information density
✅ **Tables for comparisons** - Matrix format for alternatives
✅ **Confidence levels** - High/Medium/Low on every recommendation
✅ **Explicit assumptions** - Separate "known" from "assumed"
✅ **Unknown unknowns section** - ALWAYS included
✅ **Bold key insights** - **Most important points highlighted**
✅ **Action-oriented** - Clear next steps

---

## TROUBLESHOOTING

### Q: Agent doesn't activate
**Check:**
- Agent name spelled correctly (@python-pro not @python)
- Plugin installed (/plugin to verify)
- Try explicit call: @agent-name "task"

### Q: Wrong model tier (too slow/expensive)
**Solution:**
- Most agents use Sonnet (balanced)
- Opus for complex reasoning (database-architect, cloud-architect)
- Haiku for fast tasks (test-automator)
- Check agents-catalog.md for model assignments

### Q: Context window exceeded
**Solutions:**
- Use @context-manager to compress
- Load only relevant files
- Use skills (progressive disclosure)
- Check project config context settings

### Q: Project config not loading
**Check:**
- File exists: config/projects/[name].yaml
- YAML syntax valid (use validator)
- Load command created correctly

---

## NEXT STEPS

1. **Browse catalog**: Read `agents-catalog.md` to see all 85+ agents
2. **Check cheatsheet**: Read `agents-cheatsheet.md` for top 20 agents
3. **Customize setup**: Read `MY-SETUP.md` to create your own agents
4. **Load project**: Test project configs with `/load-project`
5. **Practice workflows**: Try custom workflows (project-kickoff, decision-framework)

---

## RESOURCES

### In This Repository
- **agents-catalog.md** - All 85+ agents organized by domain
- **agents-cheatsheet.md** - Top 20 agents + quick invocations
- **MY-SETUP.md** - How to create custom agents and configs
- **config/projects/** - Project configuration templates
- **plugins/custom/agents/** - Your 5 custom agents
- **plugins/custom/workflows/** - Your 3 custom workflows

### Official Documentation
- [Claude Code Documentation](https://docs.claude.com/en/docs/claude-code/overview)
- [Plugins Guide](https://docs.claude.com/en/docs/claude-code/plugins)
- [Subagents Guide](https://docs.claude.com/en/docs/claude-code/sub-agents)
- [Agent Skills Guide](https://docs.claude.com/en/docs/agents-and-tools/agent-skills/overview)

### wshobson/agents Repository
- [Plugin Reference](docs/plugins.md) - 63 focused plugins
- [Agent Reference](docs/agents.md) - 85 agents with model tiers
- [Agent Skills Guide](docs/agent-skills.md) - 47 specialized skills
- [Usage Guide](docs/usage.md) - Commands and workflows
- [Architecture](docs/architecture.md) - Design principles

---

## QUICK REFERENCE CARD

```
INSTALLATION
/plugin marketplace add wshobson/agents
/plugin install [plugin-name]
/plugin (list installed)

INVOCATION
@agent-name "task"                    # Explicit call
"natural language description"        # Auto-activation
/plugin:command [args]                # Workflow

CUSTOM AGENTS
@emilio-memory-agent      # Conversation continuity, decision tracking
@emilio-research-agent    # Competitive/market/technical research
@emilio-strategy-agent    # Planning, prioritization, roadmaps
@emilio-sales-agent       # Sales enablement, value props, positioning
@emilio-architecture-agent # System design, integrations, scalability

CUSTOM WORKFLOWS
@emilio-project-kickoff         # Architecture → strategy → research
@emilio-decision-framework      # Research → analysis → recommendation
@emilio-content-creation        # Research → strategy → writing

PROJECT CONFIGS
/load-project luxenos           # LuxenOS memory system
/load-project icip              # IoT cost platform
/load-project sales-enablement  # B2B sales content
/load-project gap-analysis      # AI-Human Gap taxonomy

MODEL TIERS
Opus   - Complex reasoning (database-architect, cloud-architect)
Sonnet - 90% of agents (balanced performance)
Haiku  - Fast execution (test-automator)
```

---

**You're ready to go! Start with the agents that match your current work and explore from there.**

**Last Updated:** 2025-10-22
