# Workflows

This repository contains reusable workflow files for Github Actions.

## py_check.yaml

Run [`black`](https://black.readthedocs.io/en/stable/) on python files, using [rickstaa/action-black](https://github.com/rickstaa/action-black).

Include the following jobs in your existing workflows to use this workflow:
```yaml
[...]
jobs:
  check_py:
    uses: scaleway-terraform-modules/wokflows/.github/workflows/py_check.yaml@main

```

## shell_check.yaml

Run [shellcheck](https://www.shellcheck.net/) on shell scripts using [ludeeus/action-shellcheck](https://github.com/ludeeus/action-shellcheck).

Include the following jobs in your existing workflows to use this workflow:
```yaml
[...]
jobs:
  check_sh:
    uses: scaleway-terraform-modules/wokflows/.github/workflows/shell_check.yaml@main

```

## tf_module_check.yaml

Run several checks on terraform code, usefull for modules:
* Formatting check using `terraform fmt`.
* Configuration validation using `terraform validate`.
* Documentation is up to date using [`terraform-docs`](https://terraform-docs.io/).
* Linting using [`tflint`](https://github.com/terraform-linters/tflint).

Include the following jobs in your existing workflows to use this workflow:
```yaml
[...]
jobs:
  check_tf:
    uses: scaleway-terraform-modules/wokflows/.github/workflows/tf_module_check.yaml@main
    secrets: inherit

```

## tf_project_apply.yaml

Apply any changes on the infrastructure using terraform//

The job is configured to avoid deadlocks on the remote state. As such only one job will run at a time, and running jobs won't be cancelled.

Include the following jobs in your existing workflows to use this workflow:
```yaml
[...]
jobs:
  merge_tf:
    uses: scaleway-terraform-modules/wokflows/.github/workflows/tf_project_apply.yaml@main
    secrets: inherit

```

## tf_project_plan.yaml

Run some checks on terraform code and generate a plan, usefull when creating pull request on a project:
* Formatting check using `terraform fmt`.
* Configuration validation using `terraform validate`.
* Generate a plan using `terraform plan`.
* Linting using [`tflint`](https://github.com/terraform-linters/tflint).

The job is configured to avoid deadlocks on the remote state. As such only one job will run at a time, and running jobs are not cancelled.

Include the following jobs in your existing workflows to use this workflow:
```yaml
[...]
jobs:
  merge_tf:
    uses: scaleway-terraform-modules/wokflows/.github/workflows/tf_project_apply.yaml@main
    secrets: inherit

```

## yaml_check.yaml

Run [`yamllint`](https://www.yamllint.com/).

Include the following jobs in your existing workflows to use this workflow:
```yaml
[...]
jobs:
  check_yaml:
    uses: scaleway-terraform-modules/wokflows/.github/workflows/yaml_check.yaml@main

```
