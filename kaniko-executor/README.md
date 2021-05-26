# kaniko-executor

## Inputs

1. `aws-access-key-id` (required) : AWS_ACCESS_KEY_ID
2. `aws-secret-access-key` (required) : AWS_SECRET_ACCESS_KEY
2. `aws-session-token` (optional) : AWS_SESSION_TOKEN, Defaults to ""
3. `images` (required) : Build image names ('name:tag,name:tag' format)
4. `cache-repo` (required) : Pushing to docker repository for layer cache
5. `target` (optional) : Docker build target directory, Defaults to $PWD
6. `dockerfile` (optional) : Dockerfile name, Defaults to Dockerfile

## Outputs

Return none.

## Example

```yaml
steps:
  - uses: actions/checkout@v2
    with:
      ref: ${{ github.base_ref }}

  - uses: plusvion/actions/kaniko-executor@v1
    with:
      aws-access-key-id: ${{ secrets.AWS_ACCESS_KEY_ID }}
      aws-secret-access-key: ${{ secrets.AWS_SECRET_ACCESS_KEY }}
      images: image:tag
      cache-repo: docker-repository-for-cache
```
