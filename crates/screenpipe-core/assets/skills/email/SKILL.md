# Email

Send and manage emails via SMTP or service-specific APIs.

## Capabilities

- **Send emails**: Compose and send messages to one or more recipients
- **Read emails**: Fetch latest messages from Inbox (if configured)
- **Drafts**: Save messages for later

## How to Use

Requires an Email connection (SMTP settings or Gmail/Outlook OAuth).

### Send an Email

```python
import os
import smtplib
from email.message import EmailMessage

def send_email(to, subject, body):
    msg = EmailMessage()
    msg.set_content(body)
    msg['Subject'] = subject
    msg['From'] = os.environ["EMAIL_USER"]
    msg['To'] = to

    # Configure SMTP client and send
```

## Notes

- Requires appropriate SMTP credentials or OAuth token
- Subject to daily sending limits of your provider
- HTML email support varies by client
