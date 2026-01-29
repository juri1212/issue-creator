Create Issue workflow

This repository contains a GitHub Actions workflow that creates an issue in a specified repository when triggered manually.

Usage

- Set a repository secret named `GH_TOKEN` with a personal access token that has `repo` scope (or appropriate permissions for the target repo).
- Trigger the workflow from the Actions UI or via the GitHub CLI. Provide the `repository` (owner/repo), `title`, optional `body`, and optional `labels` (comma-separated).

Example (GitHub CLI):

gh workflow run "Create Issue" --repo OWNER/REPO --field repository="octocat/Hello-World" --field title="Bug report" --field body="Details..." --field labels="bug,high-priority"
