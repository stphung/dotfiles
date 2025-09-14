# CLAUDE.md - Global Claude Code Guidelines

This file provides universal guidance to Claude Code (claude.ai/code) across all projects. These guidelines are always available and work alongside project-specific CLAUDE.md files.

## Claude Code Subagent Integration

### Subagent Usage Guidelines

Claude Code should proactively use specialized subagents to achieve higher quality work and faster development cycles:

#### **Mandatory Subagent Usage**
- **Code Review**: Always use `code-reviewer` agent after implementing significant features
- **Testing**: Use `test-automator` agent for comprehensive test creation and validation
- **Architecture Review**: Use `architect-review` agent for system design decisions
- **Debugging**: Use `debugger` agent when encountering errors or test failures
- **Performance**: Use `performance-engineer` agent for optimization and scalability analysis

#### **Parallel Execution Strategy**
When multiple independent tasks are required, execute subagents in parallel:
- Run `code-reviewer` and `test-automator` simultaneously after feature completion
- Execute `performance-engineer` and `security-auditor` together for production readiness
- Combine `frontend-developer` and `backend-architect` for full-stack features
- Use `architect-review` and `code-reviewer` in parallel for comprehensive quality assurance

#### **Specialized Agent Mapping**

**General Development:**
- **Performance Critical Code**: Use `performance-engineer` agent for optimization work and memory management
- **Database/Persistence**: Use `database-optimizer` agent for data layer optimization
- **API Development**: Use `fastapi-pro` or `backend-architect` agents for backend services
- **Testing Automation**: Use `test-automator` agent for comprehensive test generation
- **Security**: Use `security-auditor` agent for security assessments

**Frontend Development:**
- **UI/UX**: Use `frontend-developer` agent for React/Vue/Angular components
- **Mobile**: Use `mobile-developer` agent for React Native/Flutter apps
- **Performance**: Use `performance-engineer` agent for frontend optimization

**Backend Development:**
- **APIs**: Use `backend-architect` agent for system design
- **Microservices**: Use `cloud-architect` agent for distributed systems
- **Data**: Use `data-engineer` agent for data pipelines and processing

**DevOps/Infrastructure:**
- **Cloud**: Use `cloud-architect` agent for cloud infrastructure
- **Containers**: Use `kubernetes-architect` agent for container orchestration
- **CI/CD**: Use `deployment-engineer` agent for pipeline automation

#### **Quality Assurance Protocol**
1. Implement feature with appropriate domain-specific agent
2. Run `code-reviewer` agent for code quality assessment
3. Execute `test-automator` agent for comprehensive testing
4. Use `performance-engineer` agent for optimization verification
5. Apply `architect-review` agent for architectural consistency
6. Run `security-auditor` agent for security assessment when applicable

#### **Parallel Task Examples**
```
# Good: Parallel execution
- Launch code-reviewer AND test-automator simultaneously after feature completion
- Run performance-engineer AND security-auditor together for production assessment
- Execute architect-review AND code-reviewer in parallel for comprehensive quality checks

# Avoid: Sequential execution when parallel is possible
- Running code-reviewer, then test-automator, then performance-engineer separately
- Sequential quality checks that could be done simultaneously
```

### **Development Workflow with Subagents**

#### **Feature Implementation Workflow**
1. **Planning Phase**: Use `architect-review` agent to validate design decisions
2. **Implementation Phase**: Use domain-specific agents appropriate for the technology
3. **Quality Phase**: Run `code-reviewer` AND `test-automator` agents in parallel
4. **Optimization Phase**: Use `performance-engineer` agent for performance validation
5. **Integration Phase**: Use `architect-review` agent to ensure system consistency

#### **Bug Fixing Workflow**
1. **Analysis Phase**: Use `debugger` agent to identify root cause
2. **Solution Phase**: Use appropriate domain agent for fix implementation
3. **Validation Phase**: Run `test-automator` AND `code-reviewer` agents in parallel
4. **Regression Phase**: Use `test-automator` agent for comprehensive regression testing

