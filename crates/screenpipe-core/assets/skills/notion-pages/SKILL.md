# Notion Pages

Creates and updates Notion pages, databases, and blocks.

## Capabilities

- **Create pages**: Add new pages to a parent page or database
- **Update blocks**: Append blocks to existing pages
- **Search pages**: Find pages by title
- **Query databases**: Filter and sort database entries

## How to Use

Requires a Notion connection with an Internal Integration Token.

### Create a Page

```python
import os
import requests

def create_notion_page(parent_id, title):
    token = os.environ["NOTION_TOKEN"]
    url = "https://api.notion.com/v1/pages"
    headers = {
        "Authorization": f"Bearer {token}",
        "Content-Type": "application/json",
        "Notion-Version": "2022-06-28"
    }
    data = {
        "parent": { "page_id": parent_id },
        "properties": {
            "title": [{ "text": { "content": title } }]
        }
    }
    # Send POST request
```

## Notes

- Requires `NOTION_TOKEN`
- Integration must have access to the parent page
- Blocks use a specific JSON structure
