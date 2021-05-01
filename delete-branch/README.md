# delete-branch

## Inputs

No inputs.

## Outputs

Return none.

## Example

```yaml
if: github.event.pull_request.merged && !contains('main,etc', github.head_ref)
steps:
  - uses: plusvision/actions/delete-branch@main
```
