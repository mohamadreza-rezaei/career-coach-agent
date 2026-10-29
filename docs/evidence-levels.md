# Evidence levels

| Level | Use when | Examples |
|---|---|---|
| `proven` | You saw it working: code in a repo with real usage, a production service, a passed drill or quiz (≥7/10) | Tests and CI in a repo the user authored; a service the user deployed that others use |
| `partial` | Proof exists but is thin, old (>3 years), toy-sized, or generated from a template | Coursework repos; a `k8s/` folder copied from a starter template |
| `claimed` | Only stated: resume, portfolio copy, LinkedIn, chat | "Reduced cost by 70%" with no dashboard or before/after |
| `self-rated` | The user gave themselves a score | "Python: 3/10" |
| `contradicted` | Two surfaces disagree, or the evidence disagrees with the claim | The title says "Full-stack" on one surface and "Backend" on another; a framework version in copy differs from the one in code |

## Rules

- Tag every row in the skill model with level + source (`GH:repo`, `CV`, `LI`, `SITE`, `CHAT`, `NOTES`, `QUIZ:date`).
- Numbers that were written with AI help or have no source are `claimed` and marked **unverified**. Never copy them to a new surface.
- Template-generated files (identical across repos, untouched since scaffold) don't count as skill evidence.
- Private work counts as `proven` only if you could read it. Otherwise it's `claimed` (strong), with "needs public proof" noted under gaps.
- Upgrades need new evidence. Downgrades need contradicting evidence or a failed quiz, and you explain why in one line.
