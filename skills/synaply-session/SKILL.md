---
name: synaply-session
description: >
  Runs a full Synaply knowledge synthesis session. Pulls from all connected sources,
  synthesizes insights using the user's Synaply schema, and publishes to ~~synaply.
  Trigger with: "run my Synaply session", "capture my insights", "log my insights",
  "post to Synaply", "Synaply session", "start my Synaply", "capture what I've learned",
  "synthesize my knowledge", "run insights". Also triggers when the user says
  "auto publish to Synaply" or "publish everything to Synaply automatically".
tools:
  - mcp__synaply__get_insight_schema
  - mcp__synaply__get_last_submission
  - mcp__synaply__get_insights
  - mcp__synaply__create_insight
  - mcp__synaply__publish_insight
  - mcp__synaply__update_insight
  - mcp__synaply__search_insights
---

# Synaply Knowledge Synthesis Session

Execute the full Synaply session workflow. Load the complete workflow instructions from `references/workflow-instructions.md` and the synthesis methodology from `references/knowledge-synthesis-guide.md` before starting any steps.

## How to run

Read both reference files in full at the start of every session. They are the authoritative source for how to execute this workflow — do not rely on summarized versions or prior session memory.

Follow the 10-step workflow in `references/workflow-instructions.md` exactly and in order:

1. Retrieve full schema
2. Resolve timeframe
3. Gather source material
4. Signal density check
5. Synthesize knowledge
6. Sanitize
7. Infer user tone
8. Draft insights
9. QA pass
10. Present for review (or auto-publish if specified)

## Synthesis approach

During step 5 (Synthesize Knowledge), apply the cross-source synthesis methodology from `references/knowledge-synthesis-guide.md`. Key principles:

- Deduplicate: merge the same information appearing across multiple sources into a single narrative item, citing all sources
- Cluster: group related results by theme, not by source
- Rank: order by relevance to each Insight Type, weighted by freshness and authority
- Assess confidence: flag when sources conflict or when information may be outdated
- Synthesize: produce a narrative view of what happened, with source attribution — not a raw list of results

Private signals (direct messages, email, private channels) are the richest source and should be prioritized. The goal is the unfiltered thinking and real decisions that never make it into formal documentation.

## Connected tool

This skill uses ~~synaply (the Synaply MCP connector) for all schema retrieval, drafting, and publishing. Every tool call that reads from or writes to Synaply goes through this connector. Do not proceed if ~~synaply is not connected — surface the message from the workflow instructions instead.

## Auto-publish mode

If the user says "auto publish", "publish everything automatically", or schedules this skill to run automatically (e.g. via a daily schedule), skip the manual review step (step 10) and publish all QA-approved drafts in sequence without prompting. Notify the user with a summary when complete.

## On completion

After publishing, give the user a brief summary:
- How many insights were published
- Which divisions and Insight Types were covered
- The timeframe that was synthesized
- Any drafts that were discarded and why (in aggregate, not individually)

Do not give an extensive debrief. One short paragraph is sufficient.
