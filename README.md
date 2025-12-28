# The Somatic Space

A minimalist, calm, high-trust brochure website for somatic practitioner Francesco Mello.

## Tech Stack

- **Framework**: Astro (static-first)
- **Styling**: Tailwind CSS v4
- **Deployment**: Netlify
- **Forms**: Netlify Forms

## Development

### Prerequisites

- Node.js 18+ and npm

### Installation

```bash
npm install
```

### Running Locally

```bash
npm run dev
```

The site will be available at `http://localhost:4321/`

### Building for Production

```bash
npm run build
```

The built site will be in the `dist/` directory.

### Preview Production Build

```bash
npm run preview
```

## Deployment to Netlify

### Option 1: Connect Git Repository (Recommended)

1. Push this repository to GitHub/GitLab/Bitbucket
2. Log in to [Netlify](https://netlify.com)
3. Click "Add new site" → "Import an existing project"
4. Connect your Git provider and select this repository
5. Netlify will auto-detect the build settings:
   - Build command: `npm run build`
   - Publish directory: `dist`
6. Click "Deploy site"

The form will automatically work once deployed to Netlify (no additional configuration needed).

### Option 2: Deploy via Netlify CLI

```bash
# Install Netlify CLI globally
npm install -g netlify-cli

# Build the site
npm run build

# Deploy to Netlify
netlify deploy --prod
```

## Project Structure

```
/
├── public/              # Static assets (favicon, images, etc.)
├── src/
│   ├── layouts/
│   │   └── BaseLayout.astro    # Base layout with SEO meta tags
│   ├── pages/
│   │   ├── index.astro         # Homepage with all content
│   │   └── success.astro       # Form submission success page
│   └── styles/
│       └── global.css          # Tailwind config and global styles
├── astro.config.mjs     # Astro configuration
└── package.json
```

## Customization

### Editing Content

All content is in `src/pages/index.astro`. The file is organized in clearly labeled sections:

- Hero
- What This Is
- How Sessions Unfold
- Sessions
- Who This Is For
- Scope
- Training
- Setting
- Testimonials
- About
- Inquiry Form

### Adding Testimonials

Uncomment the testimonial structure in `src/pages/index.astro` around line 227 and add your testimonials following this format:

```html
<div class="p-8 border border-[var(--color-accent-light)] bg-[var(--color-warm-gray)]">
  <p class="text-lg mb-4">"The testimonial text here..."</p>
  <p class="text-sm text-[var(--color-text-secondary)]">— First Name L.</p>
</div>
```

### Updating Colors

Edit the CSS variables in `src/styles/global.css`:

```css
@theme {
  --color-cream: #faf8f5;
  --color-warm-gray: #f5f1ec;
  --color-text-primary: #2a2520;
  --color-text-secondary: #5a534d;
  --color-accent: #8b7d6b;
  --color-accent-light: #b5a99a;
}
```

### Adding Custom Fonts

1. Add font files to `public/fonts/`
2. Add preload links in `src/layouts/BaseLayout.astro`
3. Update font-family variables in `src/styles/global.css`

### Adding Images

1. Place images in `public/` directory
2. Reference them in your markup: `<img src="/image-name.jpg" alt="description" />`
3. For hero images or portrait photos, update the markup in `src/pages/index.astro`

Example:
```html
<div class="max-w-md mx-auto mb-12">
  <img src="/portrait.jpg" alt="Francesco Mello" class="w-full h-auto" />
</div>
```

### SEO and Meta Tags

Update the default SEO values in `src/layouts/BaseLayout.astro`:

- `title`: Default page title
- `description`: Default meta description
- `image`: Path to Open Graph image (1200x630px recommended)

### Updating the Domain

Change the `site` URL in `astro.config.mjs`:

```js
export default defineConfig({
  site: 'https://yourdomain.com',
  // ...
});
```

## Form Configuration

The contact form uses Netlify Forms. Once deployed to Netlify:

1. Form submissions will appear in your Netlify dashboard under "Forms"
2. Set up email notifications in Netlify: Site settings → Forms → Form notifications
3. You can also integrate with Zapier, Slack, etc.

## Design Principles

This site follows these design principles:

- Minimal, restrained aesthetic
- Generous whitespace
- Calm pacing
- High trust, no hype
- Copy-driven, single-scroll friendly
- Responsive and accessible
- Fast loading times

## Browser Support

This site works in all modern browsers (Chrome, Firefox, Safari, Edge).

## License

Private project for The Somatic Space.
