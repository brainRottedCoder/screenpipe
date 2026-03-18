# Apple Reminders

You can interact with Apple Reminders to create, complete, and list reminders.

## Capabilities

- **List reminder lists**: Get all reminder lists from Apple Reminders
- **Create reminders**: Add new reminders to specific lists
- **Complete reminders**: Mark reminders as done
- **Delete reminders**: Remove reminders
- **Query reminders**: Find reminders by various criteria

## How to Use

Use AppleScript to interact with Reminders app. Here are the commands:

### List All Reminder Lists

```applescript
tell application "Reminders"
    set listNames to name of every list
    return listNames
end tell
```

### Create a Reminder

```applescript
tell application "Reminders"
    tell list "Work"
        make new reminder with properties {name:"Finish report", due date:current date}
    end tell
end tell
```

### List Incomplete Reminders

```applescript
tell application "Reminders"
    set incompleteReminders to reminders whose completed is false
    return name of incompleteReminders
end tell
```

### Complete a Reminder

```applescript
tell application "Reminders"
    set reminderList to reminders whose name contains "Finish report"
    set completed of item 1 of reminderList to true
end tell
```

### Delete a Reminder

```applescript
tell application "Reminders"
    set reminderList to reminders whose name contains "old reminder"
    delete item 1 of reminderList
end tell
```

## Notes

- Reminder list names are case-sensitive
- Reminders can have due dates, priorities, and notes
- Requires Reminders app permissions on macOS
- Works best on macOS with Reminders app installed
