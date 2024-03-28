# yarn-upgrade

ci-yarn-upgradeを使ってyarnパッケージをアップグレードします。

## Inputs

1. `github-user-name` (optional) : Commit author name, Defaults to github-actions[bot]
2. `github-user-email` (optional) : Commit author email, Defaults to github-actions[bot]@users.noreply.github.com
3. `options` (optional) : CLI options, Defaults to blank

## Outputs

Return none.

## Example

```yaml
name: yarn-update-pr
on:
  schedule:
    - cron: "0 23 * * sun" # JST 08:00 (Mon)

jobs:
  yarn-update-pr:
    runs-on: ubuntu-latest

    steps:
      - uses: actions/checkout@v4
        with:
          ref: develop

      - uses: actions/setup-node@v4
        with:
          node-version-file: .node-version

      - uses: plusvision/actions/yarn-upgrade@v2
```
