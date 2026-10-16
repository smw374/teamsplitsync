# Before kickoff

## Team checklist

- [ ] Every teammate registers on Devpost and confirms the track and schedule.
- [ ] Invite GitHub collaborators; everyone clones the team repository and verifies authentication.
- [ ] Confirm public repository visibility for the final submission.
- [ ] Install Git, an editor, and R or Python according to team familiarity; configure AI assistants if used.
- [ ] Select an integrator and provisional statistics, data/demo, and app/deployment responsibilities.
- [ ] Read the rubric together and agree on task claims, file ownership, branches, and review.
- [ ] Configure main PR review protection when appropriate; add required checks only after those checks exist.

No collaborator invitations, GitHub settings, registrations, or software installations were performed by this file setup.

## At kickoff

1. Read the released prompts and choose one as a team. Do not infer the product from the repository name.
2. Complete SPEC H-01 together: user, decision, inputs, method, assumptions, known-answer check, outputs, stack, and scope.
3. Record the plan in docs/plan.md under an agreed ledger task and resolve ownership overlaps.
4. Select ONE primary demo from the instructor repository and copy it to app/. Add a React frontend only if justified by the use case.
5. Build and verify the core statistical function before integrating UI. Create 2–3 synthetic datasets and their codebook.
6. Deploy early to course Posit Connect, then verify the public URL and fresh-clone reproducibility.

## Deployment files to copy later

From `.claude/skills/connect-publish/`, copy the selected workflow to `.github/workflows/` and the scripts it references to `.github/scripts/`:

| Stack | Workflow | Helpers |
|---|---|---|
| FastAPI | deploy-fastapi.yml | connect-publish-async.sh |
| plumber | deploy-plumber.yml | connect-publish-async.sh |
| R Shiny | deploy-shiny-r.yml | connect-publish-async.sh |
| Python Shiny | deploy-shiny-py.yml | connect-publish-async.sh |
| React static frontend | deploy-react-static.yml | both connect-publish helpers |

Set APP_DIR to the actual app path (`app` for the primary starter). API plus frontend deployment may require separate content items and workflows. Add CONNECT_SERVER and CONNECT_API_KEY as repository secrets when provided. Generate required manifests locally; preserve dependency lockfiles. No workflows are active yet. Library/package delivery may need a separate agreed deployable demonstration; no dedicated package workflow is listed by the instructor.

## Instructor materials

Copied from the adjacent instructor checkout at revision `f9a35af` (2026-10-11), repository https://github.com/timothyfraser/sixsigmahackathon:

- Root SPEC.md and CONTRACT.yaml: the event-specific, rubric-aligned versions, rather than the generic blank templates.
- Root AGENTS.md and CLAUDE.md: adapted with team repository rules and upstream references.
- docs/ and .claude/skills/: instructor reference material; existing example commands do not indicate an app has been built or deployed.
- .gitattributes and LICENSE: retained line-ending rules and MIT attribution.

No demos, blank-template directory, or OpenCode command directory were copied. References to those directories in instructor material refer to [upstream files](https://github.com/timothyfraser/sixsigmahackathon). Read-only references may retain upstream-relative links; use the instructor repository to browse those files. The local docs directory remains tracked.

Update instructor materials selectively, record the new source revision, and keep team-specific instructions and SPEC decisions. Do not merge unrelated instructor history into the team repository.
