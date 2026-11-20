# renovate-config

Shared [Renovate](https://docs.renovatebot.com/) preset for the Paper Balloon
repos. A repo opts in with `.github/renovate.json`:

```json
{ "extends": ["github>tim4724/renovate-config"] }
```

Each rule's `description` in `default.json` says why it exists. The schedule
spans all of Monday: Mend's hosted app runs a repo only once a day until one of
its PRs has been merged, so a shorter window can miss every run. Dependabot
alerts stay on in every repo: Renovate reads them for its security PRs, which
skip the schedule and the release-age wait. Dependabot security updates stay
off, or every fix arrives twice.
