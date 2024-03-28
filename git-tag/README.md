# git-tag

`.version`ファイルからgitタグを自動作成します。

## Inputs

1. `github-user-name` (optional) : Commit author name, Defaults to github-actions[bot]
2. `github-user-email` (optional) : Commit author email, Defaults to github-actions[bot]@users.noreply.github.com

## Outputs

Return none.

## Example

```yaml
name: git-tag
on:
  push:
    branches:
      - master

jobs:
  git-tag:
    runs-on: ubuntu-latest

    steps:
      - uses: actions/checkout@v4
        with: { ref: master, fetch-depth: 0 }

      - uses: plusvision/actions/git-tag@v2
```
