# git-rebase

## Inputs

1. `github-user-name` (optional) : Commit author name, Defaults to github-actions[bot]
2. `github-user-email` (optional) : Commit author email, Defaults to github-actions[bot]@users.noreply.github.com

## Outputs

Return none.

## Example

```yaml
if: github.event.issue.pull_request && github.event.comment.body == '@github rebase'
steps:
  - uses: actions/checkout@v2
    with: { fetch-depth: 0 }

  - uses: plusvision/actions/git-rebase@v1
```
