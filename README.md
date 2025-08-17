# Mythic Nav — Fantasy Neon Menu (HTML + CSS)

Neon-glass, sticky header with gradient underlines, CSS-only dropdowns (`<details>`), and a checkbox-driven hamburger. No JavaScript required.

## Structure
```text
mythic-nav/
├─ index.html
└─ style.css
```

## Quick Start
1. Save the provided HTML as `index.html` and CSS as `style.css`.
2. In `<head>` include the stylesheet:
   ```html
   <link rel="stylesheet" href="style.css" />
   ```
3. Open `index.html` in your browser.

## Features
- **Cosmic background:** layered radial/conic gradients + subtle star/twinkle effects.
- **Glass header:** translucent card with `backdrop-filter` and gradient border.
- **Gradient underline:** link/summary `::after` animates on hover/focus/active.
- **Dropdowns:** pure CSS via `<details><summary>…</summary><ul class="dropdown">…</ul></details>`.
- **Mobile nav:** hidden checkbox `#nav-toggle` + `.hamburger` toggles `.nav` (`max-height`) under 900px.
- **Dark mode:** token swap using `prefers-color-scheme: dark`.

## Customize
- **Palette tokens (`:root`):** `--primary`, `--accent`, `--magenta`, `--fg`, `--bg`.
- **Glass/blur:** `--glass` or remove `backdrop-filter` for broader support.
- **Radii & shadows:** `--radius`, `--shadow-*`.
- **Container width:** `--maxw`.
- **Breakpoint:** change `@media (max-width: 900px)`.
- **CTA glow ring:** `.btn-cta` conic-gradient border (`animation: spin …`).

## Accessibility
- Active link uses `aria-current="page"`.
- `summary` is keyboard-focusable; underline also shows on `:focus-visible`.
- Hamburger is associated with the checkbox via `label[for="nav-toggle"]`.

## Troubleshooting
- **Hamburger not opening?** Ensure DOM order is `input#nav-toggle` → `label.hamburger` → `.nav`, and `for="nav-toggle"` matches the `id`.
- **No blur?** `backdrop-filter` may be unsupported; add a solid background fallback.
- **Dropdown overlaps on desktop?** `.dropdown` is `position: absolute`; on mobile it becomes `position: static` inside the panel by design.
- **Two HTML docs pasted together?** Keep a single `<!DOCTYPE html>…</html>` page; move all CSS to `style.css`.
