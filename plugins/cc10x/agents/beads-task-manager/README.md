# Beads Task Manager Agent

## Overview

A cc10x agent that provides persistent, graph-based task management using bd (beads) issue tracker. This agent replaces TodoWrite for complex, multi-session work requiring dependency tracking and context preservation across compaction cycles.

## When to Use

### Use beads-task-manager for:
- Multi-session work spanning days or weeks
- Complex dependency graphs and blocked tasks
- Strategic planning and research work
- Side quests and exploratory work
- Project memory that survives compaction

### Use TodoWrite for:
- Simple single-session tasks
- Linear step-by-step work
- Quick checklists
- Work that doesn't need to persist

## Key Features

- **Automatic session start**: Checks for ready work at the beginning of each session
- **Proactive issue creation**: Files bugs/tasks during exploration
- **Context preservation**: Rich notes that survive compaction
- **Dependency management**: Blocked/blocking relationships
- **Strategic planning**: Design notes and research documentation

## Invocation

This agent can be invoked directly (unlike workflow-specific agents):

```
User: Let's track this work using beads
Claude: [Invokes beads-task-manager agent via Task tool]
```

Or it can be used implicitly when the user mentions:
- "track with beads"
- "create a bead"
- "use bd for this"
- "persistent task tracking"

## Integration

Works alongside other cc10x agents:
- **planner**: Creates architecture, beads-task-manager tracks implementation
- **component-builder**: Builds features, files improvements via beads
- **bug-investigator**: Finds bugs, files them via beads
- **code-reviewer**: Finds issues, creates tasks via beads

## Requirements

- bd (beads) must be installed and available in PATH
- Either `.beads/` in project or `~/.beads/` globally
- If bd is not available, agent gracefully falls back to TodoWrite

## Testing

To test the agent:

1. Ensure bd is available: `which bd`
2. Check for beads database: `ls .beads/` or `ls ~/.beads/`
3. Invoke agent through Claude Code
4. Verify it checks ready work at session start
5. Test creating/updating/closing issues

## Examples

See AGENT.md for comprehensive examples and workflows.
