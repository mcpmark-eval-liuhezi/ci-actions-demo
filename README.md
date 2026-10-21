# ci-actions-demo

A small, deliberately simple project that demonstrates how a GitHub Actions pipeline is wired together end-to-end: a pull request gets opened, reviewed, and merged, and the merged change lands on the default branch where a workflow picks it up and runs automatically.

It exists as a live walkthrough for the team — every step of the pipeline is visible in the repo history and the Actions tab, so nothing about the setup is hidden.

## What's in here

- `README.md` — this file.
- `docs/setup-notes.md` — a record of the steps taken to stand the project up.
- `.github/workflows/ci.yml` — the CI workflow: runs on pushes to `main` and can also be triggered manually.

## The pipeline in one paragraph

The workflow is modeled on the Node.js CI starter published by the `actions` org: it checks out the code with `actions/checkout@v4`, sets up Node.js with `actions/setup-node@v4`, and prints the Node version. Trivial on purpose — the point is to see the *plumbing* work, not to build anything.

## References

- [actions/starter-workflows](https://github.com/actions/starter-workflows) — the starter workflow collection the pipeline in this repo is based on. In particular, [`ci/node.js.yml`](https://github.com/actions/starter-workflows/blob/main/ci/node.js.yml) was the template the `.github/workflows/ci.yml` pipeline was modeled on.
