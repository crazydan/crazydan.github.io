# Session Context

Last updated: 2026-08-08

## Repository

- Path: `/Users/daniel/Projects/crazydan.github.io`
- Remote: `git@github.com:crazydan/crazydan.github.io.git`
- Branch used in this session: `main`
- Live domain: `https://cowmeuh.net`
- GitHub Pages fallback: `https://crazydan.github.io`
- Site entrypoint: `index.html`

## Project Intent

- Personal one-page homepage for Daniel.
- Professional contact page first, terminal-inspired playground second.
- The site should feel handcrafted, fast, static, and intentionally dependency-free.
- Keep the core implementation in one HTML file unless maintenance genuinely becomes painful.

## Hard Constraints

- No framework.
- No build step.
- No runtime dependencies.
- No analytics or tracking.
- Prefer one-file site: inline CSS and vanilla JS in `index.html`.
- Do not add npm, Vite, React, Next.js, Astro, Tailwind, Docker, or Kubernetes tooling unless explicitly requested.

## Current Committed State

Recent commits at the end of this session:

```text
e5054f7 Add GitHub development workflow
b5d9d5c Add project README
44dbfd4 Add agent project guidance
f039474 Geek up index.html
```

Current important files:

- `index.html`: complete one-file website with styles, terminal, Easter eggs, and DevTools API.
- `CNAME`: contains `cowmeuh.net`.
- `AGENTS.md`: durable project instructions for AI agents.
- `README.md`: public project docs, local dev, deployment, workflow, CI notes.
- `.github/workflows/ci.yml`: CI for static policy checks, HTML validation, and link checking.
- `.github/pull_request_template.md`: PR checklist.
- `.github/ISSUE_TEMPLATE/`: bug and idea templates.
- `.github/CODEOWNERS`: `@crazydan` owns all files.
- `.github/dependabot.yml`: weekly GitHub Actions update PRs.
- `.gitignore`: local/editor noise and dependency artifacts.
- `.lycheeignore`: ignores local dev URL.

## Website Features Present

- Hero for `Daniel`, `Principal Software Engineer`.
- Contact links: GitHub, LinkedIn, email.
- Status/stats panels.
- Interactive terminal with command history.
- `clear`, `Ctrl+L`, and `Cmd+L` handling.
- ASCII pet and `feed` persisted via `localStorage`.
- Konami code effect.
- DevTools API: `window.daniel` with `help`, `whoami`, `pet`, `source`, `secret`.
- View-source Easter egg near the top of `index.html`.

## Development Workflow Decision

- Use `main` as production.
- Future work should use short-lived branches and pull requests, even though Daniel is the only developer.
- Prefer squash merges.
- Let GitHub Pages deploy from `main` / root.
- Recommended branch names: `feature/...`, `fix/...`, `content/...`, `chore/...`.

## CI Workflow Summary

Workflow: `.github/workflows/ci.yml`

Runs on:

- Pull requests.
- Pushes to `main`.
- Manual dispatch.

Jobs:

- `Static Site Policy`: checks required files, `CNAME`, required metadata/Easter egg snippets, and prevents dependency/build artifacts.
- `HTML Validation`: installs Python, Java Temurin 21, and `html5validator`, then validates `*.html`.
- `Link Check`: uses `lycheeverse/lychee-action@v2`, excludes email and LinkedIn links.

## Validation Notes From This Session

Passed locally:

- YAML parsing for workflow, Dependabot, and issue templates using temporary `PyYAML` installed outside the repo.
- Static-site policy check copied from CI.

Not fully runnable locally at the time:

- `html5validator`, because local `java` is broken through an `asdf` shim.
- `lychee`, because it is not installed locally.

Mitigation already added:

- CI explicitly sets up Java with `actions/setup-java@v4` before running `html5validator`.

## GitHub Settings Still Need Manual Setup

Configure in GitHub UI:

- GitHub Pages: deploy from `main` / root.
- Protect `main`.
- Require PR before merge.
- Require CI status checks to pass.
- Require branch up to date before merge.
- Prefer squash merge.
- Automatically delete merged branches.

For this solo repo, requiring an external reviewer is probably unnecessary.

## AI-First Operating Model

Daniel wants this repo to be an experiment in using AI for as much of the development workflow as practical.

Good default loop:

1. User gives natural-language outcome.
2. AI creates or suggests a short-lived branch.
3. AI makes the smallest correct change.
4. AI runs available local checks.
5. AI opens or prepares a PR summary/checklist when requested.
6. GitHub Actions validates.
7. AI fixes CI failures if asked.
8. Daniel reviews and merges.

Keep Daniel in control of account-level settings, domain/DNS, secrets, merges, and final approval.

## Likely Next Improvements

- Add `CONTRIBUTING.md` focused on AI-assisted solo development.
- Add an `ai-task` issue template for prompt-shaped GitHub issues.
- Push the current `main` commits to GitHub if not already pushed.
- Create the first branch/PR using the new workflow.
- Run GitHub Actions and fix any CI findings from the remote environment.
- Add small terminal commands such as `contact`, `skills`, `source`, or `theme`.
- Add `robots.txt`, `sitemap.xml`, and favicon if discoverability/polish becomes important.

## Cautions For Future Agents

- Check worktree state before editing or committing.
- Do not revert user changes.
- Do not split CSS/JS out of `index.html` unless explicitly asked or maintenance requires it.
- Do not introduce dependencies to make validation easier.
- Keep PRs small and commits focused.
- If asked to commit, inspect `git status`, `git diff`, and recent log first.
