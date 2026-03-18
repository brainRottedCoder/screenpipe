---
name: screenpipe-elements
title: Screenpipe Elements
description: Query structured UI elements from the accessibility tree
---

# Screenpipe Elements

This skill enables Pi to query structured UI elements from the accessibility
tree.

## Usage

Use this skill when the user wants to:

- Find specific UI elements on screen
- Query element properties (text, bounds, role, etc.)
- Interact with UI elements programmatically
- Extract structured data from applications

## Capabilities

- Accessibility tree traversal
- Element property queries
- Spatial queries (elements at coordinates)
- Role-based filtering

## Guardrails

- Only query elements from visible windows
- Respect accessibility permissions
- Handle missing accessibility APIs gracefully
