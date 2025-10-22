# Agents Catalog

**Total Agents:** 85 specialized AI agents organized by domain

---

## QUICK REFERENCE TABLE

| Category | Agent Count | Model Mix | Primary Use Cases |
|----------|-------------|-----------|-------------------|
| Architecture & System Design | 12 | Opus/Sonnet | System architecture, API design, cloud infrastructure |
| Programming Languages | 23 | Sonnet | Language-specific development and optimization |
| Infrastructure & Operations | 10 | Sonnet/Opus | DevOps, deployment, database management, incident response |
| Quality Assurance & Security | 14 | Sonnet/Haiku | Code review, security audit, penetration testing |
| Data & AI | 9 | Sonnet/Opus | Data engineering, ML pipelines, LLM applications |
| Documentation & Content | 6 | Sonnet | Technical documentation, API docs, content creation |
| Business & Operations | 6 | Sonnet | Analytics, sales automation, SEO, HR/legal |
| Specialized Domains | 5 | Sonnet | Gaming, finance, blockchain, payments |

---

## ARCHITECTURE & SYSTEM DESIGN (12 agents)

### Core Architecture

| Agent | Model | Tier | Use Cases |
|-------|-------|------|-----------|
| **backend-architect** | sonnet | Advanced | RESTful/GraphQL/gRPC API design, microservices, distributed systems, event-driven architecture |
| **frontend-developer** | sonnet | Core | React components, responsive layouts, client-side state management |
| **graphql-architect** | opus | Advanced | GraphQL schemas, resolvers, federation architecture |
| **architect-reviewer** | opus | Advanced | Architectural consistency analysis, pattern validation |
| **cloud-architect** | opus | Advanced | AWS/Azure/GCP infrastructure design, cost optimization, multi-cloud strategies |
| **hybrid-cloud-architect** | opus | Advanced | Multi-cloud strategies across cloud and on-premises environments |
| **kubernetes-architect** | opus | Advanced | Cloud-native infrastructure, Kubernetes, GitOps, service mesh |

### UI/UX & Mobile

| Agent | Model | Tier | Use Cases |
|-------|-------|------|-----------|
| **ui-ux-designer** | sonnet | Core | Interface design, wireframes, design systems, accessibility |
| **ui-visual-validator** | sonnet | Core | Visual regression testing, UI verification |
| **mobile-developer** | sonnet | Core | React Native, Flutter cross-platform apps |
| **ios-developer** | sonnet | Core | Native iOS with Swift/SwiftUI |
| **flutter-expert** | sonnet | Advanced | Advanced Flutter development, state management |

**ACTIVATION PATTERNS:**
- Use **backend-architect** proactively when creating new backend services or APIs
- Use **cloud-architect** for infrastructure planning and cost optimization
- Use **kubernetes-architect** for container orchestration and cloud-native design
- Use **ui-ux-designer** for new feature design and interface improvements

---

## PROGRAMMING LANGUAGES (23 agents)

### Systems & Low-Level

| Agent | Model | Tier | Use Cases |
|-------|-------|------|-----------|
| **c-pro** | sonnet | Advanced | System programming, memory management, OS interfaces |
| **cpp-pro** | sonnet | Advanced | Modern C++ with RAII, smart pointers, STL algorithms |
| **rust-pro** | sonnet | Advanced | Memory-safe systems programming, ownership patterns |
| **golang-pro** | sonnet | Advanced | Concurrent programming, goroutines, channels |
| **arm-cortex-specialist** | sonnet | Specialized | ARM Cortex-M microcontroller programming, embedded systems |

### Web & Application

| Agent | Model | Tier | Use Cases |
|-------|-------|------|-----------|
| **javascript-pro** | sonnet | Core | Modern JavaScript, ES6+, async patterns, Node.js |
| **typescript-pro** | sonnet | Core | Advanced TypeScript, type systems, generics |
| **python-pro** | sonnet | Core | Python development, advanced features, optimization |
| **ruby-pro** | sonnet | Core | Ruby, metaprogramming, Rails patterns, gem development |
| **php-pro** | sonnet | Core | Modern PHP, frameworks, performance optimization |

### Enterprise & JVM

| Agent | Model | Tier | Use Cases |
|-------|-------|------|-----------|
| **java-pro** | sonnet | Core | Modern Java, streams, concurrency, JVM optimization |
| **scala-pro** | sonnet | Advanced | Enterprise Scala, functional programming, distributed systems |
| **csharp-pro** | sonnet | Core | C# development, .NET frameworks, async patterns |

### Specialized Frameworks

