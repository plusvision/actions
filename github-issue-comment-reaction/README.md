# github-issue-comment-reaction

## Inputs

1. `reaction-type` (optional) : Reaction type, Defaults to eyes

## Outputs

Return none.

## Example

```yaml
if: github.event.issue.pull_request && startsWith(github.event.comment.body, 'keyword')
steps:
  - uses: plusvision/actions/github-issue-comment-reaction@v1
```
