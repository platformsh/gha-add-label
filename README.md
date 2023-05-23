# Add label to pull request/issue

Will add a label to a pull request or issue. If the label does not exist, it will create it before adding it to the PR/issue.

## Inputs

* `repo-owner` - Owner/namespace of the target repository. Defaults to `github.repository_owner` from
  the [github context](https://docs.github.com/en/actions/learn-github-actions/contexts#github-context).
* `repo-name` - Target repository name. Defaults to `github.event.repository.name` from the from
  the [github context](https://docs.github.com/en/actions/learn-github-actions/contexts#github-context).
* `github-token` -
  Github [personal access token](https://docs.github.com/en/authentication/keeping-your-account-and-data-secure/creating-a-personal-access-token)
  with access rights to the target repository so we can work with the github api. **REQUIRED**.
* `issue-type` - Do you want to add the label to an `issue` or a `pull request`? **REQUIRED**.
* `identifier` - The number or URL of the pull request/issue you want to apply the label to. **REQUIRED**.
* `label` - The label you want to add to the issue/pull-request. Will be created if it doesn't exist. **REQUIRED**. Currently,
only supports a single label. 
* `fail-or-report` - If adding a label to the pr/issue fails, should the workflow `fail` or should I `report` the failure? Defaults to `fail`.
## Outputs

* `success` - `true`|`false`

## Example usage:

See `Add label on pull request` step below.

```yaml
name: Some workflow

on:
  pull_request_target:
    branches: [main]
    types: [opened,reopened]
jobs:
  add-label:
    runs-on: ubuntu-latest
    steps:
      - name: 'Add label on pull request'
        uses: platformsh/gha-add-label@main
        with:
          issue-type: pr
          identifier: ${{ github.event.number }}
          github-token: ${{ secrets.A_GITHUB_TOKEN }}
          label: 'my-custom-label'
```
## Roadmap: 
- Support adding more than one label at once.