| Agent | Model | Tier | Use Cases |
|-------|-------|------|-----------|
| **elixir-pro** | sonnet | Advanced | Elixir with OTP patterns, Phoenix frameworks |
| **django-pro** | sonnet | Core | Django development, ORM, async views |
| **fastapi-pro** | sonnet | Core | FastAPI with async patterns, Pydantic validation |
| **nextjs-expert** | sonnet | Core | Next.js with SSR/SSG, App Router, server components |
| **react-expert** | sonnet | Core | React with hooks, context, performance optimization |
| **vue-expert** | sonnet | Core | Vue 3 with Composition API, Pinia, TypeScript |
| **angular-expert** | sonnet | Core | Angular with RxJS, dependency injection, modules |
| **sql-pro** | sonnet | Core | Complex SQL queries, database optimization |
| **nosql-specialist** | sonnet | Core | MongoDB, Redis, DynamoDB, document databases |

### Game Development

| Agent | Model | Tier | Use Cases |
|-------|-------|------|-----------|
| **unity-developer** | sonnet | Specialized | Unity game development, C# scripting, optimization |
| **minecraft-bukkit-pro** | sonnet | Specialized | Minecraft server plugin development, Bukkit/Spigot APIs |

**ACTIVATION PATTERNS:**
- Use **python-pro** or **typescript-pro** for core development tasks
- Use **fastapi-pro** or **django-pro** for Python backend development
- Use **react-expert** or **nextjs-expert** for modern frontend development
- Use **sql-pro** for complex database queries and optimization

---

## INFRASTRUCTURE & OPERATIONS (10 agents)

### DevOps & Deployment

| Agent | Model | Tier | Use Cases |
|-------|-------|------|-----------|
| **devops-troubleshooter** | sonnet | Core | Production debugging, log analysis, deployment troubleshooting |
| **deployment-engineer** | sonnet | Core | CI/CD pipelines, containerization, cloud deployments |
| **terraform-specialist** | sonnet | Core | Infrastructure as Code, Terraform modules, state management |
| **dx-optimizer** | sonnet | Advanced | Developer experience optimization, tooling improvements |

### Database Management

| Agent | Model | Tier | Use Cases |
|-------|-------|------|-----------|
| **database-optimizer** | sonnet | Core | Query optimization, index design, migration strategies |
| **database-admin** | sonnet | Core | Database operations, backup, replication, monitoring |
| **database-architect** | opus | Advanced | Database design from scratch, technology selection, schema modeling |

### Incident Response & Network

| Agent | Model | Tier | Use Cases |
|-------|-------|------|-----------|
| **incident-responder** | opus | Advanced | Production incident management and resolution |
| **network-engineer** | sonnet | Core | Network debugging, load balancing, traffic analysis |
| **observability-engineer** | sonnet | Core | Monitoring, alerting, distributed tracing, logging |

**ACTIVATION PATTERNS:**
- Use **devops-troubleshooter** for production issues and deployment problems
- Use **database-architect** BEFORE backend-architect for data layer design
- Use **incident-responder** for critical production outages
- Use **observability-engineer** for monitoring and instrumentation setup

---

## QUALITY ASSURANCE & SECURITY (14 agents)

### Code Quality & Review

| Agent | Model | Tier | Use Cases |
|-------|-------|------|-----------|
| **code-reviewer** | sonnet | Core | General code review, best practices, readability |
| **security-auditor** | sonnet | Core | Security vulnerability detection, OWASP Top 10 |
| **performance-engineer** | sonnet | Core | Performance optimization, profiling, benchmarking |
| **refactoring-specialist** | sonnet | Core | Code restructuring, design pattern application |
| **comprehensive-reviewer** | opus | Advanced | Holistic code review across architecture, security, performance |

### Testing & Quality

| Agent | Model | Tier | Use Cases |
|-------|-------|------|-----------|
| **test-automator** | haiku | Fast | Test generation, test automation, coverage analysis |
| **tdd-coach** | sonnet | Core | Test-driven development guidance, testing patterns |
| **integration-tester** | haiku | Fast | Integration test creation, API testing, contract testing |
| **load-tester** | sonnet | Core | Load testing, stress testing, capacity planning |

### Security Specialists

| Agent | Model | Tier | Use Cases |
|-------|-------|------|-----------|
| **penetration-tester** | sonnet | Advanced | Security testing, vulnerability exploitation, penetration testing |
| **compliance-specialist** | sonnet | Core | GDPR, HIPAA, SOC2, regulatory compliance |
| **api-security-expert** | sonnet | Core | API authentication, authorization, rate limiting |
| **frontend-security-specialist** | sonnet | Core | XSS prevention, CSRF protection, CSP, frontend security |
| **mobile-security-expert** | sonnet | Advanced | Mobile app security, secure storage, certificate pinning |

