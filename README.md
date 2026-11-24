# Claude Code Agents — In-Class Assignment

Three custom **subagents** for Claude Code, built for the "Agents" in-class
assignment. Each one lives in `.claude/agents/` as a markdown file with YAML
frontmatter (`name`, `description`, `tools`, `model`) followed by the
agent's system prompt. Claude Code reads these automatically and can either
delegate to them by itself when a task matches their `description`, or be
invoked directly by name.

All three are built around a real project I'm already running: an automated
job search tracker for entry-level roles in business development, data
analytics, marketing, and fashion/retail.

## Agents

### `resume-tailor`
Takes a job posting and my resume and rewrites resume bullets to match that
specific posting — without inventing experience, metrics, or skills I don't
actually have. Flags any real gaps between the posting and my background so
I know what to be ready to address in an interview.

### `interview-prep-coach`
Takes a job posting (and optionally my resume) and generates likely
behavioral and role-specific interview questions, notes on what a strong
STAR-structured answer touches on, a few researched talking points about the
company, and smart questions to ask the interviewer back.

### `job-scam-screener`
Screens an entry-level job posting for common scam/MLM/commission-only red
flags (pay far above market, vague duties, "confidential" employers,
staffing agencies hiding the end client, foreign company registration for a
"US remote" role, etc.) and gives a quick verdict: looks fine / proceed with
caution / likely a scam pattern.

## How to use

```bash
# From a Claude Code session in this repo:
# Claude Code will auto-detect agents in .claude/agents/
# and can delegate to them based on their `description`,
# or you can ask for one directly, e.g.:
"Use the resume-tailor agent to tailor my resume to this posting: <paste>"
```

## Why these three

They cover three different stages of a real job search — preparing an
application, preparing for the interview, and protecting against scams —
and were designed against postings I'm actually tracking, not hypothetical
examples.
