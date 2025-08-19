---
layout: post
title: "Get Started with Claude Flow: A Command-Line Power User's Guide"
date: 2025-08-19
categories: [tutorial, claude-flow, ai, automation]
tags: [claude-flow, swarm-intelligence, mcp, cli, automation]
author: Claude Flow Swarm
description: "Master Claude Flow's AI-powered swarm orchestration from the command line. Learn to coordinate multi-agent systems, automate complex workflows, and leverage distributed AI intelligence."
---

# Get Started with Claude Flow: A Command-Line Power User's Guide

Welcome to Claude Flow - the next evolution in AI-powered development orchestration. If you're comfortable with the command line and ready to harness the power of coordinated AI swarms, you're in the right place.

## What is Claude Flow?

Claude Flow is a revolutionary AI orchestration system that coordinates multiple specialized agents to tackle complex tasks with unprecedented efficiency. Think of it as having an entire development team at your fingertips, orchestrated through simple commands.

### Key Features at a Glance

- **🐝 Swarm Intelligence**: Coordinate up to 100 specialized AI agents working in parallel
- **⚡ 84.8% SWE-Bench Performance**: Industry-leading problem-solving capabilities
- **🚀 2.8-4.4x Speed Improvement**: Parallel execution crushes sequential bottlenecks
- **🧠 27+ Neural Models**: Advanced pattern recognition and learning
- **💾 Persistent Memory**: Cross-session knowledge retention
- **🔧 MCP Integration**: Seamless tool coordination

## Installation: 60 Seconds to Swarm Power

### Prerequisites
- Node.js 18+ installed
- npm or yarn package manager
- Terminal/command line access

### Quick Install

```bash
# Install Claude Flow globally
npm install -g claude-flow@alpha

# Or use it directly with npx (no install needed)
npx claude-flow@alpha --version

# Add as MCP server to Claude Desktop (if using)
claude mcp add claude-flow npx claude-flow@alpha mcp start
```

### Verify Installation

```bash
# Check version
npx claude-flow@alpha --version

# View available commands
npx claude-flow@alpha --help

# Test swarm initialization
npx claude-flow@alpha swarm init --topology mesh
```

## Core Concepts: Understanding the Swarm

### 1. Agents: Your Specialized Workers

Claude Flow agents are specialized AI entities, each optimized for specific tasks:

```bash
# List available agent types
npx claude-flow@alpha agent types

# Common agent types:
# - coordinator: Orchestrates other agents
# - researcher: Gathers and analyzes information
# - coder: Writes and refactors code
# - tester: Creates and runs tests
# - reviewer: Performs code reviews
# - architect: Designs system architecture
```

### 2. Topologies: How Agents Connect

Choose your swarm structure based on your task:

```bash
# Mesh: Peer-to-peer, maximum flexibility
npx claude-flow@alpha swarm init --topology mesh --max-agents 5

# Hierarchical: Tree structure with clear command chain
npx claude-flow@alpha swarm init --topology hierarchical --max-agents 8

# Star: Central coordinator with worker agents
npx claude-flow@alpha swarm init --topology star --max-agents 6

# Ring: Sequential processing pipeline
npx claude-flow@alpha swarm init --topology ring --max-agents 4
```

### 3. Memory: Persistent Knowledge Base

```bash
# Store information
npx claude-flow@alpha memory store --key "project/specs" --value "API requirements..."

# Retrieve information
npx claude-flow@alpha memory get --key "project/specs"

# Search memory
npx claude-flow@alpha memory search --pattern "project/*"

# List namespaces
npx claude-flow@alpha memory namespaces
```

## Basic Usage: Your First Swarm

### Example 1: Simple Code Review

```bash
# Initialize a review swarm
npx claude-flow@alpha swarm init --topology star --max-agents 3

# Spawn specialized agents
npx claude-flow@alpha agent spawn --type reviewer --name "CodeReviewer"
npx claude-flow@alpha agent spawn --type tester --name "TestValidator"

# Execute code review task
npx claude-flow@alpha task execute \
  --description "Review auth.js for security issues" \
  --file ./src/auth.js \
  --output ./reports/review.md

# Check status
npx claude-flow@alpha swarm status
```

### Example 2: Full Feature Development

```bash
# Use SPARC methodology for systematic development
npx claude-flow@alpha sparc tdd "user authentication system"

# This automatically:
# 1. Specifications: Analyzes requirements
# 2. Pseudocode: Designs algorithms
# 3. Architecture: Plans system structure
# 4. Refinement: Implements with TDD
# 5. Completion: Integrates and validates
```

## Advanced Swarm Coordination

### Parallel Task Execution

