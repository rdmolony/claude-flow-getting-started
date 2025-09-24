> [!WARNING]
> I am not a member of the `Claude Flow` team, this is merely what I picked up from watching videos at [https://video.agentics.org/](https://video.agentics.org/). If there's anything inaccurate here, please post an issue at [https://github.com/rdmolony/claude-flow-getting-started/issues](https://github.com/rdmolony/claude-flow-getting-started/issues)
 
Since the launch of [`Claude Code`](https://docs.anthropic.com/en/docs/claude-code/overview) in May 2025, it has become more & more widely adopted among (particularly among software engineers).

> What's `Claude Code`? 
>
> Since `ChatGPT` launched in November 2022, the predominant way of interacting with `Large Language Models` has been through a web-based chat interface. `Claude Code`, by contrast, is a terminal-based interface. A web-based interface cannot access software on your computer, or files unless you manually upload them. A terminal-based interface can. This makes it waaaay more hackable since you can combine it with whatever tools or files you want. This also makes the tool more dangerous since it can now potentially delete important files on your computer, or access credentials! So "use it with caution"

I have personally use it because it is more customisable than its web-based peers like `ChatGPT` since it can access my local files and command line tools.

I can launch it like

```sh
claude
```

and then enter ask questions in my terminal as I would in a web-based interface

```sh
> what's the difference between you and a web-based interface?

● I'm Claude Code, a CLI tool that runs directly in your terminal with several key advantages:

  Local development focus: I have direct access to your filesystem, can execute commands, edit
   files, and run builds/tests locally - the web interface can't touch your machine.

  Persistent workspace: I work in your actual project directory with git integration, while
  the web version has no filesystem access.

  MCP server integration: I can connect to Model Context Protocol servers for extended
  capabilities like swarm orchestration, GitHub automation, and persistent memory.

  Terminal-native: Optimized for command-line workflows with concise output, batch operations,
   and integration with your existing dev tools.
```

So what's [`Claude Flow`](https://github.com/ruvnet/claude-flow)?

This open source library turns `Claude Code` into an opinionated subagent orchestrator, and provides it with additional tools via the Model Context Protocol (MCP) that `Claude Code` can use to achieve its goal.

Let's focus just on `Claude Flow`'s subagent orchestration here with an example - creating a `Claude Flow` tutorial for newcomers.

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

- Creates a team of AI subagents with relevant specialties (researcher, teacher, etc)
- Assigns responsibilities to each
- Waits each subagent to complete its job
- Fetches the results from each subagent
- Combines the result

I can launch it like

```sh
npx claude-flow@alpha init
claude-flow swarm "Create a `Claude Flow` tutorial for newcomers; specifically newcomers who are comfortable on the command line. Create a new file ../_posts/2025-08-19-get-started-with-claude-flow-by-claude-flow.md"
```

and it responds with something like

```sh
> You are orchestrating a Claude Flow Swarm with advanced MCP tool coordination.

  🎯 OBJECTIVE: Create a  tutorial for newcomers; specifically newcomers who are comfortable
  on the command line. Create a new file
  ../_posts/2025-08-19-get-started-with-claude-flow-by-claude-flow.md

  # ... and ~400 more lines of instructions to teach Claude Code how to orchestrate subagents

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

The resulting `Claude Flow` tutorial is actually about `Claude Flow` this time around! However, it does nonetheless halluncinate a little & invent commands.

> So how does it work?
>
> `npx claude-flow@alpha init` creates the files (like `CLAUDE.md` & `.claude/`) defining the types of subagents `Claude Code` has access to and how to invoke and orchestrate them.
> 
> The key piece of `Claude Code` that lets `Claude Flow` create subagents is `batchtool`. It lets `Claude Flow` spin up subagents in a separate process, and thus run many subagents in parallel.

Okay so running things in parallel is obviously faster than sequential, but are there any other benefits?

The big initial attraction for me was not parallelism but rather best practices like `SPARC`, or "Specification, Pseudocode, Architecture, Refinement, Completion". This forces the subagents to plan out their algorithms during Specification, Pseudocode & Architecture and adhere to TDD during the Refinement phase. 

In my experience, this makes a big difference in improving the quality of the code output since it provides some good defaults for machine-in-the-loop validation. However, as far as I understand this mode still does not fully protect against hallucinations. For example, the AI might decide to delete the tests rather than change code to "fix" failing tests. `SPARC` is not a silver bullet. You'll likely need to know what you want beforehand & define a solid specification. 
