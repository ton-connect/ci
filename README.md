# ci

Shared GitHub Actions workflows for TON Connect services.

| Workflow | Purpose |
|---|---|
| [`build-image.yml`](.github/workflows/build-image.yml) | Build the service container image and publish it to ECR via OIDC, tagged with the full commit sha (immutable tag, idempotent re-runs) |
| [`check-release-policy.yml`](.github/workflows/check-release-policy.yml) | Run `release-resolver check` on PRs that change `version.yaml`, `service.yaml` or `service.staging.yaml`, annotating each refusal on its file |

They are [reusable workflows](https://docs.github.com/en/actions/using-workflows/reusing-workflows): call them with `uses: ton-connect/ci/.github/workflows/<name>.yml@main`. Caller templates are in each workflow's header comment.
