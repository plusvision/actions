# github-status

任意のgithub statusを作成します。

## Inputs

1. `commit-sha` (required) : Git commit SHA
2. `state` (required) : Status, select of `failure`, `pending` or `success`
3. `label` (optional) : Label of status, Defaults to `workflow / job (event)`
4. `target-url` (optional) : URL of status, Defaults to Actions URL

## Outputs

Return none.

## Example

```yaml
steps:
  - uses: plusvision/actions/github-status@v2
    if: success()
    with:
      commit-sha: ${{ github.sha }}
      state: success
```

```yaml
steps:
  - uses: plusvision/actions/github-status@v2
    if: failure()
    with:
      commit-sha: ${{ github.sha }}
      state: failure
```

```yaml
steps:
  - uses: plusvision/actions/github-status@v2
    with:
      commit-sha: ${{ github.sha }}
      state: pending
```