**ACTIVATION PATTERNS:**
- Use **code-reviewer** proactively after code completion
- Use **security-auditor** before production deployment
- Use **test-automator** (haiku) for fast test generation
- Use **comprehensive-reviewer** for major releases or critical features

---

## DATA & AI (9 agents)

### Data Engineering & ML

| Agent | Model | Tier | Use Cases |
|-------|-------|------|-----------|
| **data-engineer** | sonnet | Core | Data pipelines, ETL, data warehousing, data quality |
| **ml-engineer** | sonnet | Advanced | Model training, deployment, MLOps, feature engineering |
| **mlops-specialist** | sonnet | Advanced | ML infrastructure, model monitoring, CI/CD for ML |
| **data-scientist** | opus | Advanced | Statistical analysis, experimentation, model selection |

### LLM & AI Applications

| Agent | Model | Tier | Use Cases |
|-------|-------|------|-----------|
| **llm-application-architect** | opus | Advanced | LLM application design, RAG, prompt engineering |
| **prompt-engineer** | sonnet | Core | Prompt optimization, few-shot learning, chain-of-thought |
| **rag-specialist** | sonnet | Advanced | Retrieval-Augmented Generation, vector databases, semantic search |
| **agent-orchestrator** | sonnet | Advanced | Multi-agent coordination, agent workflows, task decomposition |

### Context & Knowledge

| Agent | Model | Tier | Use Cases |
|-------|-------|------|-----------|
| **context-manager** | sonnet | Core | Context window optimization, token management, semantic compression |

**ACTIVATION PATTERNS:**
- Use **llm-application-architect** for LLM product design
- Use **rag-specialist** for knowledge base integration
- Use **agent-orchestrator** for complex multi-agent workflows
- Use **context-manager** when dealing with large codebases or context limits

---

## DOCUMENTATION & CONTENT (6 agents)

| Agent | Model | Tier | Use Cases |
|-------|-------|------|-----------|
| **technical-writer** | sonnet | Core | Technical documentation, user guides, API documentation |
| **api-documenter** | sonnet | Core | OpenAPI/Swagger specs, GraphQL docs, code examples |
| **diagram-generator** | sonnet | Core | Architecture diagrams (Mermaid), flowcharts, sequence diagrams |
| **content-strategist** | sonnet | Advanced | Content planning, information architecture, documentation strategy |
| **seo-writer** | sonnet | Core | SEO-optimized content, keyword integration, meta descriptions |
| **technical-seo-specialist** | sonnet | Advanced | Technical SEO audit, Core Web Vitals, structured data |

**ACTIVATION PATTERNS:**
- Use **api-documenter** when creating or updating APIs
- Use **diagram-generator** for visualizing architecture and workflows
- Use **technical-writer** for user-facing documentation
- Use **seo-writer** for marketing content and blog posts

---

## BUSINESS & OPERATIONS (6 agents)

| Agent | Model | Tier | Use Cases |
|-------|-------|------|-----------|
| **business-analyst** | sonnet | Core | Requirements gathering, process analysis, KPI definition |
| **sales-engineer** | sonnet | Core | Pre-sales technical consultation, demos, POCs |
| **customer-success-specialist** | sonnet | Core | Customer onboarding, training, support automation |
| **hr-legal-advisor** | sonnet | Core | Employment contracts, compliance, HR policies |
| **financial-analyst** | sonnet | Core | Financial modeling, forecasting, budget planning |
| **seo-analyst** | sonnet | Core | SEO audit, competitive analysis, keyword research |

**ACTIVATION PATTERNS:**
- Use **business-analyst** for requirements definition
- Use **sales-engineer** for technical sales enablement
- Use **customer-success-specialist** for onboarding content
- Use **seo-analyst** for website and content optimization

---

## SPECIALIZED DOMAINS (5 agents)

### Blockchain & Web3

| Agent | Model | Tier | Use Cases |
|-------|-------|------|-----------|
| **solidity-expert** | sonnet | Specialized | Smart contracts, DeFi protocols, Web3 integration |
| **web3-security-auditor** | sonnet | Specialized | Smart contract security, reentrancy, overflow vulnerabilities |

### Finance & Payments

| Agent | Model | Tier | Use Cases |
|-------|-------|------|-----------|
| **quant-trader** | opus | Specialized | Algorithmic trading, quantitative finance, risk management |
| **payment-integration-specialist** | sonnet | Core | Stripe, PayPal, payment processing, billing systems |

### Gaming

| Agent | Model | Tier | Use Cases |
|-------|-------|------|-----------|
| **game-designer** | sonnet | Specialized | Game mechanics, level design, player experience |

