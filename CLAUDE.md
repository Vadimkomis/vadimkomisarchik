# Claude Guidelines for vadimkomisarchik Blog

This document provides instructions for working with Vadim Komisarchik's personal blog—an Astro-based site covering engineering, entrepreneurship, and building systems that last.

---

## Project Overview

| Aspect | Details |
|--------|---------|
| Framework | Astro 5.x + TypeScript |
| Styling | Tailwind CSS 4.x |
| Content | Markdown files in `src/data/blog/` |
| Layouts | `src/layouts/` (Main.astro, AboutLayout.astro) |
| Components | `src/components/` (Card, Pagination, ShareLinks, Breadcrumb, etc.) |
| Config | `src/config.ts` for site metadata, `src/content.config.ts` for schema |

### Key Commands

```bash
npm run dev          # Start development server
npm run build        # Type-check + build + generate Pagefind index
npm run preview      # Preview production build
npm run format       # Format with Prettier
npm run lint         # Lint with ESLint
```

### Content Schema (Frontmatter)

Every blog post requires:
- `title` — Post title (becomes the h1)
- `description` — Used for SEO and excerpts
- `pubDatetime` — ISO 8601 format (e.g., `2025-11-20T15:22:00Z`)

Optional fields:
- `modDatetime` — Last modified date
- `author` — Defaults to "Vadim Komisarchik"
- `slug` — Custom URL slug (defaults to filename)
- `featured` — Show on homepage featured section
- `draft` — Hide from production
- `tags` — Array of strings (defaults to `["others"]`)
- `ogImage` — Custom Open Graph image
- `canonicalURL` — For syndicated content
- `hideEditPost` — Disable edit button for this post

---

## Editor Reading Guidelines

When reviewing blog posts as an editor, evaluate each piece through these lenses:

### 1. Grammar

