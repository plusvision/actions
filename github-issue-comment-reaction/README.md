# github-issue-comment-reaction

Issueのコメントが任意のキーワードと一致すると、任意のリアクションemojiを追加します。

## Inputs

1. `reaction-type` (optional) : Reaction type, Defaults to eyes

## Outputs

Return none.

## Example

```yaml
name: hello
on:
  issue_comment: { types: [created] }

jobs:
  hello:
    runs-on: ubuntu-latest
    if: github.event.comment.body == '@github hello'

    steps:
      - uses: plusvision/actions/github-issue-comment-reaction@v2
        with:
          reaction-type: heart
```