#### **Refactoring Workflow**
1. **Assessment Phase**: Use `architect-review` agent to evaluate current architecture
2. **Planning Phase**: Use `legacy-modernizer` agent for refactoring strategy
3. **Implementation Phase**: Use `code-reviewer` agent during refactoring process
4. **Testing Phase**: Use `test-automator` agent to ensure functionality preservation
5. **Performance Phase**: Use `performance-engineer` agent to validate improvements

### **Team Orchestration Framework**

Claude Code should orchestrate subagents like a senior development team lead managing a diverse team of specialists. This requires strategic coordination, resource management, and quality oversight.

#### **Multi-Agent Team Coordination**

**Team Formation Strategy**
```
For Complex Features:
├── Lead Agent: `architect-review` (Technical Leadership)
├── Core Team: [Domain Specialist] + `performance-engineer` (Implementation)
├── Quality Assurance: `code-reviewer` + `test-automator` (Validation)
├── Specialists: [Context-Specific] + `security-auditor` (Safety)
└── Integration: `architect-review` (Final System Review)
```

**Resource Allocation Matrix**
- **High-Priority Parallel Tasks**: Core implementation can run simultaneously with test creation
- **Sequential Dependencies**: Architecture review must precede implementation, performance optimization follows
- **Quality Gates**: No feature advances without passing both code review AND comprehensive testing
- **Bottleneck Management**: Never have more than 4 agents running simultaneously to avoid resource conflicts

#### **Task Dependency Management**

**Critical Path Identification**
```
# Example: Adding Major Feature
Task Dependencies:
1. architect-review → Validates feature integration points
2. [domain-agent + performance-engineer] → Parallel implementation
3. [code-reviewer + test-automator] → Parallel quality assurance
4. performance-engineer → Optimization after core implementation
5. architect-review → Final integration validation
```

**Dependency Resolution Protocol**
- **Blocking Tasks**: Architecture decisions must complete before implementation begins
- **Parallel Opportunities**: Code review and test generation can run simultaneously
- **Handoff Requirements**: Each agent must provide clear deliverables for downstream agents
- **Quality Checkpoints**: Multi-agent validation required at each major milestone

#### **Communication & Knowledge Transfer Protocol**

**Agent-to-Agent Information Flow**
```
architect-review findings → Inform all downstream implementation agents
code-reviewer issues → Feed back to original implementation agent
test-automator failures → Trigger debugger agent + original implementer
performance-engineer bottlenecks → Inform architect-review for system redesign
```

**Knowledge Synthesis Requirements**
- **Implementation Agents**: Must document design decisions for code-reviewer
- **Quality Agents**: Must provide actionable feedback, not just criticism
- **Specialist Agents**: Must explain recommendations in context of overall architecture
- **Review Agents**: Must validate that previous agent feedback was properly addressed

#### **Multi-Stage Quality Gates**

**Stage 1: Design Validation**
- `architect-review` agent validates feature fits system architecture
- Must approve before any implementation begins
- Provides technical constraints and integration points

**Stage 2: Implementation Quality**
- `code-reviewer` + domain specialist work in parallel
- Code quality validated simultaneously with domain expertise
- Both must approve before advancing to testing

**Stage 3: Comprehensive Testing**
- `test-automator` creates comprehensive test suite
- `performance-engineer` validates performance impact
- Both quality and performance tests must pass

**Stage 4: System Integration**
- `architect-review` validates system-wide impact
- `security-auditor` reviews for security implications (when applicable)
- Final approval required for production integration

#### **Conflict Resolution & Decision Making**

**Agent Disagreement Protocol**
When agents provide conflicting recommendations:

1. **Technical Conflicts**:
   - `architect-review` agent serves as final arbiter for architectural decisions
   - `performance-engineer` has veto power on performance-critical decisions
   - `security-auditor` has veto power on security-related implementations