**What to check:**
- Subject-verb agreement ("The team works" not "The team work")
- Correct tense usage and consistency throughout the post
- Proper use of articles (a, an, the)
- Comma placement, especially with introductory phrases and lists
- Apostrophe usage (its vs. it's, possessives)
- Run-on sentences and comma splices
- Dangling modifiers and misplaced phrases

**Common mistakes to flag:**
- its/it's confusion
- their/there/they're errors
- affect/effect misuse
- who/whom (when used)
- Inconsistent capitalization in headings
- Missing Oxford commas in lists (or inconsistent use)

**Voice preference:**
- Active voice over passive ("I built this" not "This was built by me")
- Direct statements over hedging ("This works" not "This might potentially work")
- Eliminate filler words: just, really, very, actually, basically, literally, stuff

### 2. Spelling

**Systematic checks:**
- Technical terms and product names (case-sensitive)
- Proper nouns (company names, people, places)
- Common typos that spell-check misses (form/from, then/than, loose/lose)
- Consistency in British vs. American spelling (prefer American: "color" not "colour")
- Hyphenation consistency (real-time vs realtime—pick one and stick with it)

**Tools to run:**
```bash
npx prettier --check .
```

### 3. Readability

**Sentence level:**
- Aim for sentences under 20 words when possible
- Vary sentence length to create rhythm (short punchy sentences followed by longer explanatory ones)
- One idea per sentence
- If a sentence needs re-reading to understand, rewrite it

**Paragraph level:**
- Maximum 4 sentences per paragraph
- Each paragraph should have a single focus
- Strong opening sentence that signals what the paragraph covers
- White space is a feature, not a bug—break up walls of text

**Structure level:**
- Descriptive headings every 200-300 words
- Headings should be scannable—readers should understand the post from headings alone
- Use h2 (##) for main sections, h3 (###) for subsections (h1 is reserved for title)
- Bulleted lists for unordered items, numbered lists for sequences or ranked items
- Tables for comparative information
- Code blocks with syntax highlighting for any code

**Flow:**
- Smooth transitions between paragraphs (avoid jarring topic shifts)
- Logical progression of ideas (setup → development → conclusion)
- No orphaned ideas—every point should connect to what comes before and after

### 4. Storytelling

Every post should have a narrative arc, even technical ones:

**The Hook (First 2 sentences):**
- Must grab attention immediately
- State a problem, pose a question, or make a bold claim
- The reader should know why they should care within 30 seconds
- Example from existing post: *"'Never give up' is advice people throw around casually. But taken literally, it's terrible."*

**The Setup:**
- Establish context and stakes
- What's the conventional wisdom? What's the problem with it?
- Ground abstract ideas in concrete examples

**The Build:**
- Develop the argument or story with specifics
- Include real examples, code, data, or personal experience
- Build tension or curiosity—what's the insight coming?
- Each section should raise questions the next section answers

**The Payoff:**
- Deliver the insight or solution
- Make it concrete and actionable
- The reader should think "I can use this"

**The Close:**
- End with momentum, not a whimper
- Call to action, provocative question, or challenge
- Leave the reader with something to do or think about
- Signature sign-off is acceptable (e.g., "✌️ V.K.")

**Red flags in storytelling:**
- Posts that meander without a clear point
- Burying the lead (the interesting part is in paragraph 5)
- Ending with "In conclusion..." followed by a summary (just end strong)
- No concrete examples—all abstract advice
- Missing the "so what?"—why should the reader care?

---

## The Rebel and Creator Archetypes

All content on this blog is written from the perspective of two brand archetypes. When editing, ensure both voices are present:

### The Rebel

The Rebel questions what everyone else accepts. This voice:

- **Challenges conventional wisdom** — Names the "accepted approach" and explains why it's wrong or incomplete. Doesn't accept "best practices" at face value.
- **Speaks with conviction** — Uses direct, confident language. No hedging with "I think maybe" or "it could be that."
- **Values authenticity over conformity** — Shares real failures, not just highlight reels. Admits when something didn't work.
- **Provokes without being edgy** — The goal is to make people think, not to shock. Contrarian for a reason, not for attention.
- **Questions the status quo** — Asks "why do we do it this way?" and isn't satisfied with "because that's how it's done."

**Rebel voice in practice:**
> "Never give up" is advice people throw around casually. But taken literally, it's terrible.

> I refuse to be vanilla. If I have weak spots, they're going on the page.

### The Creator

The Creator builds and teaches. This voice:

- **Shows the work** — Doesn't just state conclusions; walks through the process. Shares the craft behind the result.
- **Makes things tangible** — Every post should include something actionable: code, a checklist, a framework, a tool, a decision.
- **Teaches through doing** — Uses real examples from actual projects. References specific products, commits, or experiences.
- **Celebrates craft** — Cares about doing things well, not just doing things fast. Respects the details.
- **Transforms ideas into outcomes** — Moves from abstract to concrete. Theory is only valuable if it leads to action.

**Creator voice in practice:**
> Take my last two products: AI Magic Touch, ProblemSpotter. Neither got traction. Here's what I learned...

> An MVP is the smallest marketable piece of value you can put into the world—something real people can actually use.

### Blending the Archetypes

The best posts demonstrate both:

1. **Rebel sets up the problem** — "Here's what everyone does, and here's why it's broken"
2. **Creator delivers the solution** — "Here's what I built instead, and here's how you can too"

A post that's all Rebel is just complaining. A post that's all Creator lacks edge. The blend creates posts that challenge thinking AND provide value.

**Questions to ask when editing:**
- Does this post challenge something? (Rebel check)
- Does this post teach or build something? (Creator check)
- Is there a tangible takeaway the reader can use? (Creator check)
- Is there conviction in the voice, or is it hedged and safe? (Rebel check)
- Does the author share real experience, including failures? (Both)

---

## Post Interconnection

No post should exist in isolation. The blog is a connected body of work, not a collection of random articles.

### Why This Matters

- Readers who find one post should discover related content
- Ideas build on each other across posts
- The blog tells a larger story over time
- SEO benefits from internal linking
- Creates a sense of ongoing narrative

### Connection Requirements

**Every new post must:**

1. **Reference at least one previous post** — Either link directly or mention a concept introduced elsewhere
   - Good: "In my post on giving up, I talked about pivoting from failed products..."
   - Good: "This builds on [Never Give Up](/posts/Never%20Give%20Up) where I discussed..."

2. **Fit thematically** — Posts should relate to the blog's core themes:
   - Engineering and building
   - Entrepreneurship and shipping products
   - Focus, discipline, and intentionality
   - Learning from failure
   - Questioning conventional approaches

3. **Continue conversations** — If a post introduces a concept, future posts should reference and build on it
   - The "WTF" series is a good example of ongoing narrative

### Updating Existing Posts

When a new post extends a topic covered previously:
- Consider adding a "See also" or "Related" link to the older post
- Update the older post's description if the new post supersedes it
- Check if tags should be aligned

### Identifying Disconnected Posts

Flag posts that:
- Don't reference any other content on the blog
- Cover a topic completely unrelated to existing themes
- Could exist on any blog (no personal voice or connection to author's journey)
- Miss obvious opportunities to link to related posts

### Series and Continuity

Some posts work as series (like "Vadim, WTF!" parts 1 and 2). When editing series:
- Ensure each part links to previous parts
- Maintain consistent formatting and structure
- Each part should stand alone but reward reading the series
- The series should have a clear arc or progression

---

## Technical Standards

### File Organization

```
src/data/blog/
├── _releases/           # Underscore prefix = doesn't affect URL
├── examples/            # Subdirectory affects URL path
├── post-name.md         # Standard post
└── 2025/               # Year-based organization (optional)
    └── post.md         # URL: /posts/2025/post
```

### Markdown Best Practices

- Use `## Table of contents` (h2) to auto-generate TOC
- Images: prefer `src/assets/` for optimization, use relative paths
- Code blocks: specify language for syntax highlighting
- Use `<figure>` and `<figcaption>` for images with captions
- Keep frontmatter consistent with schema

### Pre-Publish Checklist

```bash
npm run format          # Auto-format
npm run lint            # Check for issues
npm run build           # Verify build succeeds
```

### Component Usage

- `Card.astro` — For post listings
- `LinkButton.astro` — For CTAs and external links
- `ShareLinks.astro` — Social sharing (auto-included in post layout)
- `BackToTopButton.astro` — Long post navigation
- `Breadcrumb.astro` — Navigation trail

---

## Quick Reference: Editor Checklist

Before approving any post, verify:

- [ ] **Grammar**: No errors, active voice, no filler words
- [ ] **Spelling**: All words spelled correctly, consistent terminology
- [ ] **Readability**: Short paragraphs, clear headings, logical flow
- [ ] **Hook**: First 2 sentences grab attention
- [ ] **Storytelling**: Clear arc with setup, build, and payoff
- [ ] **Rebel voice**: Challenges something, speaks with conviction
- [ ] **Creator voice**: Builds or teaches something tangible
- [ ] **Connection**: Links to at least one other post
- [ ] **Thematic fit**: Relates to blog's core themes
- [ ] **Frontmatter**: All required fields present and valid
- [ ] **Actionable close**: Ends with something the reader can do

---

## The One-Line Summary

Read every post asking: *Does this challenge conventional thinking (Rebel) while teaching something practical (Creator), and does it connect to the larger story this blog is telling?*
