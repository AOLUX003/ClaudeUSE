# Agents Cheatsheet

**Quick reference for the 20 most useful agents** + common invocation patterns

---

## TOP 20 ESSENTIAL AGENTS

### 🏗️ Architecture & Design (6)

| # | Agent | Model | When to Use | Quick Invocation |
|---|-------|-------|-------------|------------------|
| 1 | **backend-architect** | sonnet | New APIs, microservices, distributed systems | "Design RESTful API for [feature]" |
| 2 | **database-architect** | opus | Data modeling, schema design (use BEFORE backend) | "Design database schema for [domain]" |
| 3 | **cloud-architect** | opus | Infrastructure planning, AWS/Azure/GCP | "Design cloud infrastructure for [system]" |
| 4 | **frontend-developer** | sonnet | React/Vue/Angular components, client-side logic | "Build responsive UI for [feature]" |
| 5 | **kubernetes-architect** | opus | Container orchestration, cloud-native design | "Create K8s deployment for [service]" |
| 6 | **llm-application-architect** | opus | LLM products, RAG systems, prompt workflows | "Design LLM application with RAG for [use case]" |

### 💻 Core Development (6)

| # | Agent | Model | When to Use | Quick Invocation |
|---|-------|-------|-------------|------------------|
| 7 | **python-pro** | sonnet | Python development, async, optimization | "Implement [feature] in Python with async" |
| 8 | **typescript-pro** | sonnet | TypeScript, advanced types, generics | "Add TypeScript types for [module]" |
| 9 | **react-expert** | sonnet | React hooks, context, performance | "Optimize React component [name]" |
| 10 | **fastapi-pro** | sonnet | FastAPI backends, async endpoints, Pydantic | "Create FastAPI endpoint for [feature]" |
| 11 | **nextjs-expert** | sonnet | Next.js SSR/SSG, App Router, server components | "Build Next.js page with SSR for [feature]" |
| 12 | **sql-pro** | sonnet | Complex queries, optimization, indexing | "Optimize query for [operation]" |

### 🔍 Quality & Security (4)

| # | Agent | Model | When to Use | Quick Invocation |
|---|-------|-------|-------------|------------------|
| 13 | **code-reviewer** | sonnet | General code review, best practices | "Review this code for improvements" |
| 14 | **security-auditor** | sonnet | Security vulnerabilities, OWASP Top 10 | "Audit security for [component]" |
| 15 | **test-automator** | haiku | Fast test generation, coverage | "Generate tests for [function/class]" |
| 16 | **performance-engineer** | sonnet | Performance optimization, profiling | "Profile and optimize [feature]" |

### 🚀 Operations & DevOps (4)

| # | Agent | Model | When to Use | Quick Invocation |
|---|-------|-------|-------------|------------------|
| 17 | **devops-troubleshooter** | sonnet | Production issues, deployment problems | "Debug deployment failure for [service]" |
| 18 | **deployment-engineer** | sonnet | CI/CD pipelines, Docker, cloud deployment | "Create CI/CD pipeline for [project]" |
| 19 | **incident-responder** | opus | Critical production outages | "Help resolve production incident: [issue]" |
| 20 | **observability-engineer** | sonnet | Monitoring, logging, distributed tracing | "Add observability to [service]" |

---

## COMMON INVOCATION PATTERNS

### Pattern 1: Explicit Agent Call
```
@backend-architect Design RESTful API for order management system
```

### Pattern 2: Natural Language (Agent Auto-Detected)
```
"I need to design a microservices architecture for e-commerce platform"
→ backend-architect auto-activates
```

### Pattern 3: Workflow Orchestration
```
/full-stack-orchestration:full-stack-feature "user authentication with OAuth2"
→ Coordinates: backend-architect → database-architect → frontend-developer → test-automator → security-auditor
```

### Pattern 4: Multi-Agent Parallel
```
"Review this code for quality, security, and performance"
→ code-reviewer + security-auditor + performance-engineer (run simultaneously)
```

### Pattern 5: Sequential Pipeline
```
Step 1: @database-architect design schema
Step 2: @backend-architect build API on schema
Step 3: @frontend-developer create UI
Step 4: @test-automator generate tests
```

