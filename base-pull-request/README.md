# base-pull-request

Base BranchのPull Requestが存在するときは、Pull Requestの本文にPR番号を追加します。

## Inputs

1. `description-title` (optional) : PR description title, Defaults to "Base PR"

## Outputs

Return none.

## Example

```yaml
name: base-pull-request
on:
  pull_request:
    types: [opened]

jobs:
  base-pull-request:
    runs-on: ubuntu-latest
    if: ${{ !contains('main,master,develop,deploy', github.base_ref) }}

    steps:
      - uses: plusvision/actions/base-pull-request@v2
        with:
          description-title: "Base Branch"
```
