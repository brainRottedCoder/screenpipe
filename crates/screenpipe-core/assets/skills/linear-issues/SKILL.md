# Linear Issues

Interacts with Linear to manage workspace issues and projects.

## Capabilities

- **Create issues**: Create new issues in a team
- **List issues**: Find issues by state, team, or assignee
- **Update issues**: Change issue status, assignee, or description
- **Search projects**: Find Linear projects

## How to Use

Requires a Linear connection with an API key (Personal Access Token).

### Create an Issue

```python
import os
import requests

def create_linear_issue(team_id, title, description):
    api_key = os.environ["LINEAR_API_KEY"]
    query = """
    mutation IssueCreate($input: IssueCreateInput!) {
        issueCreate(input: $input) {
            success
            issue { id title }
        }
    }
    """
    variables = {
        "input": {
            "teamId": team_id,
            "title": title,
            "description": description
        }
    }
    # Send request to Linear GraphQL API
```

## Notes

- Requires `LINEAR_API_KEY`
- Uses GraphQL API
- Works best when team ID is known
