# GH-300 practice room

A study aid for the GitHub Copilot certification (exam GH-300): exam simulations, practice by domain, and scenario questions with dropdowns, yes/no statements and drag-to-order steps.

The whole app is one self-contained file, `public/index.html`. It makes no network requests, sets no cookies and has no analytics. Progress is kept in the visitor’s own browser (`localStorage`).

## How the questions were made

Written from public sources only: the official GH-300 study guide (skills measured as of 7 August 2026), GitHub Docs, the GitHub Copilot Trust Center, the GitHub Blog and Microsoft Learn. Drafted with an AI assistant (Claude, by Anthropic) and checked against the cited docs; every answer links to its source. No questions from the live exam or exam dumps.

Not affiliated with or endorsed by GitHub or Microsoft.

## Run locally

Open `public/index.html` in a browser. That’s it.

## Deploy

Hosted as static assets on Cloudflare Workers (`wrangler.jsonc`). Security headers live in `public/_headers`.

- Automatic: pushes to `main` deploy through Workers Builds.
- Manual: `npx wrangler deploy`

## Editing questions

Questions live in the `BANK` arrays inside `public/index.html`. Each needs a domain (`d`), the question, the answer, an explanation (`e`) and a source key (`s`) that exists in `SRC`.

## Contact

Eugen Gavriluta: eugen.gavriluta@ing.com, [linkedin.com/in/egavriluta](https://www.linkedin.com/in/egavriluta/)