---

## SCENARIO-BASED QUICK COMMANDS

### 🆕 Starting a New Project

```bash
# Backend API Project
@database-architect "Design database for [domain]"
@backend-architect "Design RESTful API based on schema"
@deployment-engineer "Setup CI/CD for FastAPI project"

# Frontend App Project
@frontend-developer "Create React app structure for [feature]"
@react-expert "Setup state management with Context"
@performance-engineer "Optimize initial load time"

# Full-Stack Project
/full-stack-orchestration:full-stack-feature "[feature description]"
```

### 🐛 Debugging Production Issues

```bash
# Immediate Triage
@incident-responder "Production down: [error message]"

# Deep Analysis
@devops-troubleshooter "Analyze logs for [service]"
@observability-engineer "Add tracing to identify bottleneck"
@performance-engineer "Profile and fix performance issue"

# Database Issues
@database-optimizer "Query taking 10s+ to execute: [query]"
@database-admin "Replication lag increasing - diagnose"
```

### 🔒 Security Hardening

```bash
# Pre-Production Audit
@security-auditor "Comprehensive security audit"
@penetration-tester "Test for vulnerabilities"
@compliance-specialist "Verify GDPR compliance"

# API Security
@api-security-expert "Add OAuth2 authentication"
@backend-architect "Implement rate limiting and API throttling"

# Frontend Security
@frontend-security-specialist "Prevent XSS and CSRF attacks"
```

### ✅ Code Quality & Testing

```bash
# Code Review
@code-reviewer "Review recent changes"
@security-auditor "Security review of [module]"
@performance-engineer "Performance review of [component]"

# Test Generation
@test-automator "Generate unit tests for [class]"
@integration-tester "Create integration tests for API"
@load-tester "Design load test for [endpoint]"

# TDD Workflow
@tdd-coach "Guide TDD implementation for [feature]"
```

### 📊 Data & AI Development

```bash
# LLM Application
@llm-application-architect "Design RAG system for [use case]"
@rag-specialist "Implement vector search with Pinecone"
@prompt-engineer "Optimize prompts for [task]"

# Data Pipeline
@data-engineer "Design ETL pipeline for [source] to [destination]"
@ml-engineer "Train model for [prediction task]"
@mlops-specialist "Deploy model with monitoring"

# Multi-Agent System
@agent-orchestrator "Design multi-agent workflow for [task]"
```

### 🏗️ Infrastructure & DevOps

```bash
# Kubernetes Deployment
@kubernetes-architect "Create production K8s deployment"
@deployment-engineer "Setup Helm charts and GitOps"
@observability-engineer "Add Prometheus + Grafana monitoring"

# Cloud Migration
@cloud-architect "Design AWS architecture for [system]"
@terraform-specialist "Create Terraform modules"
@deployment-engineer "Implement blue-green deployment"

# CI/CD Setup
@deployment-engineer "Create GitHub Actions pipeline"
@security-auditor "Add security scanning to CI/CD"
@test-automator "Integrate automated tests"
```

### 📝 Documentation & Content

```bash
# Technical Documentation
@technical-writer "Document API usage for [endpoint]"
@api-documenter "Generate OpenAPI spec"
@diagram-generator "Create architecture diagram"

# SEO Content
@seo-writer "Write SEO-optimized blog post about [topic]"
@technical-seo-specialist "Audit site for Core Web Vitals"
@content-strategist "Plan content calendar for Q1"
```

---

## AGENT SKILL ACTIVATION

### Skills Auto-Load When Needed

**Python Development:**
```
@python-pro "Create async FastAPI service"
→ Auto-activates: async-python-patterns, python-testing-patterns, uv-package-manager
```

**Kubernetes:**
```
@kubernetes-architect "Deploy microservice to K8s"
→ Auto-activates: k8s-manifests, helm-charts, gitops-patterns, k8s-security
```

**Backend Architecture:**
```
@backend-architect "Design RESTful API"
→ Auto-activates: api-design, architecture-patterns, microservices-patterns
```

**LLM Applications:**
```
@llm-application-architect "Build RAG chatbot"
→ Auto-activates: langchain-patterns, prompt-engineering, rag-architecture, evaluation-frameworks
```

