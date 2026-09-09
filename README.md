# RepoLens

Paste any public GitHub repo and get an instant health score — README presence, license, recent activity, issue load, and archive status — plus a live stats and language breakdown, styled like a git diffstat.

**[Live demo →](#)** (link added after deploy)

## How it works

Single static page, vanilla JS, zero backend. On submit it calls the public GitHub REST API directly from the browser:

- `GET /repos/{owner}/{repo}` — metadata (stars, forks, issues, license, last push)
- `GET /repos/{owner}/{repo}/languages` — language byte breakdown
- `GET /repos/{owner}/{repo}/readme` — README presence check

Six checks (README, license, description, recent push ≤90d, issue-to-star ratio, not archived) are scored and averaged into a 0–100 health score.

## Run locally

Just open `index.html` in a browser — no build step, no dependencies.

## Notes

Uses the unauthenticated GitHub API, which is rate-limited to 60 requests/hour per IP. Fine for demo use; add a personal access token header for heavier use.
<!-- test -->
<!-- linked -->
