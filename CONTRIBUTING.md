# Team workflow

Read SPEC.md and CONTRACT.yaml before every task. CONTRACT.yaml is the task authority; issues and chat may reference task IDs but do not replace the ledger.

## Claim a task

- Coordinate with the integrator and read the latest `main` ledger before claiming.
- Each person or agent has at most one task in progress. Never claim someone else's active task.
- Merge a small claim PR first: edit only your task block with `status: in_progress`, an owner, and a timestamp. Start the implementation branch from the updated main.
- Add a task and get teammate agreement before work outside the existing task scope. Ledger status changes are the administrative exception to task file ownership.
- Update SPEC before implementing an agreed behavior change. Do not fill prompt-dependent fields before kickoff.

## Branches and review

- Keep `main` reviewed and runnable once application work begins. Use short branches such as `h-03/qc-function`; avoid a long-lived develop branch.
- Work only inside the claimed task's paths. Each teammate should use a separate clone; agents sharing a machine need separate worktrees before concurrent edits.
- Keep changes small. Stage explicit files, never `git add .` or `git add -A`.
- Run the task's definition of done and include actual output in the PR. Review statistical code against known answers and degenerate cases before UI integration.
- Have a teammate read the diff. Record `status: done` and a concise evidence-based result in the same change as the implementation. Squash the PR so the resulting commit contains both.
- Preserve other task blocks when resolving CONTRACT conflicts; re-read the latest main before merging. Ask the integrator if ownership is unclear.
- Obtain explicit authorization before committing, pushing, deploying, or changing GitHub settings when working through an agent. Setup authorization alone does not authorize those actions.

## Avoid overlapping ownership

The instructor ledger contains broad parent paths. Treat these as explicit exclusions from H-04's `app/` ownership:

- H-03 owns `app/qc.py` or `app/qc.R`, plus `tests/`.
- H-05 owns `app/frontend/` and `demo/`.
- H-06 owns `app/manifest.json`, `app/.python-version`, and GitHub deployment files.
- H-07 owns `app/README.md` and the root README.

Do not edit these paths concurrently under H-04. If copying a starter touches them, coordinate a sequential handoff before their owners begin. Agree and record additional path changes in the ledger before work; a separate branch does not grant ownership. Remove unused Python/R paths after stack selection. Planning and CI work need their own agreed tasks if existing ownership does not cover them.

## Team responsibilities

Select an integrator for claims and merges, a statistics owner/reviewer, a data/demo owner, and an app/deployment owner. Combine roles for smaller teams, but have another teammate verify the numbers and reproduce the instructions.

## GitHub settings to configure manually

Invite collaborators, confirm the repository is public for submission, and protect main with PR review and relevant passing checks once available. These settings have not been changed by repository setup. Keep the team repository as origin; an instructor upstream remote is optional. Selectively import instructor updates rather than merging the instructor repository wholesale.

## Reproducibility and secrets

Keep statistics out of UI code. Label invented datasets as synthetic and document columns, units, and real-world collection requirements. Never commit credentials. Use GitHub Actions secrets for CONNECT_SERVER and CONNECT_API_KEY when supplied at the event. Preserve the selected starter's testme, manifestme, deployme, and README interface; verify the actual starter provides it and adapt missing pieces under an agreed task.
