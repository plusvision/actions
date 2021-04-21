# delete-branch

## Inputs

1. `github-token` (required) : GitHub token

## Outputs

Return none.

## Example

```yaml
if: github.event.pull_request.merged && !contains('main,etc', github.head_ref)
steps:
  - uses: plusvision/actions/delete-branch@main
    with:
      github-token: ${{ secrets.GITHUB_TOKEN }}
```
