# AI UGC Content Creator

Personal project — automated slideshow and carousel production pipeline.

Digested from [@adriansolarzz thread](https://x.com/adriansolarzz/status/2053631122656092405) — May 2026

---

## Project Idea

Build an automated system that produces AI-generated UGC slideshows and carousels at volume, then distributes them across TikTok, Instagram, Facebook, and YouTube Shorts.

**Not an agency play** — a personal content engine that can be applied to any niche or offer.

---

## The Pipeline (6 Steps)

### Step 1: Daily Production Brief
Use Claude to analyze previous performance data and output a structured brief:
- Which formats to prioritize (personal story, ranked list, realization, controversial opinion, routine breakdown)
- Which platforms to weight toward based on recent performance
- Which content categories to expand vs retire
- **Time:** 30-45 min

### Step 2: Batch Script + Slide Prompt Generation
Claude generates complete slideshow scripts with slide-by-slide text overlays AND image generation prompts, calibrated per platform.

**Master prompt structure:**
```
Using the production brief above, generate:
- [X] personal story slideshow scripts for TikTok
- [X] ranked list slideshow scripts for Instagram
- [X] realization format slideshow scripts for Facebook
- [X] routine breakdown slideshow scripts for YouTube Shorts

Each script includes:
- Complete slide-by-slide text overlay structure
- Image generation prompt for each slide
- Platform-specific calibration (caption styling, format specs, audio approach)
```
**Time:** 60-90 min

### Step 3: Visual Production (GPT Image 2)

**Critical technique — character reference consistency:**
- Load the SAME character reference as multimodal input across every slide in a slideshow
- Without this, each slide looks independently fine but the slideshow feels incoherent
- Algorithm reads visual inconsistency as low-quality content

**Scene reference layer:**
- For slideshows in a consistent environment (kitchen, office, gym), load the same scene reference across all slides in that scene
- Locks lighting direction, color palette, spatial details

**Standing technical specs for every slide with a human face:**
- Skin texture: "realistic skin texture, visible pores around nose and cheeks, natural slight unevenness, no filter quality"
- Anti-polish: "casual phone framing, photographed in a real environment, not a professional set, organic not studio quality"
- Lighting as dedicated clause: "soft warm light from window at left, casting gentle shadows, no harsh highlights, skin properly illuminated without overexposure"

**Variant selection:** Generate 6-8 variants per slide, select best based on realism, detail, and the "real test" (would this pass as a real person in 2 seconds).

**Batch processing:** 6-8 slides per slideshow generated in parallel.

### Step 4: Assembly With Text Overlays

**Platform specs:**

| Platform | Aspect Ratio | Dimensions | Text Position | Notes |
|----------|-------------|------------|---------------|-------|
| TikTok | 9:16 | 1080x1920 | Upper/center, bold | Pair with trending audio |
| YouTube Shorts | 9:16 | 1080x1920 | Upper/center, bold | Separate title + description |
| Instagram Carousels | 4:5 | 1080x1350 | Bottom third, dark gradient behind text | Slide 2 = alternative hook |
| Facebook | 9:16 or 4:5 | Varies | Flexible | Longer captions (3-5x Instagram) |

**Instagram slide 2 rule:** The algorithm re-serves carousels starting from slide 2 if the viewer scrolled past slide 1. Design slide 2 as a standalone hook — it gets a second chance.

### Step 5: TikTok Trending Audio Matching
1. Research currently trending sounds in target niche
2. Filter for emotional register match (don't force mismatched audio)
3. Assign audio per slideshow
4. Monitor and rotate as trends shift (weekly cycle)
- **Time:** 5-10 min per batch

### Step 6: Schedule + Distribute
Use Later (later.com) for cross-platform scheduling from a single calendar.
- Stagger posting times 30-90 min apart across accounts
- Each account posts at its own peak engagement window
- **Time:** 30-45 min

---

## Daily Time Budget

| Phase | Time |
|-------|------|
| Analytics → Production brief | 30-45 min |
| Script + prompt generation | 60-90 min |
| Audio matching (TikTok) | 10 min |
| Assembly | 30 min |
| Scheduling | 30-45 min |
| **Total** | **~2.5-3.5 hours** |

---

## Tools Needed

| Tool | Purpose | Cost |
|------|---------|------|
| Claude Pro/Max | Script generation, analytics, briefs | $20-200/mo |
| ChatGPT Plus or GPT Image 2 API | Slide visual generation | $20/mo+ |
| Later | Cross-platform scheduling | $25-80/mo |
| Cloud phones (if multi-account TikTok) | Isolated device instances | $50-500+/mo |
| US proxies (if multi-account) | Per cloud phone | $50-200+/mo |

**Solo operator minimum:** ~$65-300/mo  
**At scale with multi-account:** $165-1,000+/mo

---

## Key Techniques to Remember

1. **Character + scene references are non-negotiable** — without them, slideshows look like random AI images stitched together
2. **Variant selection > first output accepted** — 6-8 variants per slide, pick the best
3. **Platform-specific calibration in the same Claude session** — don't adapt after the fact, generate calibrated from the start
4. **Instagram slide 2 as alternative hook** — algorithm gives it a second chance
5. **Trending audio matching for TikTok** — 10 min of research = real distribution lift
6. **Quality gates** — "organic content test" = would this pass as real UGC in the first 2 seconds?

---

## Open Questions / Next Steps

- [ ] Pick a niche to test this with
- [ ] Set up GPT Image 2 workflow for character-consistent slideshows
- [ ] Test 5 slideshows manually before automating anything
- [ ] Research cloud phone setup if going multi-account on TikTok
- [ ] Build the Claude production brief prompt tailored to chosen niche
- [ ] Evaluate Later vs alternatives for scheduling

---

## Honest Assessment

- The pipeline is real and technically sound
- "30-50 slideshows per day" is agency scale — start with 3-5 per day and prove the concept
- The hardest part is visual consistency across slides, not the scripting
- Multi-account TikTok infrastructure (cloud phones + proxies) is a separate project in itself
- Start manual, automate incrementally — don't try to build the full pipeline day one
