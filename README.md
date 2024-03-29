# Workflows

This repository contains reusable workflow files for Github Actions.

## check_py.yaml

Run [`black`](https://black.readthedocs.io/en/stable/) on python files, using [rickstaa/action-black](https://github.com/rickstaa/action-black).

Include the following jobs in your existing workflows to use workflows:
```yaml
[...]
jobs:
  check_tf:
    uses: scaleway-terraform-modules/wokflows/.github/workflows/check_py.yaml@main

```

## check_shell.yaml

Run [shellcheck](https://www.shellcheck.net/) on shell scripts using [ludeeus/action-shellcheck](https://github.com/ludeeus/action-shellcheck).

Include the following jobs in your existing workflows:
```yaml
[...]
jobs:
  check_sh:
    uses: scaleway-terraform-modules/wokflows/.github/workflows/check_shell.yaml@main

```

## check_tf.yaml

Run several checks on terraform code:
* Formatting check using `terraform fmt`.
* Configuration validation using `terraform validate`.
* Documentation is up to date using [`terraform-docs`](https://terraform-docs.io/).
* Linting using [`tflint`](https://github.com/terraform-linters/tflint).

Include the following jobs in your existing workflows to use workflows:
```yaml
[...]
jobs:
  check_tf:
    uses: scaleway-terraform-modules/wokflows/.github/workflows/check_tf.yaml@main
    secrets: inherit

```

## check_yaml.yaml

Run [`yamllint`](https://www.yamllint.com/).

Include the following jobs in your existing workflows to use workflows:
```yaml
[...]
jobs:
  check_tf:
    uses: scaleway-terraform-modules/wokflows/.github/workflows/check_yaml.yaml@main

```

