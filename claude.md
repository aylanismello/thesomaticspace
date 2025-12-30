# Claude Code Instructions for The Somatic Space

## Project Overview

This is a minimalist, single-page brochure website for somatic practitioner Francesco Mello.

**Core Technical Goals:**
- Calm, restrained design with generous whitespace
- Single-scroll experience with full-height snap sections
- Fast, lightweight (Astro static site)
- Forms handled via Netlify (no third-party services)
- Grounded, non-hype tone throughout all content

## Critical Rules

### DO NOT Run Servers or Scripts Unless Explicitly Asked

**NEVER run these commands unless the user explicitly requests them:**
- `npm run dev` / `npm start` / any dev server
- `npm run build`
- `npm test` / `npm run test`
- `npm run preview`
- Any other npm scripts

**Why:** The user will run these themselves when they need to. Running servers in Claude Code creates background processes and is not helpful.

**Exception:** Only run these if the user explicitly says "run the dev server" or "build the site" or similar direct request.

## Content and Tone Guidelines

### Writing Tone Rules
- **NO hype language** - avoid "transform your life," "revolutionary," "amazing," etc.
- **NO spiritual posturing** - keep grounded and embodied
- **NO aggressive CTAs** - no popups, no pressure tactics
- **NO overclaiming** - avoid words like "cure," "heal," "fix" as promises
- Use **short, grounded sentences**
- Maintain **adult, contained, non-salesy tone**
- Focus on **felt experience** and **body-based language**

### Brand Voice
- Serious, grounded, non-clinical
- Healing-oriented without promising outcomes
- Emphasizes safety, pacing, and client agency
- Professional but warm
- Trust-building through restraint, not persuasion

### The Word "Trauma"
- Can appear once in context if needed
- NEVER use as a headline or promise ("heal your trauma")
- Keep clinical language minimal

## Design Principles

### Visual Intent
- Extremely simple, restrained, "private studio" feeling
- Calm pacing with large whitespace
- Short sections with generous breathing room
- Trust signals: face + scope + testimonials + clear descriptions
- Single-scroll friendly (avoid pagination)

### Typography
- Serif for headings (quiet authority)
- Sans-serif for body (clean readability)
- Generous line-height (1.7 for body text)
- Limited type scale (don't go crazy with sizes)

### Color Palette
- Neutral, warm tones (cream, warm grays, soft browns)
- Avoid: bright colors, high contrast, saturated hues
- Current palette in `src/styles/global.css` is intentional

## Code Standards

### When Making Changes

1. **Read files first** - ALWAYS read before editing
2. **Minimal changes** - only change what's necessary
3. **Preserve formatting** - respect existing indentation and style
4. **No over-engineering** - keep it simple
5. **No unnecessary abstractions** - this is a brochure site, not an app

### What NOT to Do

- Don't add features that weren't requested
- Don't create components unless necessary
- Don't add dependencies without asking
- Don't refactor working code unless asked
- Don't add comments or docstrings to unchanged code
- Don't add error handling for scenarios that can't happen
- Don't create utility functions for one-time operations

### File Organization

```
src/
├── layouts/
│   └── BaseLayout.astro     # SEO, meta tags, HTML structure
├── pages/
│   ├── index.astro          # All content lives here
│   └── success.astro        # Form success page
└── styles/
    └── global.css           # Tailwind theme + global styles
```

**DO NOT** create new folders or files unless explicitly needed.

## Site Purpose and Architecture

**Main Goal:** A minimalist, single-page brochure site that builds trust through restraint, clarity, and grounded language. The site should guide potential clients to understanding the work and booking sessions without pressure tactics.

**Technical Architecture:**
- Single-page scroll experience with snap sections
- Content lives in `src/pages/index.astro`
- Data abstracted to `src/content/data.js` where applicable
- Sections use full-height viewport with background images
- Navigation via scroll or section dots (fixed sidebar)

### When Editing Content

- Preserve the grounded, body-based language
- Keep sections concise (avoid long paragraphs)
- Use bullets for clarity when listing items
- Respect the "no hype" rule
- Sections are clearly marked in the code with comments

## Forms

- Uses **Netlify Forms** (built-in)
- Form submissions go to Netlify dashboard
- NO third-party form services
- Keep form fields minimal and necessary

## Images

- Place in `public/` directory
- Optimize before adding (no massive files)
- Use semantic alt text
- Reference as `/image-name.jpg` in markup

## SEO

- Meta tags in `BaseLayout.astro`
- Keep titles under 60 characters
- Keep descriptions 150-160 characters
- Use semantic HTML (proper heading hierarchy)
- Don't keyword stuff

## Deployment

- Site deploys to **Netlify**
- Build command: `npm run build`
- Publish directory: `dist`
- Forms work automatically on Netlify (no setup needed)

## Testing Approach

- **DO NOT run tests unless explicitly asked**
- Manual testing in browser is preferred
- User will test responsive design themselves
- User will test form submission after deployment

## When User Asks for Changes

1. Read the relevant files first
2. Make targeted, minimal edits
3. Explain what you changed and why
4. DO NOT rebuild or restart dev server unless asked

## Common Requests & How to Handle

### "Update the copy in [section]"
- Read `src/pages/index.astro`
- Find the section (they're labeled with HTML comments)
- Make the edit
- Done. Don't run anything.

### "Change the colors"
- Read `src/styles/global.css`
- Update CSS variables or color values
- Done. Don't run anything.

### "Add/update content"
- Read the relevant file (`src/pages/index.astro` or `src/content/data.js`)
- Make targeted edits
- Done. Don't run anything.

### "Add an image"
- Ask where the image file is
- Update markup in the relevant file
- Remind them to place image in `public/`
- Done. Don't run anything.

## What to Ask Before Changing

- If adding new sections: "Where should this go?"
- If changing tone: "Is this language grounded enough?"
- If adding features: "Do you really need this?"
- If unsure about copy: "Should this follow the 'no hype' rule?"

## Git Commits

When the user asks you to commit:
- Use clear, concise commit messages
- Focus on *what* changed, not *why* (that's in the code)
- Follow existing commit style if there is one

## Summary

**Remember:**
- This is a calm, minimal brochure site
- DO NOT run servers or scripts unless asked
- Preserve the grounded, body-based tone
- Keep changes minimal and targeted
- Trust the existing design decisions
- Let the user test their own site

Got it.
