# AI Agent Team Blueprint

Digested from [@eng_khairallah1](https://x.com/eng_khairallah1/status/2051596186851914019) and [@cyrilXBT](https://x.com/cyrilxbt/status/2052570518667378918) — May 2026

## Concept

Build specialized AI agents (Claude + MCP servers + N8N) to cover the roles every early-stage business needs before hiring:

1. **Research Agent** — market intelligence, competitor monitoring, weekly briefs
2. **Content Agent** — ideation, drafting, editing, repurposing, scheduling
3. **Operations Agent** — email triage, meeting prep, weekly reporting
4. **Customer Communication Agent** — categorize inquiries, draft responses, route complex issues
5. **Analytics Agent** — analyze performance across all agents, optimize the system monthly

## Key Architecture Ideas

- **3-layer prompt structure** per agent: system prompt (role/expertise), workflow prompt (what to do each cycle), output prompt (format/structure)
- **Quality gates for content**: score drafts on voice match, hook strength, value density, originality — rewrite until threshold met, then human pass for personal touch
- **Shared knowledge base**: all agents read/write to a common context so they coordinate (e.g., research agent flags competitor move → content agent creates response posts → ops agent drafts outreach email)
- **ROUTINE/CUSTOM/ESCALATE triage** for customer comms: every incoming message gets categorized. ROUTINE = template response. CUSTOM = draft needing review. ESCALATE = human only. When uncertain, always ESCALATE. This prevents the agent from making promises or handling edge cases it shouldn't.
- **Analytics meta-agent**: one agent reads performance data monthly and produces specific changes to the other agents' prompts. Content agent voice profile gets refined, research topics get updated, communication templates get optimized. This is what makes the system compound instead of plateau.
- **Voice profile extraction**: feed Claude your 20 best-performing posts, ask it to extract patterns (sentence length, capitalization habits, vocabulary level, structural tendencies, what you never say). Use that extracted profile as the voice section of your content agent's system prompt.
- **N8N as orchestration layer**: use N8N to schedule agents and chain outputs. Research agent's Monday brief triggers content agent's drafting queue. Analytics agent's monthly report triggers prompt updates across all agents.

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

### Customer Communication Agent
1. Define hard rules: what it can/can't promise, pricing boundaries, escalation triggers
2. Build ROUTINE/CUSTOM/ESCALATE categorization
3. Run in review mode for 2 weeks — approve every output before sending
4. After 100+ approved outputs, move ROUTINE to auto-send with daily audit

### Analytics Agent (build last — needs data from the others)
1. Wait until other agents have 4-6 weeks of data
2. Feed performance data monthly: content metrics, comms volume, research utility
3. Agent produces: top 3 patterns, single highest-leverage action, prediction, and specific prompt changes for other agents
4. Apply the recommended prompt updates, measure impact next month

## Build Order

Don't build all at once. One agent per week, in this order:
1. **Week 1:** Research Agent + shared knowledge base
2. **Week 2:** Content Agent, connected to research output
3. **Week 3:** Operations Agent, reporting mode only for first week
4. **Week 4-5:** Communication Agent, review mode for 2 weeks minimum
5. **Week 6:** Analytics Agent, once you have enough data to analyze

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
| N8N (self-hosted) | ~$5/mo on a VPS |
| Obsidian | Free |

**Total: ~$30-255/mo** vs $15K+/mo for hires
