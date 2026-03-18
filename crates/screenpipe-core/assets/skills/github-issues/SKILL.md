# GitHub Issues

You can interact with GitHub to create and manage issues.

## Capabilities

- **List issues**: Get issues from a repository
- **Create issues**: Create new issues
- **Update issues**: Modify existing issues
- **Close issues**: Close issues
- **Add labels**: Add labels to issues

## How to Use

This skill uses the GitHub API. You'll need to configure a GitHub connection
with a personal access token.

### Authentication

First, ensure you have a GitHub connection configured:

1. Go to Connections in Pi settings
2. Add GitHub connection with your Personal Access Token

### List Issues

```python
import os
from github import Github

client = Github(os.environ["GITHUB_TOKEN"])
repo = client.get_repo("owner/repo")
issues = repo.get_issues(state="open")

for issue in issues:
    print(f"#{issue.number}: {issue.title}")
```

### Create an Issue

```python
repo = client.get_repo("owner/repo")
issue = repo.create_issue(
    title="Bug: Something is broken",
    body="Description of the bug",
    labels=["bug"]
)
```

### Close an Issue

```python
issue = repo.get_issue(number=123)
issue.edit(state="closed")
```

## Notes

- Requires a GitHub connection with a personal access token
- Token needs `repo` scope for private repositories
- Issues can include labels, assignees, and milestones
