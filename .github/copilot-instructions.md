# Repo overview

This is a small static portfolio template (HTML + CSS). Key files:
- `index.html` — main site structure, repeatable project blocks.
- `style.css` — central stylesheet; mobile breakpoints at 900px and 600px.
- `README.md` — project purpose and contributor expectations.

## Big picture (what an agent needs to know)
- This repo is a static site: no build system, no tests. Edits are live when the files are served as static HTML.
- Projects are represented as repeatable HTML blocks (an `iframe` + a `.reflection` pane) inside `.resource-card` sections. Keep that pattern when adding projects.
- Important class names (do not rename without reason): `.resource-card`, `.project`, `.reflection`, `.navbar`, `.home-card`, `.bio`, `.skill-images`.

## Common tasks & commands
- Preview locally: open `index.html` in a browser or use VS Code "Live Server" (recommended) to get live reload.
- Manual checks: verify embeds and images load, test responsive layouts using DevTools at widths around **900px** and **600px** (these are used by the CSS media queries).
- Git workflow: stage changes (`git add -A`), commit (`git commit -m "Add: <short description>"`), push to a feature branch and open a PR. Keep commits focused (one feature/fix per PR).
- Deployment: this is a static site — enable GitHub Pages from repository settings (serve from root/main) to publish `index.html`.

## How to add a project (concrete example)
- Copy an existing project block in `index.html` (look for "<!-- PROJECT 1 -->") and update:
  - `iframe src` to your project URL
  - `title` attribute on the `iframe`
  - `h3` and reflection paragraph text
  - `Skills` list when present

Example (minimal):

```html
<section class="resource-card">
  <div class="project">
    <iframe src="PASTE-PROJECT-LINK" title="Project Title"></iframe>
    <div class="reflection">
      <h3>Project Title</h3>
      <p>3–5 sentence reflection here.</p>
      <p><strong>Skills:</strong> HTML, CSS, ...</p>
    </div>
  </div>
</section>
```

## Style & conventions
- Use CSS classes for repeated elements (the README explicitly asks to prefer classes over IDs).
- Preserve the layout structure and class names when possible — many templates and CSS rules assume the same DOM (e.g., `.project` relies on flex layout and media queries).
- Keep design changes responsive — avoid fixed widths that break smaller screens.

## Tests / Quality checks
- There are no automated tests in this repo. Typical checks are manual:
  - Open `index.html` and validate in multiple screen sizes
  - Confirm all links and embeds are not broken
  - Inspect console for JS errors (the only script only sets the footer year)

## Notes for agents
- Be concise when editing: small, well-scoped PRs are easiest to review.
- When modifying or suggesting CSS, reference `style.css` and verify both 900px and 600px breakpoints.
- When adding assets (images, favicons), reference them with relative paths and ensure files are added to the repo.

---

If anything here is unclear or you want more examples (for example: multiple project variations, accessibility checks, or recommended commit messages), tell me which sections to expand and I'll iterate. ✅