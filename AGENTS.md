# Claude Rules for the Astro Blog

These guidelines keep the `vadimkomisarchik` Astro blog consistent, readable, and aligned with the brand’s Creator/Rebel identity.

## Project Snapshot
- Framework: Astro + TypeScript (see `astro.config.ts`)
- Content: Markdown/MDX in `src/content/posts`
- Layouts: `src/layouts` (`Layout.astro`, `PostDetails.astro`, etc.)
- Components: `src/components` (Pagination, Breadcrumb, ShareLinks, etc.)

## Brand Identity & Voice
- **Archetype blend**: Lead with creator energy (teach, build, expose craft). Inject rebel energy by challenging stale assumptions and offering bold alternatives.
- **Tone**: Confident, precise, never snarky. Invite readers to experiment while questioning the status quo.
- **Perspective**: Author speaks as a practitioner who ships. Don’t lecture without showing receipts (demos, data, or lived experience).

## Content Craft Guidelines
### Readability & Flow
- Keep paragraphs ≤ 4 sentences, sentences ≤ 20 words when possible.
- Use descriptive headings every 200–300 words; mirror the navigation trail shown by `Breadcrumb.astro`.
- Break complex ideas into numbered steps or tables; prefer Astro `MarkdownLayout` components for callouts/admonitions.

### Grammar & Spelling
- Run every post through a grammar/spell check (e.g., `npx cspell "**/*.mdx"` and `npx prettier --check`).
- Favor active voice and plain English; avoid filler like “just”, “really”, “stuff”.
- Write dates in ISO format (`2024-05-18`) to match the frontmatter schema.

### Connection to Previous Posts
- Always link to at least one earlier post or archive page; use `Astro.glob` metadata for accurate titles and dates.
- Reference prior learnings explicitly (“In _How Rebels Ship Fast_, we…”). Summarize the takeaway before presenting the new angle.
- Update relevant posts’ “See also” sections whenever a new post extends the topic.

### Rebel + Creator Storytelling
- Present the “accepted approach” in 1–2 lines, then contrast it with the blog’s crafted alternative.
- Include a tangible make/build section (code, checklist, downloadable asset) so readers leave with something they can create.
- Close with a prompt that nudges readers to break a rule responsibly (“What would you redesign if X no longer constrained you?”).

## Astro Authoring Standards
- **Frontmatter**: `title`, `description`, `pubDate`, `updatedDate`, `tags`, `heroImage`, `related` (slugs). All required unless the content collection schema changes.
- **Collections**: Register new content types in `src/content/config.ts`; run `npx astro check --watch` to validate.
- **MDX Enhancements**: Import shared components (e.g., `LinkButton`, `Card`) instead of recreating inline HTML.
- **Assets**: Store hero images under `public/blog/`; use descriptive filenames (`topic-angle-source.jpg`).

## Layout & Component Use
- Keep typography hierarchy consistent with `Main.astro`; never override heading sizes inside posts except via scoped styles.
- Use `ShareLinks.astro` + `BackToTopButton.astro` on all article pages.
- Pagination pages must include `Pagination.astro` and `Breadcrumb.astro` for continuity.
- For experimental UI, add a new component under `src/components`, export from an index file, and document props in-code.

## Technical Quality & Tooling
- Commands before publishing:
  1. `npm run lint`
  2. `npm run format`
  3. `npm run astro check`
  4. `npm run test` (if applicable)
- Optimize long lists via Astro `paginate` helpers; avoid loading >20 posts on a single page.
- Defer non-critical scripts with `client:idle` or `client:visible`.
- Respect accessibility: test with `npm run astro check -- --diagnostics accessibility`.

## Review Checklist (per post or feature)
- [ ] Narrative ties back to at least one earlier article.
- [ ] Voice balances creator guidance with rebel challenge.
- [ ] Spelling/grammar tools report zero errors.
- [ ] Frontmatter validated; tags consistent with `/src/content/config.ts`.
- [ ] CTA encourages readers to build or rethink something.
- [ ] Layout uses shared components; no inline style drift.

When in doubt, build something useful, tell the story of how you broke the boring way to reach it, and document it with clarity so others can create their own rebellion.
