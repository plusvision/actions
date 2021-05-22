# github-reviewers

## Inputs

1. `slack-webhook-url` (required) : Slack Webhook URL
2. `message-color` (optional) : Slack message attachments color, Defaults to "#000000"

## Outputs

Return none.

## Example

```yaml
steps:
  - uses: plusvision/actions/github-reviewers@v1
    with:
      slack-webhook-url: ${{ secrets.SLACK_WEBHOOK_URL }}
```