```bash
# Execute multiple tasks simultaneously
npx claude-flow@alpha batch execute \
  --tasks "analyze-db-schema,optimize-queries,generate-migrations" \
  --parallel true \
  --max-agents 6
```

### Custom Workflows

Create a workflow file `workflow.json`:

```json
{
  "name": "api-development",
  "steps": [
    {
      "id": "design",
      "agent": "architect",
      "task": "Design REST API endpoints"
    },
    {
      "id": "implement",
      "agent": "coder",
      "task": "Implement API handlers",
      "depends_on": ["design"]
    },
    {
      "id": "test",
      "agent": "tester",
      "task": "Create integration tests",
      "depends_on": ["implement"]
    }
  ]
}
```

Execute the workflow:

```bash
npx claude-flow@alpha workflow run --file workflow.json --monitor
```

### Neural Pattern Training

```bash
# Train patterns from successful executions
npx claude-flow@alpha neural train \
  --pattern coordination \
  --data ./success-logs \
  --iterations 50

# Use trained patterns
npx claude-flow@alpha neural predict \
  --model coordination \
  --input "optimize database queries"
```

## Practical Examples

### 1. Automated PR Review

```bash
#!/bin/bash
# pr-review.sh

PR_NUMBER=$1
REPO=$(basename $(git rev-parse --show-toplevel))

# Initialize swarm
npx claude-flow@alpha swarm init --topology hierarchical

# Spawn review team
npx claude-flow@alpha agent spawn --type coordinator --name "PRLead"
npx claude-flow@alpha agent spawn --type reviewer --name "CodeReviewer"
npx claude-flow@alpha agent spawn --type tester --name "TestRunner"
npx claude-flow@alpha agent spawn --type analyst --name "SecurityAnalyst"

# Execute review
npx claude-flow@alpha github pr-review \
  --repo $REPO \
  --pr $PR_NUMBER \
  --checks "code-quality,tests,security,performance" \
  --output pr-review-$PR_NUMBER.md

echo "Review complete: pr-review-$PR_NUMBER.md"
```

### 2. Codebase Migration

```bash
# Migrate from JavaScript to TypeScript
npx claude-flow@alpha migrate \
  --from javascript \
  --to typescript \
  --directory ./src \
  --strategy incremental \
  --preserve-tests true
```

### 3. Performance Optimization

```bash
# Analyze and optimize performance bottlenecks
npx claude-flow@alpha performance analyze \
  --target ./src \
  --metrics "cpu,memory,io" \
  --suggest-optimizations \
  --auto-fix safe
```

## Monitoring and Debugging

### Real-time Monitoring

```bash
# Watch swarm activity
npx claude-flow@alpha swarm monitor --interval 1

# View agent metrics
npx claude-flow@alpha agent metrics --format table

# Check task progress
npx claude-flow@alpha task status --verbose
```

### Debugging Commands

```bash
# View swarm logs
npx claude-flow@alpha logs --level debug --tail 50

# Inspect agent state
npx claude-flow@alpha agent inspect --id agent_123

# Memory dump
npx claude-flow@alpha memory dump --namespace swarm_001
```

## Performance Tips

### 1. Optimize Agent Count

```bash
# Auto-scale based on workload
npx claude-flow@alpha swarm scale --auto --min 2 --max 10
```

### 2. Use Appropriate Topologies

- **Mesh**: Complex interdependent tasks
- **Hierarchical**: Large projects with clear structure
- **Star**: Simple coordination needs
- **Ring**: Sequential processing pipelines

### 3. Leverage Memory Effectively

```bash
# Pre-load context
npx claude-flow@alpha memory preload --file context.json

# Use namespaces for organization
npx claude-flow@alpha memory store \
  --namespace "project-alpha" \
  --key "specs" \
  --value "..."
```

## Troubleshooting

### Common Issues and Solutions

#### Swarm Won't Initialize

```bash
# Clear cache and retry
npx claude-flow@alpha cache clear
npx claude-flow@alpha swarm init --force
```

#### Agent Timeout

```bash
# Increase timeout
export CLAUDE_FLOW_TIMEOUT=120
npx claude-flow@alpha task execute --timeout 120000
```

#### Memory Issues

```bash
# Check memory usage
npx claude-flow@alpha memory stats

# Clean old data
npx claude-flow@alpha memory clean --older-than 7d
```

## Integration Examples

### GitHub Actions

```yaml
name: Claude Flow CI
on: [push, pull_request]

jobs:
  ai-review:
    runs-on: ubuntu-latest
    steps:
      - uses: actions/checkout@v2
      - uses: actions/setup-node@v2
      - run: npm install -g claude-flow@alpha
      - run: |
          npx claude-flow@alpha swarm init --topology star
          npx claude-flow@alpha task execute \
            --description "Review and test changes" \
            --output review.md
      - uses: actions/upload-artifact@v2
        with:
          name: ai-review
          path: review.md
```

