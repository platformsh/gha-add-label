# Add label to pull request/issue



## Inputs

* `repo-owner` - Owner/namespace of the target repository. Defaults to `github.repository_owner` from
  the [github context](https://docs.github.com/en/actions/learn-github-actions/contexts#github-context).
* `repo-name` - Target repository name. Defaults to `github.event.repository.name` from the from
  the [github context](https://docs.github.com/en/actions/learn-github-actions/contexts#github-context).
* `github-token` -
  Github [personal access token](https://docs.github.com/en/authentication/keeping-your-account-and-data-secure/creating-a-personal-access-token)
  with access rights to the target repository so we can work with the github api. **REQUIRED**.
* `issue-type` - Do you want to add the label to an `issue` or a `pull request`? **REQUIRED**.
* `number` - The number of the pull request/issue you want to apply the label to. **REQUIRED**.
* `label` - The label you want to add to the issue/pull-request. Will be created if it doesn't exist. **REQUIRED**.
## Outputs

* `success` - `true`|`false`

## Example usage:

See `yyy` step below.

```yaml
To come
```
