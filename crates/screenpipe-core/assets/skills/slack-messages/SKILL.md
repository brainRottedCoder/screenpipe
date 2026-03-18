# Slack Messages

You can interact with Slack to search and send messages.

## Capabilities

- **Search messages**: Find messages in channels
- **Send messages**: Post messages to channels
- **List channels**: Get list of available channels
- **Get thread**: Retrieve thread replies

## How to Use

This skill uses the Slack API. You'll need to configure a Slack connection with
an API token.

### Authentication

First, ensure you have a Slack connection configured:

1. Go to Connections in Pi settings
2. Add Slack connection with your Slack API token (from slack.com/apps)

### Search Messages

```python
import os
from slack_sdk import WebClient

client = WebClient(token=os.environ["SLACK_TOKEN"])

# Search messages
result = client.search_messages(
    query="meeting",
    channel="C01234567",
    count=10
)
```

### Send a Message

```python
# Send message to a channel
result = client.chat_postMessage(
    channel="#general",
    text="Hello from Pi!"
)
```

### List Channels

```python
# Get list of channels
result = client.conversations_list()
for channel in result["channels"]:
    print(f"{channel['name']} - {channel['id']}")
```

## Notes

- Requires a Slack connection with API token
- Token needs appropriate scopes: channels:read, chat:write, search:read
- Works in workspace-installed apps
- Message search is subject to Slack's retention policies
