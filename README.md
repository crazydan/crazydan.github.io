# Daniel's Personal Homepage

A tiny terminal-inspired personal homepage for Daniel, hosted on GitHub Pages.

It is meant to work first as a professional contact page, and second as a small interactive playground for people who like poking at things.

Live site:

```text
https://cowmeuh.net
```

GitHub Pages fallback:

```text
https://crazydan.github.io
```

## Philosophy

This site is intentionally simple:

```text
1 HTML file
0 frameworks
0 build steps
0 dependencies
0 analytics
0 trackers
$0/month hosting
```

The constraint is part of the design. It should feel like someone discovered a tiny computer running at Daniel's domain.

## Tech Stack

- Static HTML
- Inline CSS
- Vanilla JavaScript
- GitHub Pages

No React, Next.js, Astro, npm, webpack, Vite, Tailwind, or build tooling.

## Local Development

Open `index.html` directly in a browser.

No install step is required.

If you prefer serving it locally:

```sh
python3 -m http.server 8000
```

Then open:

```text
http://localhost:8000
```

## Deployment

The site is deployed with GitHub Pages from this repository:

```text
crazydan.github.io
```

Expected Pages settings:

```text
Deploy from a branch
main
/ (root)
```

The custom domain is configured via `CNAME`:

```text
cowmeuh.net
```

## Development Workflow

Use `main` as the production branch. Changes should go through short-lived branches and pull requests, even as a solo developer.

Typical flow:

```sh
git switch main
git pull --ff-only
git switch -c feature/small-clear-name
```

Make the change, commit it, then push the branch:

```sh
git push -u origin feature/small-clear-name
```

Open a pull request on GitHub, wait for CI, review the diff, then squash merge into `main`.

Branch naming conventions:

- `feature/...` for new commands, visual polish, or content
- `fix/...` for bugs
- `content/...` for copy/contact updates
- `chore/...` for repository maintenance

Keep PRs small enough that the full diff can be reviewed in a few minutes.

## Continuous Integration

GitHub Actions runs on pull requests and pushes to `main`.

The workflow checks:

- Required project files exist
- `CNAME` still points at `cowmeuh.net`
- Required metadata and Easter eggs are still present
- No runtime dependency or build-tool files were introduced
- HTML validates
- Links in HTML and Markdown resolve

CI tooling is intentionally limited to GitHub Actions. The website itself still has no runtime dependencies and no build step.

## Recommended GitHub Settings

Configure these in the GitHub repository settings:

- Enable GitHub Pages from `main` / root
- Protect the `main` branch
- Require a pull request before merging
- Require status checks to pass before merging
- Require branches to be up to date before merging
- Use squash merge by default
- Automatically delete head branches after merge

For a solo personal site, requiring another reviewer is optional and probably unnecessary.

## Features

- Professional hero section
- Contact links
- System-status panel
- Interactive terminal
- Command history with arrow keys
- LocalStorage-backed ASCII pet
- Konami code Easter egg
- DevTools API exposed as `window.daniel`
- View-source Easter egg
- Responsive, accessible, lightweight layout

## Terminal Commands

Try clicking the terminal and running:

```text
help
whoami
work
projects
interests
uptime
status
pet
feed
git log
ps aux
clear
```

There are also a few deliberately unnecessary Easter eggs.

## DevTools

Open DevTools and try:

```js
daniel.help()
daniel.whoami()
daniel.pet()
daniel.source()
daniel.secret()
```

## Maintenance Notes

Keep the site small, fast, and static.

Prefer improving `index.html` in place unless the file becomes genuinely painful to maintain. Splitting CSS or JavaScript into separate files is possible, but the current one-file design is intentional.

Avoid adding third-party scripts, trackers, package managers, or build steps unless there is a very good reason.
