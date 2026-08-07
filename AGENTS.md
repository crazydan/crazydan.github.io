# AGENTS.md

## Project

Personal one-page website for Daniel, hosted free on GitHub Pages.

GitHub account:

```text
https://github.com/crazydan
```

Expected GitHub Pages repository:

```text
crazydan.github.io
```

Expected default site URL:

```text
https://crazydan.github.io
```

A custom root domain may later point to this GitHub Pages site.

## Goal

Build a polished, geeky, terminal-inspired personal homepage that works as a professional contact page first and an interactive nerd playground second.

The page should feel like:

> someone discovered a tiny computer running at Daniel's domain

A recruiter should understand the page in ~10 seconds.

A software engineer should be able to spend several minutes discovering interactive details and Easter eggs.

## Core principles

Keep the site:

- free to host
- static
- extremely lightweight
- fast
- responsive
- accessible
- maintainable
- intentionally over-engineered only in fun UX details

Prefer:

```text
1 HTML file
0 frameworks
0 build steps
0 dependencies
0 analytics
0 trackers
$0/month hosting
```

Do not introduce React, Next.js, Astro, npm, webpack, Vite, Tailwind, Docker, Kubernetes, or other tooling unless explicitly requested.

The simplicity is part of the personality of the site.

## Hosting

Use GitHub Pages.

Repository:

```text
crazydan.github.io
```

Primary file:

```text
index.html
```

GitHub Pages deployment should use:

```text
Settings
→ Pages
→ Deploy from a branch
→ main
→ / (root)
```

For a custom apex/root domain, GitHub Pages currently uses:

```text
A @ 185.199.108.153
A @ 185.199.109.153
A @ 185.199.110.153
A @ 185.199.111.153
```

For `www`:

```text
CNAME www crazydan.github.io
```

Do not modify Google Workspace MX records when configuring the website.

Email DNS and website DNS are independent.

## Visual direction

Dark terminal / hacker aesthetic, but tasteful rather than cosplay.

Use:

- near-black background
- subtle green radial glow
- monospace typography
- restrained neon-green accent
- thin borders
- terminal-style panels
- large typography for `Daniel`
- subtle blinking cursor
- simple responsive layout
- light CRT/scanline texture only if unobtrusive

The page should look polished enough to function as a real professional homepage.

Avoid:

- Matrix clichés
- excessive animation
- huge blocks of ASCII art
- aggressive glitch effects
- autoplay sound
- unreadable green-on-black everywhere
- fake terminal UI that prevents basic navigation

## Hero content

Primary identity:

```text
Daniel
Principal Software Engineer
```

Suggested tagline:

```text
// builder of things
```

Suggested bio:

```text
I build games, distributed systems, and things that probably didn't need automating.
```

Location:

```text
Sydney, Australia
```

Contact buttons:

```text
GitHub
LinkedIn
Email
```

GitHub link is known:

```text
https://github.com/crazydan
```

LinkedIn and email should remain easy-to-replace placeholders if not yet supplied.

## Personality

Daniel's technical interests include:

- games
- distributed systems
- architecture
- developer tooling
- automation
- AI-assisted engineering
- recommendation systems
- product engineering
- Japanese
- side projects

The site may reflect these themes.

Do not expose confidential or internal employer information.

Keep references to professional experience generic.

## Status panel

Include a small playful system-status panel such as:

```text
SYSTEM STATUS

Website       operational
Coffee        nominal
Ideas         too many
Sleep         optional
Production    someone else's problem
```

Include site stats:

```text
HTML          1 file
Frameworks    0
Dependencies  0
Build step    none
Monthly cost  $0.00
Uptime        24/7*
```

Suggested footnote:

```text
* unless GitHub is down
```

## Interactive terminal

The terminal should actually work.

Users should be able to click/focus it and type commands.

Support terminal history with:

```text
ArrowUp
ArrowDown
```

Support clearing with:

```text
clear
Ctrl+L
Cmd+L if practical without breaking browser behavior
```

Core commands:

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

Suggested `help` output:

```text
Available commands:

whoami       about me
work         what I do
projects     selected side quests
interests    current rabbit holes
uptime       important operational metrics
status       system health
pet          summon the resident daemon
feed         feed the resident daemon
git log      career history, obviously
ps aux       processes currently consuming CPU
sudo         exercise your authority
clear        clear terminal
```

## Easter egg commands

Implement playful responses for at least:

```text
sudo
vim
emacs
npm
npm install
kubectl
kubectl get pods
docker
rm
rm -rf /
ls
pwd
date
echo ...
hello
hi
exit
42
coffee
help --verbose
```

Tone should be dry, engineering-flavored, and understated.

Examples:

```text
$ npm install

npm ERR! enoent

package.json not found.

There are no dependencies.

This is intentional.
```

```text
$ kubectl get pods

No resources found.

Also:

this is a static HTML file.

Please stop trying to deploy Kubernetes.
```

```text
$ rm -rf /

Permission denied.

Thankfully.
```

```text
$ vim

You have entered vim.

To exit:

1. press Esc
2. type :q!
3. question your life choices
```

## Pet

The terminal should include a tiny ASCII pet.

Example:

```text
 /\_/\
( o.o )
 > ^ <
```

Command:

```text
pet
```

shows the pet.

Command:

```text
feed
```

feeds it.

Persist feeding count using:

```text
localStorage
```

Example response:

```text
cronchy.

feeding count persisted to localStorage:
3

Yes, this website has state now.
We have gone too far.
```

This feature is intentionally unnecessary.

That is part of the joke.

## `git log`

Use a fake compact career-history command:

```text
$ git log --oneline career

a18cf72  principal-software-engineer
91deac4  built-a-lot-of-game-tech
2f813bb  distributed-systems-happened
771bd02  automated-the-boring-parts
09c221a  discovered-computers
```

Keep it generic enough to avoid exposing employer-internal details.

## `ps aux`

Use as a playful list of current interests:

```text
$ ps aux

PID   CPU   PROCESS

101   41%   building-things
203   27%   experimenting-with-ai
317   18%   automating-everything
411    9%   learning-japanese
999    5%   finishing-side-projects
```

## Konami code

Support:

```text
↑ ↑ ↓ ↓ ← → ← → B A
```

When triggered:

- briefly activate a visual effect
- show a small achievement message
- optionally invoke `pet`

Keep the effect brief.

Respect:

```text
prefers-reduced-motion
```

## DevTools Easter egg

On page load, write a tasteful message to the browser console:

```text
Hey.

You opened DevTools on a website
consisting of one HTML file.

Good choice.

Try:

daniel.help()
```

Expose:

```javascript
window.daniel
```

with functions such as:

```javascript
daniel.help()
daniel.whoami()
daniel.pet()
daniel.source()
daniel.secret()
```

## View Source Easter egg

Near the top of the HTML source, include a comment like:

```html
<!--
  You looked at the source.

  Good.

  No React.
  No Next.js.
  No webpack.
  No node_modules.
  No cookie banner.
  No analytics.
  No tracking.

  It's a personal homepage.
  It doesn't need a framework.

  Try the Konami code.
  Or open DevTools and run:

    daniel.help()
-->
```

## Footer

Suggested copy:

```text
© CURRENT_YEAR Daniel
No frameworks. No tracking. Just vibes.
```

Compute the year dynamically if JavaScript is already present.

## Accessibility

Maintain:

- semantic HTML
- keyboard-accessible buttons
- visible focus behavior
- high contrast
- appropriate labels
- responsive layout
- `prefers-reduced-motion`
- no functionality that requires a mouse

The terminal should not trap keyboard focus.

## Performance

The site should load essentially instantly.

Avoid:

- external JavaScript
- third-party fonts unless explicitly requested
- external CSS
- large images
- runtime dependencies
- tracking scripts

Prefer system fonts.

## Metadata

Include:

```html
<title>Daniel — Principal Software Engineer</title>
```

and sensible:

```text
description
viewport
theme-color
Open Graph title
Open Graph description
Open Graph type
```

## Code style

Keep all HTML, CSS, and JavaScript in `index.html` unless the project grows enough to justify splitting files.

Use:

- semantic naming
- CSS custom properties
- clear section comments
- vanilla JavaScript
- no unnecessary abstractions
- no minification while developing
- readable code over clever code

Avoid global state where practical.

Wrap JavaScript in an IIFE or equivalent isolated scope.

## Design test

Before considering changes complete, verify:

1. The page looks professional without using the terminal.
2. GitHub, LinkedIn, and email links work.
3. Mobile layout is clean.
4. Terminal commands work.
5. Arrow-key history works.
6. `clear` works.
7. pet state survives reloads.
8. Konami code works.
9. `daniel.help()` works in DevTools.
10. View Source contains the Easter egg.
11. There are no network requests caused by third-party dependencies.
12. The site works as a plain static file.
13. GitHub Pages can serve it with no build step.

## Guiding philosophy

The page should have progressive discovery.

At first glance:

```text
clean personal homepage
```

Then:

```text
terminal commands work
```

Then:

```text
hidden commands
```

Then:

```text
pet
Konami code
DevTools API
View Source message
```

The geekiness should reward curiosity rather than overwhelm the visitor.

Most importantly:

```text
It should feel handcrafted.
```

Do not turn this into a generic portfolio template.