---

## CHEAT CODE PHRASES

### Architecture Decisions
- "Design from scratch" → Uses **opus** tier (database-architect, cloud-architect)
- "Optimize existing" → Uses **sonnet** tier (performance-engineer, refactoring-specialist)
- "Quick implementation" → Uses **haiku** tier (test-automator, integration-tester)

### Quality Gates
- "Review before merging" → code-reviewer (proactive activation)
- "Security audit before prod" → security-auditor + penetration-tester
- "Performance baseline" → performance-engineer + load-tester

### Emergency Response
- "Production outage" → incident-responder (opus) → devops-troubleshooter
- "Security breach" → security-auditor + penetration-tester + compliance-specialist
- "Data corruption" → database-admin + database-optimizer

---

## MODEL TIER SELECTION GUIDE

### Use Opus (Advanced) When:
- ✅ Designing new system architecture from scratch
- ✅ Making critical architectural decisions
- ✅ Responding to production incidents
- ✅ Complex data modeling and schema design

**Agents:** database-architect, cloud-architect, incident-responder, llm-application-architect

### Use Sonnet (Balanced) For:
- ✅ 90% of development tasks
- ✅ Code review and refactoring
- ✅ API development and implementation
- ✅ Security audits and quality checks

**Agents:** Most agents use Sonnet

### Use Haiku (Fast) For:
- ✅ Test generation at scale
- ✅ Quick analysis and validation
- ✅ Batch operations and deterministic tasks

**Agents:** test-automator, integration-tester

---

## WORKFLOW ORCHESTRATION SHORTCUTS

### Pre-Configured Workflows

```bash
# Full-Stack Feature
/full-stack-orchestration:full-stack-feature "[description]"
→ 7-agent workflow: backend → database → frontend → test → security → deployment → observability

# Security Hardening
/security-scanning:security-hardening --level comprehensive
→ Multi-agent security: SAST → dependency scan → code review → penetration test

# Python Project Scaffold
/python-development:python-scaffold fastapi-microservice
→ Creates project + activates: async-python-patterns + python-testing-patterns + uv-package-manager

# Kubernetes Production Deployment
"Create production Kubernetes deployment with Helm chart and GitOps"
→ kubernetes-architect + activates: k8s-manifests + helm-charts + gitops-patterns + k8s-security
```

---

## CONTEXT WINDOW OPTIMIZATION

### When Dealing with Large Codebases

```bash
# Use Context Manager
@context-manager "Compress context for [large file]"

# Progressive Disclosure with Skills
- Skills load ONLY when activated (minimal token usage)
- Metadata always loaded (~50 lines)
- Instructions loaded when agent activated (~200 lines)
- Resources loaded on-demand (examples, templates)
```

---

## QUICK TIPS

1. **Proactive Activation**: backend-architect and code-reviewer activate without explicit call
2. **Agent Deference**: backend-architect defers database schema to database-architect
3. **Sequential Workflows**: database-architect → backend-architect → frontend-developer
4. **Parallel Review**: code-reviewer + security-auditor + performance-engineer (simultaneously)
5. **Model Optimization**: Opus for planning → Sonnet for execution → Haiku for testing
6. **Skill Efficiency**: Skills use progressive disclosure (3-tier: metadata → instructions → resources)
7. **Granular Installation**: Install only needed plugins (average 3.4 components per plugin)

---

## EMERGENCY QUICK REFERENCE

| Emergency | First Response | Follow-Up |
|-----------|----------------|-----------|
| **Site Down** | incident-responder | devops-troubleshooter → observability-engineer |
| **Security Breach** | security-auditor | penetration-tester → compliance-specialist |
| **Data Loss** | database-admin | database-optimizer → incident-responder |
| **Performance Crash** | performance-engineer | devops-troubleshooter → observability-engineer |
| **Deployment Failed** | deployment-engineer | devops-troubleshooter → kubernetes-architect |
| **API Down** | backend-architect | devops-troubleshooter → observability-engineer |

---

**Pro Tip:** Bookmark this cheatsheet and use it as your daily reference. Most tasks can be solved by these 20 agents!

**Last Updated:** 2025-10-22