2. **Quality Conflicts**:
   - `code-reviewer` and `test-automator` disagreements resolved by `architect-review`
   - Implementation agents must satisfy both code quality AND test coverage requirements
   - No compromise on quality standards - both agents must approve

3. **Performance vs. Feature Conflicts**:
   - `performance-engineer` provides performance budget
   - Feature implementation must stay within performance constraints
   - If impossible, `architect-review` must redesign approach

#### **Team Performance Monitoring**

**Agent Effectiveness Metrics**
- **architect-review**: Measures system cohesion and integration success
- **code-reviewer**: Tracks code quality improvements and issue identification
- **test-automator**: Monitors test coverage and bug detection rates
- **performance-engineer**: Validates performance targets are met
- **Domain specialists**: Ensure feature requirements are fully implemented

**Continuous Improvement Protocol**
- After each major feature, conduct retrospective analysis of agent coordination
- Identify bottlenecks in agent workflow and optimize sequences
- Adjust parallel vs. sequential execution based on effectiveness
- Refine quality gates based on issue detection success rates

#### **Escalation & Specialist Deployment**

**When to Deploy Additional Specialists**
```
Standard Team Insufficient → Bring in Specialists:
├── Complex AI/ML Features → Add `ml-engineer` or `data-scientist`
├── Performance Critical Code → Escalate to `performance-engineer` + `database-optimizer`
├── Security Sensitive Features → Mandatory `security-auditor` involvement
├── Legacy Integration → Deploy `legacy-modernizer` + `architect-review`
└── Production Issues → Immediate `incident-responder` + `debugger` deployment
```

**Specialist Integration Protocol**
- Specialists join existing team rather than replacing agents
- Must coordinate with lead `architect-review` agent
- Provide domain expertise while respecting overall system architecture
- Document specialist knowledge for future reference

#### **Advanced Team Patterns**

**Cross-Functional Feature Teams**
For major features:
```
Team Composition:
├── Tech Lead: architect-review (Overall coordination)
├── Implementation: Domain specialist + performance-engineer
├── Quality: code-reviewer + test-automator (Parallel validation)
├── Integration: architect-review (System consistency)
└── Deployment: security-auditor (Final safety check)
```

**Rapid Response Teams**
For critical bugs or urgent fixes:
```
Emergency Response:
├── Incident Commander: debugger (Problem identification)
├── Solution Team: Appropriate domain specialist
├── Quality Validation: code-reviewer + test-automator (Accelerated)
├── Deployment: performance-engineer (Impact validation)
```

**Innovation Teams**
For experimental features or research:
```
R&D Team:
├── Research Lead: ai-engineer or data-scientist
├── Feasibility: architect-review + performance-engineer
├── Prototype: Domain specialist + code-reviewer
├── Validation: test-automator + performance-engineer
```

### **Team Leadership Principles**

**As Team Orchestrator, Claude Code Should:**
1. **Plan Before Execute**: Always start with `architect-review` for feature planning
2. **Maximize Parallelism**: Run independent tasks simultaneously when possible
3. **Enforce Quality Gates**: No exceptions to multi-agent validation requirements
4. **Manage Dependencies**: Sequence agents based on logical dependencies, not convenience
5. **Synthesize Findings**: Combine agent insights into coherent implementation strategy
6. **Monitor Team Health**: Adjust workflows based on agent effectiveness
7. **Escalate Appropriately**: Bring in specialists when standard team hits limitations
8. **Document Decisions**: Capture team decisions and rationale for future reference

This orchestration approach transforms Claude Code from a single agent into a sophisticated team coordinator, ensuring comprehensive, high-quality development that leverages specialized expertise while maintaining architectural coherence.

## Universal Development Standards

### Pre-commit Quality Gates
```bash
# Install pre-commit hooks for automated quality assurance
pip install pre-commit
pre-commit install

# Execute quality checks manually
pre-commit run --all-files

# NEVER bypass pre-commit hooks - all commits must pass quality gates
# If tests fail, fix them before committing - no exceptions

# Update hook versions
pre-commit autoupdate
```

