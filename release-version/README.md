# release-version

## Inputs

1. `github-user-name` (optional) : Commit author name, Defaults to github-actions[bot]
2. `github-user-email` (optional) : Commit author email, Defaults to github-actions[bot]@users.noreply.github.com
3. `commit-message` (optional) : Commit message, Defaults to `🎉 Release ${NEW_VERSION}`
4. `version-file` (optional) : Versioning file, Defaults to `.version`

## Outputs

Return none.

## Example

```yaml
if: ${{ contains(github.event.label.name, 'major') || contains(github.event.label.name, 'minor') || contains(github.event.label.name, 'patch') }}
steps:
  - uses: actions/checkout@v3
    with: { ref: "barnch" }

  - uses: plusvision/actions/release-version@v2
```