**ACTIVATION PATTERNS:**
- Use **solidity-expert** and **web3-security-auditor** together for smart contracts
- Use **payment-integration-specialist** for payment gateway integration
- Use **quant-trader** for financial modeling and trading systems

---

## MODEL TIER GUIDE

### Opus (Advanced/Complex Reasoning)
- **When to use**: Architectural decisions, complex system design, strategic planning
- **Agents**: database-architect, cloud-architect, llm-application-architect, incident-responder
- **Cost**: Higher tokens, slower, but deepest reasoning

### Sonnet (Balanced Performance)
- **When to use**: Core development, code review, documentation, most tasks
- **Agents**: 90% of agents use Sonnet
- **Cost**: Moderate tokens, fast, excellent quality

### Haiku (Fast Execution)
- **When to use**: Test generation, quick analysis, deterministic tasks
- **Agents**: test-automator, integration-tester
- **Cost**: Low tokens, very fast, good for batch operations

---

## COMMON USE CASE MAPPINGS

| Use Case | Primary Agent | Supporting Agents |
|----------|---------------|-------------------|
| **New Backend API** | backend-architect | database-architect → security-auditor → test-automator |
| **Frontend Feature** | frontend-developer | ui-ux-designer → react-expert → security-auditor |
| **Database Design** | database-architect | backend-architect → performance-engineer |
| **Production Incident** | incident-responder | devops-troubleshooter → observability-engineer |
| **Security Audit** | security-auditor | penetration-tester → compliance-specialist |
| **LLM Application** | llm-application-architect | rag-specialist → prompt-engineer → agent-orchestrator |
| **CI/CD Pipeline** | deployment-engineer | devops-troubleshooter → security-auditor |
| **Code Review** | code-reviewer | security-auditor → performance-engineer |
| **Full-Stack Feature** | backend-architect | frontend-developer → database-architect → test-automator |
| **Documentation** | technical-writer | api-documenter → diagram-generator |

---

## AGENT COORDINATION PATTERNS

### Sequential Workflows
1. **Data Layer First**: database-architect → backend-architect → frontend-developer
2. **Security Hardening**: security-auditor → penetration-tester → compliance-specialist
3. **Full-Stack Feature**: backend-architect → frontend-developer → test-automator → security-auditor

### Parallel Execution
- **Code Review**: code-reviewer + security-auditor + performance-engineer (run simultaneously)
- **Documentation**: technical-writer + api-documenter + diagram-generator (parallel creation)

### Hybrid Orchestration
- **Planning (Opus)** → **Execution (Sonnet)** → **Testing (Haiku)** → **Review (Sonnet)**

---

## QUICK START RECOMMENDATIONS

### For Backend Development
1. Install: `python-development`, `backend-development`, `database-design`
2. Key agents: python-pro, backend-architect, database-architect
3. Workflow: database-architect → backend-architect → test-automator

### For Frontend Development
1. Install: `javascript-typescript`, `multi-platform-apps`, `application-performance`
2. Key agents: typescript-pro, react-expert, frontend-developer
3. Workflow: ui-ux-designer → react-expert → performance-engineer

### For Full-Stack Development
1. Install: `full-stack-orchestration`, `backend-development`, `javascript-typescript`
2. Key agents: backend-architect, frontend-developer, database-architect
3. Use workflow: `/full-stack-orchestration:full-stack-feature`

### For DevOps & Infrastructure
1. Install: `kubernetes-operations`, `cloud-infrastructure`, `cicd-automation`
2. Key agents: kubernetes-architect, cloud-architect, deployment-engineer
3. Workflow: cloud-architect → kubernetes-architect → deployment-engineer

### For Security & Compliance
1. Install: `security-scanning`, `backend-api-security`, `accessibility-compliance`
2. Key agents: security-auditor, penetration-tester, compliance-specialist
3. Workflow: security-auditor → penetration-tester → compliance-specialist

---

## NOTES

- **Proactive Agents**: Some agents (backend-architect, code-reviewer) should be used proactively without explicit invocation
- **Agent Deference**: Agents defer to specialists (backend-architect defers database schema to database-architect)
- **Progressive Disclosure**: Agent skills load knowledge only when activated (minimal token usage)
- **Granular Installation**: Install only the plugins you need - each loads specific agents, commands, and skills
- **Model Optimization**: Hybrid orchestration combines models strategically (Opus for planning, Sonnet for execution, Haiku for testing)

---

**Last Updated:** 2025-10-22
**Repository:** wshobson/agents
**Total Plugins:** 63 | **Total Agents:** 85 | **Total Skills:** 47 | **Total Commands:** 44
