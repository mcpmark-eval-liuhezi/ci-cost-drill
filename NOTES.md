# Soak Drill Notes

- Repository: ci-cost-drill (scratch sandbox)
- Workflow: soak.yml — runs `sleep 600` on pull_request events
- Purpose: rehearse the on-call runbook for killing a live (runaway) Actions run

## Runbook steps rehearsed

1. Confirm the workflow file exists on the default branch.
2. Open a PR from `drill/soak-test` into `main` to trigger the soak run.
3. Verify the run's head SHA and branch match the pull request's head.
4. Capture billable usage metrics while the run is in progress.
5. Cancel the run.
6. Poll until the run reaches a terminal state.
7. File the incident report.
