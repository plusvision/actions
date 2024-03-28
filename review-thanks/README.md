# review-thanks

Pull Requestがcloseされたら、任意のラベルを削除します。

## Inputs

1. `remove-labels` (optional) : Labels list for pull request (comma-separated string), Defaults to "review"

## Outputs

Return none.

## Example

```yaml
name: review
on:
  pull_request:
    types: [closed]

jobs:
  review-thanks:
    runs-on: ubuntu-latest

    steps:
      - uses: plusvision/actions/review-thanks@v2
        with:
          remove-labels: ":pray: review"
```
