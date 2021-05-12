# pr-copy

## Inputs

1. `github-token` (required) : GitHub Personal Access Token
2. `pr-bullet-version` (optional) : pr-bullet version, Defaults to 0.2.1

## Outputs

Return none.

## Example

```yaml
if: github.event.issue.pull_request && startsWith(github.event.comment.body, '@github copy ')
steps:
  - uses: plusvision/actions/pr-copy@main
    with:
      github-token: ${{ secrets.PERSONAL_ACCESS_TOKEN }}
```
