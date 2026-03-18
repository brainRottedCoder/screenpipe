# Google Calendar

You can interact with Google Calendar to create, read, update, and delete
calendar events via the Google Calendar API.

## Capabilities

- **List calendars**: Get all calendars from Google Calendar
- **Create events**: Create new calendar events with title, dates, location,
  description
- **Update events**: Modify existing event details
- **Delete events**: Remove events from calendars
- **Query events**: Find events within a date range

## How to Use

This skill uses the Google Calendar API. It works best when connected via
OAuth in the Screenpipe Connections settings.

### List All Calendars

```python
import os
from googleapiclient.discovery import build

def list_calendars():
    # Credentials are automatically handled by Screenpipe
    service = build('calendar', 'v3')
    calendar_list = service.calendarList().list().execute()
    return calendar_list.get('items', [])
```

### Create an Event

```python
def create_event(summary, start_time, end_time):
    service = build('calendar', 'v3')
    event = {
        'summary': summary,
        'start': {'dateTime': start_time},
        'end': {'dateTime': end_time},
    }
    event = service.events().insert(calendarId='primary', body=event).execute()
    return event['id']
```

### Get Events in Date Range

```python
def get_events(time_min, time_max):
    service = build('calendar', 'v3')
    events_result = service.events().list(
        calendarId='primary', 
        timeMin=time_min,
        timeMax=time_max, 
        singleEvents=True,
        orderBy='startTime'
    ).execute()
    return events_result.get('items', [])
```

## Notes

- Requires a Google Calendar connection
- Dates must be in RFC3339 format
- Primary calendar is used by default if calendarId is not specified
- Requires `https://www.googleapis.com/auth/calendar` scope
