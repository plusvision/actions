# review-please

Reviewersが割り当てられたら、任意のラベルを追加します。

## Inputs

1. `add-labels` (optional) : Labels list for pull request (comma-separated string), Defaults to "review"

## Outputs

Return none.

## Example

```yaml
name: review
on:
  pull_request:
    types: [review_requested]

jobs:
  review-please:
    runs-on: ubuntu-latest

    steps:
      - uses: plusvision/actions/review-please@v2
        with:
          add-labels: ":pray: review"
```
