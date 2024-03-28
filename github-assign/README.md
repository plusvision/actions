# github-assign

Pull Requestの作成者をAssigneesに割り当てます。

## Inputs

No inputs.

## Outputs

Return none.

## Example

```yaml
name: github-assign
on:
  pull_request: { types: [opened] }

jobs:
  github-assign:
    runs-on: ubuntu-latest

    steps:
      - uses: plusvision/actions/github-assign@v2
```
