# Project Rules

*(USER: Fill in the bracketed values below after initializing your project)*

## Stack
- **Framework:** [e.g., Next.js, Astro, SvelteKit]
- **Language:** [e.g., TypeScript]
- **Styling:** [e.g., Tailwind CSS, CSS Modules]
- **Database:** [e.g., PostgreSQL, MongoDB]

## File Structure
```text
src/
├── components/        # Reusable UI components
├── layouts/           # Page layouts
├── pages/             # Routes
└── assets/            # Optimized images
```

## Naming Conventions
- **Filenames:** kebab-case (e.g., `portfolio-card.tsx`)
- **Components:** PascalCase (e.g., `PortfolioCard`)
- **Functions/Variables:** camelCase (e.g., `fetchUserData`)
- **Constants:** UPPER_SNAKE_CASE (e.g., `MAX_RETRY_COUNT`)

## Code Style
- Always define typed interfaces for component props.
- No inline styles unless dynamically computed.
- Prevent N+1 queries in database calls.
- Sanitize all inputs at trust boundaries.

## Content Collections
- Always validate frontmatter schema — never allow undefined fields at runtime.
- Use explicit types for your content models.

## SEO
- Every page must use a base layout which includes meta tags, OG image, and canonical URL.
- Required props on every page: `title`, `description`.

## Images
- Always use the framework's optimized image component — never raw `<img>` tags.
- Provide `alt` text on every image.

## Performance
- Zero client-side JavaScript unless strictly required.
- External scripts loaded with `defer` or `async`.
- Images always optimized via framework's built-in tooling.