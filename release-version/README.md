# release-version

Pull Requestのラベルに基づいて`.version`ファイルを更新します。

## Inputs

1. `github-user-name` (optional) : Commit author name, Defaults to github-actions[bot]
2. `github-user-email` (optional) : Commit author email, Defaults to github-actions[bot]@users.noreply.github.com
3. `commit-message` (optional) : Commit message, Defaults to `🎉 Release ${NEW_VERSION}`
4. `version-file` (optional) : Versioning file, Defaults to `.version`

## Outputs

Return none.

## Example

```yaml
name: release-version
on:
  pull_request:
    types: [labeled]

jobs:
  release-version:
    runs-on: ubuntu-latest
    if: ${{ contains(github.event.label.name, 'major') || contains(github.event.label.name, 'minor') || contains(github.event.label.name, 'patch') }}

    steps:
      - uses: actions/checkout@v4
        with:
          ref: ${{ github.head_ref }}

      - uses: plusvision/actions/release-version@v2
        with:
          commit-message: ":tada: Release ${NEW_VERSION} [ci skip]"
```
