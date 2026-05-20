# AI Agent Team Blueprint

Digested from [@eng_khairallah1 thread](https://x.com/eng_khairallah1/status/2051596186851914019) — May 2026

## Concept

Build three AI agents (Claude + MCP servers) to cover the roles every early-stage business needs before hiring:

1. **Research Agent** — market intelligence, competitor monitoring, weekly briefs
2. **Content Agent** — ideation, drafting, editing, repurposing, scheduling
3. **Operations Agent** — email triage, meeting prep, weekly reporting

## Key Architecture Ideas

- **3-layer prompt structure** per agent: system prompt (role/expertise), workflow prompt (what to do each cycle), output prompt (format/structure)
- **Quality gates for content**: score drafts on voice match, hook strength, value density, originality — rewrite until threshold met, then human pass for personal touch
- **Shared knowledge base**: all agents read/write to a common context so they coordinate (e.g., research agent flags competitor move → content agent creates response posts → ops agent drafts outreach email)

## Implementation Steps (per agent)

### Research Agent
1. Build knowledge base: competitors, ICP, industry context
2. Connect MCP servers: web search, Google Drive, email
3. Write 3-layer prompt
4. Schedule weekly Monday sweep
5. Test 3 weeks, iterate

### Content Agent
1. Build voice/brand document from top 20 posts
2. Connect MCP servers: web search, CMS, analytics
3. Monthly workflow: 30 ideas → drafts → quality scoring → repurposing
4. Human pass for personal stories/perspective

### Operations Agent
1. Connect MCP servers: email, calendar, project management
2. Email triage workflow (categorize, draft, flag)
3. Meeting prep workflow (docs, history, action items)
4. Weekly reporting workflow (metrics, done/not done, priorities)

## Honest Assessment

- The thread is high-level — no actual prompts, configs, or code provided
- "One week per agent" is optimistic; expect weeks to months for production quality
- 70-80% coverage claim is unsupported
- The shared knowledge base idea is the most valuable and underrated concept
- Best starting point: pick ONE workflow (email triage or meeting prep) and build it properly before scaling

## Estimated Costs

| Tool | Price |
|------|-------|
| Claude Pro/Max | $20-200/mo |
| MCP Servers | Free (self-hosted, open source) |
| Web Search API | $5-50/mo |
| CMS/Scheduler | $0-30/mo |

**Total: ~$25-250/mo** vs $15K/mo for three hires
