# release-version

## Inputs

1. `github-user-name` (optional) : Commit author name, Defaults to github-actions
2. `github-user-email` (optional) : Commit author email, Defaults to github-actions@github.com
2. `commit-message` (optional) : Commit message, Defaults to `🎉 Release ${NEW_VERSION}`

## Outputs

Return none.

## Example

```yaml
if: github.event.issue.pull_request && startsWith(github.event.comment.body, '@github version ')
steps:
  - uses: actions/checkout@v2
    with: { ref: "barnch" }

  - uses: plusvision/actions/release-version@v1
```