### Shell Aliases

Add to your `.bashrc` or `.zshrc`:

```bash
# Claude Flow aliases
alias cfs='npx claude-flow@alpha swarm'
alias cfa='npx claude-flow@alpha agent'
alias cft='npx claude-flow@alpha task'
alias cfm='npx claude-flow@alpha memory'

# Quick swarm init
cfquick() {
  npx claude-flow@alpha swarm init --topology mesh --max-agents 5
  npx claude-flow@alpha agent spawn --type coordinator
  npx claude-flow@alpha agent spawn --type coder
  npx claude-flow@alpha agent spawn --type tester
}

# Development swarm
cfdev() {
  npx claude-flow@alpha sparc tdd "$1"
}
```

## Advanced Features

### Custom Agent Creation

```javascript
// custom-agent.js
module.exports = {
  type: 'custom-analyzer',
  capabilities: ['code-analysis', 'metric-extraction'],
  execute: async (task) => {
    // Custom logic here
    return { success: true, metrics: {...} }
  }
}
```

Register and use:

```bash
npx claude-flow@alpha agent register --file custom-agent.js
npx claude-flow@alpha agent spawn --type custom-analyzer
```

### Webhook Integration

```bash
# Setup webhook for task completion
npx claude-flow@alpha webhook create \
  --event task.complete \
  --url https://your-api.com/webhook \
  --secret your-secret
```

### Export and Import Workflows

```bash
# Export successful workflow
npx claude-flow@alpha workflow export \
  --id workflow_123 \
  --format json > my-workflow.json

# Import and reuse
npx claude-flow@alpha workflow import --file my-workflow.json
npx claude-flow@alpha workflow run --name my-workflow
```

## Best Practices

### 1. Start Small, Scale Smart

```bash
# Begin with minimal agents
npx claude-flow@alpha swarm init --max-agents 3

# Scale based on performance
npx claude-flow@alpha swarm scale --based-on metrics
```

### 2. Use Memory for Context

```bash
# Store project context
npx claude-flow@alpha memory store \
  --key "context/architecture" \
  --file architecture.md

# Agents automatically access stored context
```

### 3. Monitor and Optimize

```bash
# Regular performance checks
npx claude-flow@alpha performance report --weekly

# Optimize based on metrics
npx claude-flow@alpha optimize --target efficiency
```

### 4. Version Control Integration

```bash
# Pre-commit hook example
#!/bin/bash
npx claude-flow@alpha task execute \
  --description "Validate code quality" \
  --fail-on-issues
```

## Community and Resources

### Getting Help

```bash
# Built-in help
npx claude-flow@alpha help [command]

# Interactive tutorial
npx claude-flow@alpha tutorial

# Generate examples
npx claude-flow@alpha examples --category swarm-coordination
```

### Useful Links

- **Documentation**: [github.com/ruvnet/claude-flow](https://github.com/ruvnet/claude-flow)
- **Issues**: [github.com/ruvnet/claude-flow/issues](https://github.com/ruvnet/claude-flow/issues)
- **Discord**: Join the Claude Flow community
- **Examples**: [github.com/ruvnet/claude-flow/examples](https://github.com/ruvnet/claude-flow/examples)

## Quick Reference Card

```bash
# Essential Commands
npx claude-flow@alpha swarm init         # Initialize swarm
npx claude-flow@alpha agent spawn        # Create agent
npx claude-flow@alpha task execute       # Run task
npx claude-flow@alpha swarm status       # Check status
npx claude-flow@alpha memory store       # Store data
npx claude-flow@alpha sparc tdd         # TDD workflow

# Monitoring
npx claude-flow@alpha swarm monitor     # Real-time monitoring
npx claude-flow@alpha agent metrics     # Agent performance
npx claude-flow@alpha logs             # View logs

# Advanced
npx claude-flow@alpha neural train     # Train patterns
npx claude-flow@alpha workflow run     # Run workflows
npx claude-flow@alpha optimize         # Auto-optimize
```

## Conclusion

You're now equipped to harness the full power of Claude Flow's swarm intelligence. Start with simple tasks, experiment with different topologies, and gradually build complex automated workflows. The command line is your gateway to orchestrating AI agents that work together with unprecedented efficiency.

Remember: With Claude Flow, you're not just running commands - you're conducting a symphony of specialized AI agents, each contributing their expertise to achieve your goals faster and better than ever before.

Happy swarming! 🐝🚀

---

*This tutorial was created by a Claude Flow swarm consisting of 4 specialized agents working in parallel. Total creation time: < 2 minutes.*