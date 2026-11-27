# renovate-config

Shared [Renovate](https://docs.renovatebot.com/) preset for the Paper Balloon
repos. A repo opts in with `.github/renovate.json`:

```json
{ "extends": ["github>tim4724/renovate-config"] }
```

Each rule's `description` in `default.json` says why it exists. PRs open on
Mondays. Mend's hosted app checks a repo every few hours only once one of its
Renovate PRs has been merged; until then it can skip a whole Monday. A new repo
therefore needs a manual start: tick "Create all awaiting schedule PRs at once"
on its Dependency Dashboard and merge one of the PRs. Dependabot
alerts stay on in every repo: Renovate reads them for its security PRs, which
skip the schedule and the release-age wait. Dependabot security updates stay
off, or every fix arrives twice.