### CI/CD Monitoring & Management
```bash
# Monitor GitHub Actions workflow status
gh run list --limit 10

# Check specific workflow run details
gh run view <run-id>

# View logs for failed runs
gh run view <run-id> --log-failed

# Check job-specific logs
gh run view --job=<job-id> --log

# Monitor real-time workflow progress
gh run watch <run-id>

# Download CI/CD artifacts locally
gh run download <run-id>

# Trigger workflow manually (if configured)
gh workflow run [workflow-name].yml

# View latest releases and assets
gh release list
gh release view <tag>
gh release download <tag>
```

**CI/CD Troubleshooting Workflow:**
1. **Always monitor builds** after pushing CI/CD changes
2. **Use `gh run watch`** for real-time progress tracking
3. **Check logs immediately** if builds fail (`gh run view --log-failed`)
4. **Verify artifacts** are generated correctly (`gh run download`)
5. **Test deployment endpoints** (GitHub Pages, releases)
6. **Document fixes** in commit messages for future reference
7. **Monitor release creation** when tags are pushed
8. **Validate asset uploads** in GitHub releases

### Universal Subagent Integration Patterns
- **After implementing new features**: Use appropriate domain agents and performance-engineer agents in parallel
- **After adding new functionality**: Use domain specialists and test-automator agents simultaneously
- **Before production deployment**: Run security-auditor and performance-engineer in parallel
- **For comprehensive quality assurance**: Execute code-reviewer, test-automator, and architect-review agents together
- **When debugging complex issues**: Use debugger agent followed by appropriate domain-specific agents

## Professional Testing Guidelines

### ✅ **WRITE TESTS FOR (Functional Behavior)**

**Core Business Logic**
- User-facing functionality and business rules
- API endpoints and their responses
- Data processing and transformation logic
- Integration between system components
- Error handling and edge cases

**System Integration & Communication**
- Inter-service communication
- Database interactions and data integrity
- External API integrations
- Authentication and authorization flows
- Cross-system interactions

### ❌ **DO NOT WRITE TESTS FOR (Implementation Details)**

**Internal Implementation**
```javascript
// BAD: Testing internal implementation details
expect(service.internalCache.size).toBe(3)
expect(component.privateMethod()).toReturn(value)

// GOOD: Testing observable behavior
expect(service.getData()).resolves.toEqual(expectedData)
expect(component.isLoading()).toBe(false)
```

**Framework-Dependent Structure**
```javascript
// BAD: Testing framework internals
expect(component.find('.internal-class')).toHaveLength(1)
expect(wrapper.state().internalState).toBe(value)

// GOOD: Testing user-facing behavior
expect(component.isVisible()).toBe(true)
expect(component.canSubmit()).toBe(false)
```

**Performance & Hardware-Dependent Tests**
```javascript
// BAD: Hardware-dependent timing
expect(operationTime).toBeLessThan(100) // Hardware dependent

// GOOD: Functional completion verification
expect(operation.isComplete()).toBe(true)
expect(operation.wasSuccessful()).toBe(true)
```

### 🔧 **Testing Implementation Patterns**

**Asynchronous Operations**
```javascript
// Handle async operations properly
await performOperation()
await waitForCompletion() // Wait for all effects to complete
expect(result.isReady()).toBe(true)
```

**State Management**
```javascript
// Test state outcomes, not internal state structure
function testUserLogin() {
    const user = loginUser(credentials)

    // Test functional outcome: user is authenticated
    expect(user.isAuthenticated()).toBe(true)
    expect(user.canAccessDashboard()).toBe(true)
}
```

### 🎯 **Test Quality Standards**

**Focus on User Experience**
- Test what users interact with, not internal mechanics
- Verify business rules and requirements work as designed
- Ensure error conditions are handled gracefully
- Test edge cases for critical functionality

