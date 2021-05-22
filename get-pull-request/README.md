# get-pull-request

## Inputs

1. `pull-number` (required) : Pull request number

## Outputs

1. `head-ref` : Head branch name in Pull request
2. `base-ref` : Base branch name in Pull request
3. `pull-request` : Pull request by json format

## Example

```yaml
steps:
  - uses: plusvision/actions/get-pull-request@v1
    with:
      pull-number: 1
    id: get-pull-request

  - run: echo ${{ steps.get-pull-request.outputs.head-ref }}
```
