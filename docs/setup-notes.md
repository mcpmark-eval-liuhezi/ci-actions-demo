# Setup notes

A record of the steps taken to stand this project up, so the setup can be reproduced or reverse-engineered by anyone on the team.

## Steps taken

1. Searched GitHub for the CI starter workflows published by the `actions` org in their `starter-workflows` repository, and inspected `ci/node.js.yml` in that repo to see the actual structure of a starter CI workflow.
2. Created this public repository (`ci-actions-demo`) with an initial README, giving it a `main` default branch to build on.
3. Created a branch and opened the first pull request (**Add project scaffolding**), which contains this README and `docs/setup-notes.md`.
4. Opened a second pull request (**Add CI workflow**) that adds the workflow file at `.github/workflows/ci.yml`, modeled on the starter described in step 1.
5. Merged both pull requests into `main` in order.
6. Manually triggered the workflow on `main` via `workflow_dispatch` and recorded the reported run status.

## Why the workflow looks the way it does

The pipeline follows the conventions from the starter:

- a single `build` job that runs on `ubuntu-latest`;
- `actions/checkout@v4` to get the code onto the runner;
- `actions/setup-node@v4` to provision a Node.js toolchain;
- triggered by pushes to the default branch (`main`), with `workflow_dispatch` added so it can also be started manually from the Actions tab, which the starter doesn't include.

The only deviation from the starter is that the workflow body is deliberately trivial — it just prints the Node version — because the goal of this repo is to demo the pipeline itself, not to build or test anything.
