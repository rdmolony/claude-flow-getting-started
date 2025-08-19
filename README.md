# Getting started with Claude Flow

> Published on 

Since the launch of [`Claude Code`](https://docs.anthropic.com/en/docs/claude-code/overview) in May 2025, it has become more & more widely adopted among software engineers.

> What's `Claude Code`? 
>
> Since `ChatGPT` launched in November 2022, the predominant way of interacting with `Large Language Models` has been through a web-based chat interface. `Claude Code`, by contrast, is a terminal-based interface. A web-based interface cannot access software on your computer, or files unless you manually upload them. A terminal-based interface can. This makes it waaaay more hackable since you can combine it with whatever tools or files you want. This also makes the tool more dangerous since it can now potentially delete important files on your computer, or access credentials! So "use it with caution"

I have personally use it because it is more customisable than it's web-based peers like `ChatGPT` since it can access my local files and command line tools.

So what's [`Claude Flow`](https://github.com/ruvnet/claude-flow)? This open source library was initally launched as a `Claude Code` agent orchestrator. This means that it can create and coordinate multiple agents to solve a particular goal.  This is most easily understood with an example.

Let's say I want to create a `Claude Flow` tutorial for newcomers.

Using only `Claude Code` I can launch it

```sh
claude
```

and ask it to help me

```sh
> Create a `Claude Flow` tutorial for newcomers; specifically newcomers who are comfortable on
   the command line. Create a new file
  ./_posts/2025-08-19-get-started-with-claude-flow-by-claude.md

● I'll create a comprehensive Claude Flow tutorial for command-line comfortable newcomers. Let
   me start by organizing this task.

● Update Todos
  ⎿  ☐ Create the blog post file structure with proper frontmatter
     ☐ Write introduction and overview section
     ☐ Add installation instructions
     ☐ Include basic usage examples
     ☐ Add advanced tips and workflow suggestions
     ☐ Include troubleshooting section

● Write(_posts/2025-08-19-get-started-with-claude-flow-by-claude.md)
  ⎿  Wrote 370 lines to _posts/2025-08-19-get-started-with-claude-flow-by-claude.md
```

`Claude Code` breaks up my task into subtasks and executes each sequentially (one after the other).

Unfortunately the resulting tutorial has absolutely nothing to do with `Claude Flow`, but rather describes how to work with `Claude Code` - "Claude Flow (also known as Claude Code) is Anthropic's official CLI tool that brings Claude's AI capabilities directly to your terminal"

Oh well. Let's see if `Claude Flow` does any better.

If I use `Claude Flow` instead it breaks up the goal into subtasks **and** 
- Creates a team of AI agents with relevant specialties (researcher, teacher, etc)
- Assigns responsibilities to each
- Waits each agent to complete its job
- Fetches the results from each agent
- Combines the result

I can launch it like

```sh
npx claude-flow@alpha init
claude-flow swarm "Create a `Claude Flow` tutorial for newcomers; specifically newcomers who are comfortable on the command line. Create a new file ../_posts/2025-08-19-get-started-with-claude-flow-by-claude-flow.md"
```

and it responds with

```sh
> You are orchestrating a Claude Flow Swarm with advanced MCP tool coordination.

  🎯 OBJECTIVE: Create a  tutorial for newcomers; specifically newcomers who are comfortable
  on the command line. Create a new file
  ../_posts/2025-08-19-get-started-with-claude-flow-by-claude-flow.md

  # ... and ~400 more lines of instructions to teach Claude Code how to orchestrate agents

● I'll create a comprehensive Claude Flow tutorial for command-line savvy newcomers. Let me
  start by initializing a swarm to orchestrate this task efficiently.

● claude-flow - swarm_init (MCP)(topology: "mesh", maxAgents: 5, strategy: "adaptive")

● claude-flow - agent_spawn (MCP)(type: "coordinator", name: "TutorialLead", capabilities:
                                 ["task-planning","content-structure","quality-control"])

● claude-flow - agent_spawn (MCP)(type: "researcher", name: "ContentResearcher", capabilities:
                                  ["documentation-analysis","best-practices","example-gatherin
                                 g"])

● claude-flow - agent_spawn (MCP)(type: "coder", name: "CodeExampleCreator", capabilities:
                                 ["code-examples","command-snippets","script-generation"])

● claude-flow - agent_spawn (MCP)(type: "documenter", name: "TutorialWriter", capabilities:
                                 ["technical-writing","markdown","tutorial-structure"])

● Update Todos
  ⎿  ☒ Initialize swarm for tutorial creation
     ☐ Research Claude Flow core concepts and features
     ☐ Define tutorial structure and sections
     ☐ Create installation and setup section
     ☐ Write basic commands and usage examples
     ☐ Add swarm coordination examples
     ☐ Create practical hands-on exercises
     ☐ Add troubleshooting and tips section
     ☐ Review and polish the tutorial
     ☐ Save to Jekyll post format

● claude-flow - memory_usage (MCP)(action: "store", key: "tutorial/objective", value: "Create
                                  comprehensive Claude Flow tutorial for CLI-comfortable
                                  newcomers in Jekyll post format", namespace:
                                  "swarm_1755616697754")

● claude-flow - memory_usage (MCP)(action: "store", key: "tutorial/target_audience", value:
                                  "Command-line comfortable users new to Claude Flow",
                                  namespace: "swarm_1755616697754")


● claude-flow - memory_usage (MCP)(action: "store", key: "tutorial/sections", value:
                                  "Introduction, Installation, Core Concepts, Basic Usage,
                                  Swarm Coordination, Advanced Features, Practical Examples,
                                  Troubleshooting", namespace: "swarm_1755616697754")

● Now I'll create the comprehensive Claude Flow tutorial for command-line comfortable
  newcomers. Let me orchestrate the content creation and write the tutorial in Jekyll post
  format.

● claude-flow - task_orchestrate (MCP)(task: "Research and compile Claude Flow core concepts,
                                      features, installation steps, and best practices for
                                      tutorial", strategy: "parallel", priority: "high")

● Write(_posts/2025-08-19-get-started-with-claude-flow-by-claude-flow.md)
  ⎿  Wrote 546 lines to _posts/2025-08-19-get-started-with-claude-flow-by-claude-flow.md
```

The `Claude Flow` tutorial is actually about `Claude Code`, however, it does nonetheless halluncinate a little & invent commands.

