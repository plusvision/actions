# release-please

## Inputs

1. `merge-from-branch` (optional) : Merge from branch, Defaults to develop
2. `merge-to-branch` (optional) : Merge to branch, Defaults to main
3. `pr-template` (optional) : Pull request title and body template, Defaults to the content below is used
    ```
    Release by @${{ github.actor }}

    ## Pull requests

    <% pull_requests.each do |pr| -%>
    <%=  pr.to_checklist_item %>
    <% end -%>
    ```
4. `pr-labels` (optional) : Labels list for pull request (comma-separated string), Defaults to ":octocat: release-please"

## Outputs

Return none.

## Example

```yaml
steps:
  - uses: actions/checkout@v2
    with: { fetch-depth: 0 }

  - uses: plusvision/actions/release-please@v1
```
