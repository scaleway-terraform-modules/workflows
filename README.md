# Workflows

This repository contains reusable workflow files for Github Actions.

## Usage

Call workflows pinned to the full commit SHA of a [release](https://github.com/scaleway-terraform-modules/workflows/releases), followed by the release version as a comment. This prevents changes on `main` from silently reaching every repository, and lets Dependabot propose updates when a new release is published:

```yaml
uses: scaleway-terraform-modules/workflows/.github/workflows/<workflow>.yaml@<commit-sha>  # vX.Y.Z
```

## py_check.yaml

Run [`black`](https://black.readthedocs.io/en/stable/) on python files, using [rickstaa/action-black](https://github.com/rickstaa/action-black).

Include the following jobs in your existing workflows to use this workflow:
```yaml
[...]
jobs:
  check_py:
    uses: scaleway-terraform-modules/workflows/.github/workflows/py_check.yaml@<commit-sha>  # vX.Y.Z

```

## shell_check.yaml

Run [shellcheck](https://www.shellcheck.net/) on shell scripts using [ludeeus/action-shellcheck](https://github.com/ludeeus/action-shellcheck).

Include the following jobs in your existing workflows to use this workflow:
```yaml
[...]
jobs:
  check_sh:
    uses: scaleway-terraform-modules/workflows/.github/workflows/shell_check.yaml@<commit-sha>  # vX.Y.Z

```

## tf_module_check.yaml

Run several checks on terraform code, useful for modules:
* Formatting check using `terraform fmt`.
* Configuration validation using `terraform validate`.
* Documentation is up to date using [`terraform-docs`](https://terraform-docs.io/).
* Linting using [`tflint`](https://github.com/terraform-linters/tflint).

Include the following jobs in your existing workflows to use this workflow:
```yaml
[...]
jobs:
  check_tf:
    uses: scaleway-terraform-modules/workflows/.github/workflows/tf_module_check.yaml@<commit-sha>  # vX.Y.Z
    secrets: inherit

```

## tf_project_apply.yaml

Apply any changes on the infrastructure using terraform.

The job is configured to avoid deadlocks on the remote state. As such only one job will run at a time, and running jobs won't be cancelled.

Include the following jobs in your existing workflows to use this workflow:
```yaml
[...]
jobs:
  merge_tf:
    uses: scaleway-terraform-modules/workflows/.github/workflows/tf_project_apply.yaml@<commit-sha>  # vX.Y.Z
    secrets: inherit

```

## tf_project_plan.yaml

Run some checks on terraform code and generate a plan, useful when creating pull request on a project:
* Formatting check using `terraform fmt`.
* Configuration validation using `terraform validate`.
* Generate a plan using `terraform plan`.
* Linting using [`tflint`](https://github.com/terraform-linters/tflint).

The job is configured to avoid deadlocks on the remote state. As such only one job will run at a time, and running jobs are not cancelled.

Include the following jobs in your existing workflows to use this workflow:
```yaml
[...]
jobs:
  plan_tf:
    uses: scaleway-terraform-modules/workflows/.github/workflows/tf_project_plan.yaml@<commit-sha>  # vX.Y.Z
    secrets: inherit

```

## yaml_check.yaml

Run [`yamllint`](https://www.yamllint.com/).

Include the following jobs in your existing workflows to use this workflow:
```yaml
[...]
jobs:
  check_yaml:
    uses: scaleway-terraform-modules/workflows/.github/workflows/yaml_check.yaml@<commit-sha>  # vX.Y.Z

```
