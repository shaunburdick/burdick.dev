# Agent Guide — burdick.dev

This file defines conventions and constraints for AI agents working on this project.

## Project overview

Static single-page consulting site for Shaun Burdick. Zero build step — plain HTML + CSS deployed to GitHub Pages.

## Key decisions

- **No framework, no build**: Pure static HTML/CSS. No npm, no bundler, no SSR.
- **GitHub Pages via Actions**: Artifact-based deployment (`actions/configure-pages@v6` + `actions/deploy-pages@v5`). Do not switch to branch-based deployment.
- **Terminal aesthetic**: Green-on-black (`#00ff00` accent, `#eee` text, `#000` background). Fira Code monospace throughout.
- **WCAG AA compliance**: Minimum 4.5:1 contrast ratios. `--muted` is `#009a00` (5.6:1 on black). `:focus-visible` outlines required. `prefers-reduced-motion` required.
- **No JS dependencies**: The only JavaScript is email-obfuscation decode. All animations are CSS.

## Coding conventions

- **No linting suppressions**: Never use `eslint-disable`, `@ts-ignore`, `@ts-nocheck`, etc.
- **No `any` types**: Full type safety if TypeScript is introduced.
- **Inline styles**: Acceptable for one-off overrides. Prefer CSS classes for reusable patterns.
- **CSS variables**: Defined in `assets/terminal.css`. Use `var(--*)` consistently.
- **Accessibility**: All sections need `aria-labelledby` pointing to their heading. Decorative elements must have `aria-hidden="true"`. Skip link required.

## Architecture

```
index.html        → All page content and page-specific styles in <style>
assets/
  terminal.css    → Design tokens (colors, fonts, spacing), reset, utilities
  favicon.svg     → Terminal-prompt favicon
.github/
  workflows/
    deploy.yml    → Build-less artifact upload + Pages deploy
```

## Prohibited changes

- Do not add a framework, build step, or package manager.
- Do not replace the artifact-based deploy workflow with branch-based deployment.
- Do not disable GPG signing.
- Do not add analytics, trackers, or external JS (CDN fonts are the exception).
