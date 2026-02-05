Create Issue workflow

This repository contains a GitHub Actions workflow that creates an issue in a specified repository when triggered manually, and optionally adds it to a GitHub Project.

Usage

- Set a repository secret named `GH_TOKEN` with a personal access token that has `repo` scope (or appropriate permissions for the target repo).
- If using the project assignment feature, ensure your token also has the `project` scope.
- Trigger the workflow from the Actions UI or via the GitHub CLI. Provide the `repository` (owner/repo), `title`, optional `body`, optional `labels` (comma-separated), and optional `project_number`.

Example (GitHub CLI):

```bash
# Create an issue without adding to a project
gh workflow run "Create Issue" --repo OWNER/REPO --field repository="octocat/Hello-World" --field title="Bug report" --field body="Details..." --field labels="bug,high-priority"

# Create an issue and add it to project #1
gh workflow run "Create Issue" --repo OWNER/REPO --field repository="octocat/Hello-World" --field title="Feature request" --field body="Add new feature" --field project_number="1"
```

Parameters

- `repository` (required): The target repository in `owner/repo` format
- `title` (required): The issue title
- `body` (optional): The issue description
- `labels` (optional): Comma-separated list of labels to apply
- `project_number` (optional): The project number (e.g., 1 for project #1) to add the issue to

Requirements for Project Assignment

To use the project assignment feature:
1. Your `GH_TOKEN` must have both `repo` and `project` scopes
2. The project must exist in the target repository
3. You must have write access to the project
