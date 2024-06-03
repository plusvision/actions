# github-reviewers

Pull RequestのReviewersが割り当てられたら、Slackにメッセージ送信します。

## Inputs

1. `slack-webhook-url` (required) : Slack Webhook URL
2. `message` (optional) : Slack message, Defaults to "レビューお願いします :pray:"
3. `message-color` (optional) : Slack message attachments color, Defaults to "#000000"

## Outputs

Return none.

## Example

```yaml
name: github-reviewers
on:
  pull_request: { types: [review_requested] }

concurrency:
  group: ${{ github.workflow }}-${{ github.event.pull_request.number }}
  cancel-in-progress: true

jobs:
  github-reviewers:
    runs-on: ubuntu-latest

    steps:
      - uses: plusvision/actions/github-reviewers@v3
        with:
          slack-webhook-url: ${{ secrets.SLACK_WEBHOOK_URL }}
```
