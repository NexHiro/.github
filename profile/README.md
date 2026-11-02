# NexHiro

[![nexhiro.ai](https://img.shields.io/website?url=https%3A%2F%2Fnexhiro.ai&label=nexhiro.ai)](https://nexhiro.ai)
[![app.nexhiro.ai](https://img.shields.io/website?url=https%3A%2F%2Fapp.nexhiro.ai&label=app.nexhiro.ai)](https://app.nexhiro.ai)

NexHiro is an agentic AI recruiter.

Meet Hiro, one AI with five modes that source candidates, send outreach, screen over voice calls, and flag who to interview next. It runs 24/7, so you wake up to shortlists instead of scrolling profiles.

## Hiro modes

- **Hiro:Seek** finds and scores candidates
- **Hiro:Reach** messages and follows up
- **Hiro:Voice** screens over the phone
- **Hiro:Next** tells you who to act on
- **Hiro:Brain** is your recruiter copilot

## Links

- Website: [nexhiro.ai](https://nexhiro.ai)
- App: [app.nexhiro.ai](https://app.nexhiro.ai)

## Shared security workflow

This repo holds the reusable [`security.yml`](https://github.com/NexHiro/.github/blob/main/.github/workflows/security.yml) workflow that our repos call. It's public so that private repos can use it, and it contains no secrets.

```yaml
jobs:
  scan:
    uses: NexHiro/.github/.github/workflows/security.yml@<commit-sha>
```

| Job | Tool | Fails on |
|-----|------|----------|
| Secrets | gitleaks | Secrets in new commits on PRs, or in the full history otherwise |
| Dependencies and config | trivy | Fixable high and critical vulnerabilities, and critical misconfigurations (high ones are only reported) |
| Code | semgrep | Error-level findings from the `p/default` rules |
| Workflows | zizmor | High severity findings in GitHub Actions workflows |

Results go to the job logs.
