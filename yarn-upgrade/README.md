# yarn-upgrade

## Inputs

1. `github-user-name` (optional) : Commit author name, Defaults to github-actions
2. `github-user-email` (optional) : Commit author email, Defaults to github-actions@users.noreply.github.com
3. `options` (optional) : CLI options, Defaults to blank

## Outputs

Return none.

## Example

```yaml
steps:
  - uses: actions/checkout@v2
  - uses: actions/setup-node@v2
    with: { node-version: 14 }

  - uses: plusvision/actions/yarn-upgrade@v1
```
