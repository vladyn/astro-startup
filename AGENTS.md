# Repository Guidelines

## Project Structure & Module Organization

This is an Astro app. Routes live in `src/pages/` (`about.astro` becomes `/about`), reusable components in `src/components/`, layouts in `src/layouts/`, and global styles in `src/styles/`. Keep processed images in `src/assets/`; use `public/` for unchanged files such as `favicon.svg`. Place tests beside source files or in `tests/`, consistently. Configuration lives in root `astro.config.mjs`, `tsconfig.json`, and `package.json`.

## Astro Component Rules

Use `.astro` components for HTML content. Put imports, data loading, and server-side logic in frontmatter; frontmatter does not run in the browser. Add a `<script>` for small browser interactions, and use a framework component with a `client:*` directive when its interactive state needs one. Put shared markup in a layout with a `<slot />`. Use component-scoped `<style>` rules by default; reserve global CSS for resets, tokens, and typography.

## Build, Test, and Development Commands

Run `npm install` after dependency changes, then `npm run dev` for the local server, `npm run check` for Astro and TypeScript diagnostics, `npm run build` for production output, and `npm run preview` to inspect the build. Report results only for commands that have run.

## Coding Style & Naming Conventions

Use two-space indentation until a formatter defines the style. Name components and layouts in PascalCase (`SiteHeader.astro`, `BaseLayout.astro`); name routes for their URL paths (`src/pages/contact.astro`). Keep TypeScript types explicit at component boundaries. Use semantic HTML, meaningful link text, labels for form controls, and descriptive image `alt` text. Prefer Astro's image tools for imported images that need optimization.

## Testing Guidelines

No test framework or coverage threshold is configured. When tests are added, use Vitest for utilities and Playwright for route and browser behavior; name files `*.test.ts` or `*.spec.ts` consistently. Cover navigation, forms, and data transformations as they appear. Run the configured tests and production build before submitting a pull request.

## Security & Configuration

Keep secrets out of Git and browser code. Variables prefixed `PUBLIC_` are available to client code, so use that prefix only for values safe to expose. Document required variable names in an example environment file without real values.

## Commit & Pull Request Guidelines

There is no Git history to establish a convention. Use short, imperative commit subjects, such as `Add site navigation`. Pull requests should explain the change, list checks run, link relevant issues, and include screenshots for visible UI changes.
