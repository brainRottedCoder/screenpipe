---
name: screenpipe-analytics
title: Screenpipe Analytics
description: Run raw SQL queries on the Screenpipe database
---

# Screenpipe Analytics

This skill enables Pi to run raw SQL queries on the Screenpipe database for
advanced analytics.

## Usage

Use this skill when the user wants to:

- Run custom SQL queries on screen/audio data
- Generate analytics reports
- Export data in custom formats
- Perform complex filtering and aggregation

## Capabilities

- Direct SQLite database access
- Query optimization hints
- Result formatting
- Export to CSV/JSON

## Guardrails

- Only query data that the user has access to
- Prevent destructive queries (DELETE, DROP, etc.)
- Limit result set size for performance
