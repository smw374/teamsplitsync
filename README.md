# TeamSplitSync

Team repository for the Cornell Six Sigma Hackathon. This repository contains preparation and collaboration documentation only. The prompt, user, statistical method, stack, and application will be selected after kickoff.

## Start here

1. Read [SPEC.md](SPEC.md) and [CONTRACT.yaml](CONTRACT.yaml).
2. Read [CONTRIBUTING.md](CONTRIBUTING.md) for task claims, branches, and reviews.
3. Follow the [preparation checklist](docs/PREPARATION.md).
4. Review the [rubric](docs/criteria.md), [schedule](docs/schedule.md), and [starter prompts](docs/prompts-starter.md).

At kickoff, complete H-01 together before writing application code. Choose one instructor demo and copy it into `app/` only after agreeing on the SPEC. There is no application run or test command yet.

## Planned layout

- `app/`: one selected starter, including the plain QC function and local-run/deployment scripts.
- `tests/`: known-answer and degenerate-case statistical tests.
- `data/`: 2–3 clearly labeled synthetic datasets and a codebook.
- `demo/README.md`: reproducible walkthrough of every dataset.
- `docs/plan.md`: agreed implementation plan, created after prompt selection.
- `.github/workflows/` and `.github/scripts/`: stack-specific CI and deployment, added later.

These application paths are planned, not implemented. The course Posit Connect server is the deployment target; no deployment workflow or credentials are configured.

## Sources

Instructor materials come from [timothyfraser/sixsigmahackathon](https://github.com/timothyfraser/sixsigmahackathon). See [provenance and setup notes](docs/PREPARATION.md#instructor-materials) and the retained [MIT license](LICENSE). The repository name does not determine our eventual product or prompt.
