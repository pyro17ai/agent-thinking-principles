# Agent Thinking Principles

This repository contains my global `AGENTS.md` for Codex and other AI coding agents.

The goal is simple: make the agent reason through the whole problem before it starts generating answers. I use these instructions to push the agent away from narrow edge-case suggestions and toward structured problem solving with explicit context, constraints, hypotheses, and evidence.

## Why This Exists

AI agents often answer too narrowly. They can produce a technically correct suggestion while missing the real shape of the problem: budget limits, platform constraints, user goals, available tools, or the fact that several solution paths need to be compared before one is chosen.

For example, imagine a content-making agent that needs to collect references for vertical videos through Apify. If TikTok search is limited to hashtags and the feed updates unpredictably, a shallow answer might be:

- search across more hashtags
- scrape more results each time
- deduplicate videos after scraping

That sounds reasonable until you add the real constraint: Apify calls cost money, the account has a strict budget, and increasing the number of actor runs can burn the budget without solving the core quality problem.

I do not want to paste that level of context into every prompt. Instead, I keep reusable reasoning rules in `AGENTS.md`.

## What The Agent Must Do

The instructions make the agent follow a stricter thinking flow:

1. Frame the problem before solving it.
2. Separate context, success criteria, scope, constraints, stakeholders, and sources of insight.
3. Generate possible paths before judging them.
4. Structure options with issue trees and MECE logic.
5. Turn branches into testable hypotheses.
6. Prioritize the hypotheses that can actually change the result.
7. Use evidence and external context when needed.
8. Show the final answer to the user, not the full internal worksheet.

The point is not to make the agent verbose. The point is to make the hidden reasoning more complete, so the final answer is sharper.

**IMPORTANT**: For better results, you should also install EXA MCP to enrich the tasks context.

## Repository Contents

- `AGENTS.md` - the actual global agent instructions
- `README.md` - the public explanation of the reasoning system

## How To Use

Copy the relevant parts of `AGENTS.md` into your global Codex agent instructions, or adapt them for another AI agent environment that supports persistent project or user-level instructions.

The principles work best when paired with a small set of high-quality Markdown context files for your active projects.
