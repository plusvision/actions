# delete-branch

このブランチをターゲットにしたPull Requestがなければブランチを削除します。

## Inputs

No inputs.

## Outputs

Return none.

## Example

```yaml
name: delete-branch
on:
  pull_request:
    types: [closed]

jobs:
  delete-branch:
    runs-on: ubuntu-latest
    if: github.event.pull_request.merged && !contains('main,master,develop,deploy', github.head_ref)

    steps:
      - uses: plusvision/actions/delete-branch@v2
```
