# Apple Calendar

You can interact with Apple Calendar to create, read, update, and delete
calendar events.

## Capabilities

- **List calendars**: Get all calendars from Apple Calendar
- **Create events**: Create new calendar events with title, dates, location,
  notes
- **Update events**: Modify existing event details
- **Delete events**: Remove events from calendars
- **Query events**: Find events within a date range

## How to Use

Use AppleScript to interact with Calendar app. Here are the commands:

### List All Calendars

```applescript
tell application "Calendar"
    set calendarList to name of every calendar
    return calendarList
end tell
```

### Create an Event

```applescript
tell application "Calendar"
    tell calendar "Work"
        make new event at end with properties {summary:"Meeting with Team", start date:current date, end date:(current date + 3600)}
    end tell
end tell
```

### Get Events in Date Range

```applescript
tell application "Calendar"
    set startDate to date "Monday of this week"
    set endDate to date "Friday of this week"
    tell calendar "Work"
        set eventsList to events where start date >= startDate and start date <= endDate
        return summary of eventsList
    end tell
end tell
```

### Delete an Event

```applescript
tell application "Calendar"
    tell calendar "Work"
        set eventList to events where summary contains "Meeting"
        delete item 1 of eventList
    end tell
end tell
```

## Notes

- Calendar names are case-sensitive
- Dates must be in a format AppleScript understands
- Requires Calendar app permissions on macOS
- Works best on macOS with Calendar app installed
