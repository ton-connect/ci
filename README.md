# ci

Shared GitHub Actions workflows for TON Connect services.

| Workflow | Purpose |
|---|---|
| [`build-image.yml`](.github/workflows/build-image.yml) | Build the service container image and publish it to ECR via OIDC, tagged with the full + short commit sha (immutable tags, idempotent re-runs) |
| [`verify-release-pointer.yml`](.github/workflows/verify-release-pointer.yml) | Validate `version.yaml` release-pointer PRs: schema, commit provenance, published-image existence — all fail-closed |

Both are [reusable workflows](https://docs.github.com/en/actions/using-workflows/reusing-workflows): call them with `uses: ton-connect/ci/.github/workflows/<name>.yml@main`. Caller templates are in each workflow's header comment.
