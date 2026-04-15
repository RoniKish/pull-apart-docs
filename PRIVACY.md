# Privacy Policy

## About Pull Apart
Pull Apart is a GitHub App that splits a pull request into separate pull requests — one for refactoring/cleanup changes and one for behavioral/feature changes.

## What data Pull Apart accesses
When installed on a repository and triggered by a `/split-pr` comment, Pull Apart accesses the following data from GitHub via the GitHub API:

- **Pull request metadata:** title, description, base branch, head branch, and commit SHAs
- **Pull request file list:** the names, statuses, and unified diffs of changed files
- **Repository file contents:** the content of changed files at specific git revisions (base and head), used to construct the split branches
- **Issue comments:** to detect `/split-pr` and `@pull-apart /close` trigger commands

Pull Apart acts on your behalf (using an installation token) to:
- Create new branches and commits in the repository
- Open two new pull requests
- Post a comment with links to the new pull requests
- Close pull requests and delete branches when instructed via `@pull-apart /close`


## What data is sent to third parties
Pull request diffs, file contents, and PR titles/descriptions are sent to the **AI model provider API** to classify changed files and produce split file versions. This data is processed by the model company in accordance with API Terms of Service and Privacy Policy. No data is sent to any other third parties.

## Data retention
Pull Apart does not store, log, or retain any repository content, pull request data, or file contents. All data is processed in memory during the handling of a single webhook event and is not persisted anywhere.

## What Pull Apart does not do
- Pull Apart does not collect personal information about GitHub users beyond what is necessary to process the webhook event
- Pull Apart does not sell or share data with advertisers or data brokers
- Pull Apart does not track users across repositories or sessions

## Required GitHub permissions
Pull Apart requests only the permissions it needs to function:

| Permission | Access | Reason |
|---|---|---|
| Metadata | Read | Required by GitHub for all apps |
| Issues | Read & write | Read trigger comments; post result comment |
| Pull requests | Read & write | Read PR data; open split PRs |
| Contents | Read & write | Read file content at git refs; create branches and commits |

## Contact

If you have questions about this privacy policy or how Pull Apart handles data, please open an issue in the [repository](https://github.com/rkishner/split-pr-backend) or contact the developer directly via GitHub.
