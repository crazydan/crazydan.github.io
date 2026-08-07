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
