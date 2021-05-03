# git-tag

## Inputs

1. `github-user-name` (optional) : Commit author name, Defaults to github-actions
2. `github-user-email` (optional) : Commit author email, Defaults to github-actions@github.com

## Outputs

Return none.

## Example

```yaml
steps:
  - uses: actions/checkout@v2
    with: { ref: "branch", fetch-depth: 0 }

  - uses: plusvision/actions/git-tag@main
```