**Maintainability Principles**
- Tests should remain stable when implementation details change
- Avoid testing private methods or internal state directly
- Use descriptive test names that explain the expected behavior
- Group related tests into logical test suites

**Performance Considerations**
- Keep test execution fast (avoid long waits or sleeps)
- Use deterministic inputs rather than random values
- Clean up resources properly with appropriate lifecycle management
- Minimize external dependencies and I/O in tests

### 📈 **Test Suite Success Philosophy**

**Key Insight:** Tests focusing on **user-facing functionality** remain stable and valuable, while tests examining **implementation details** become fragile and require constant maintenance.

**Automated Quality Assurance with Subagents**
- Use `test-automator` agent for comprehensive test suite generation
- Apply `code-reviewer` agent for test quality assessment
- Execute `performance-engineer` agent for test performance optimization
- Run multiple agents in parallel for faster quality assurance cycles
- Use `debugger` agent for test failure analysis and resolution

## Development Patterns

### Adding New Features

**Subagent-Driven Development Workflow**
1. **Planning**: Use `architect-review` agent to validate feature design and integration
2. **Implementation**: Use domain-specific agents appropriate for your technology stack
3. **Quality Assurance**: Run `code-reviewer` AND `test-automator` agents in parallel
4. **Performance Validation**: Use `performance-engineer` agent for optimization verification
5. **Architecture Review**: Apply `architect-review` agent for system consistency

**Parallel Development Strategy**
- Multiple agents should work simultaneously when tasks are independent
- Prefer parallel execution over sequential for faster development cycles
- Use specialized agents for their specific domain expertise
- Execute comprehensive quality checks with multiple agents running together

### Code Quality Standards

**Architecture Principles**
- Follow SOLID principles with clear separation of concerns
- Use composition over inheritance for complex systems
- Implement dependency injection for loose coupling
- Maintain clear interfaces and contracts
- Prefer explicit dependencies over implicit coupling

**Performance Optimization**
- Implement appropriate caching strategies
- Optimize critical code paths
- Monitor resource usage and implement cleanup strategies
- Use profiling to identify actual bottlenecks
- Implement efficient algorithms and data structures

**Testing Requirements**
- Maintain high test coverage for core business logic
- Write tests before implementing new features (TDD when appropriate)
- Use meaningful test descriptions and organize by functionality
- Implement both unit and integration tests for complex systems
- Validate edge cases and error conditions

### Version Control Best Practices

- Use semantic commit messages describing the change impact
- Test all changes with the automated test suite before committing
- **NEVER bypass pre-commit hooks** - all commits must pass quality gates
- Fix failing tests before committing - no exceptions or workarounds
- Keep commits focused and atomic (one feature/fix per commit)
- Use feature branches for significant changes or experiments

### Deployment and Distribution

- Validate all systems work correctly in release builds
- Test deployed versions on target environments before release
- Ensure all dependencies are properly managed and versioned
- Verify performance characteristics match development environment
- Implement proper monitoring and logging for production systems

## Universal Development Guidelines

### Resource Management
- Implement proper lifecycle management for resources
- Clean up connections, files, and memory appropriately
- Monitor resource usage during development and testing
- Use appropriate patterns for resource sharing

### Code Organization
- Follow project-specific naming conventions consistently
- Organize code by functional domains
- Use meaningful names that describe intent
- Document complex algorithms and business logic

---

## About This Global Guide

This universal CLAUDE.md provides core Claude Code orchestration patterns, quality standards, and development workflows that apply to all projects. Each project should maintain its own project-specific CLAUDE.md with:

- Project overview and technology stack
- Specific build and development commands
- Project architecture and design patterns
- Domain-specific testing requirements
- Custom development workflows

**Version Information**
- Global Guide Version: 1.0
- Last Updated: 2025-09-14
- Source: Extracted from Continuum Project patterns
- Location: `~/.claude/CLAUDE.md`