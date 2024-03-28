# git-rebase

Pull Requestのコメントで任意のキーワードを入力すると、Pull Requestのベースブランチでrebase force pushします。

## Inputs

1. `github-user-name` (optional) : Commit author name, Defaults to github-actions[bot]
2. `github-user-email` (optional) : Commit author email, Defaults to github-actions[bot]@users.noreply.github.com

## Outputs

Return none.

## Example

```yaml
name: git-rebase
on:
  issue_comment:
    types: [created]

jobs:
  git-rebase:
    runs-on: ubuntu-latest
    if: github.event.issue.pull_request && github.event.comment.body == '@github rebase'

    steps:
      - uses: plusvision/actions/github-issue-comment-reaction@v2

      - uses: actions/checkout@v4
        with: { fetch-depth: 0 }

      - uses: plusvision/actions/git-rebase@v2
```
