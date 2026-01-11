# CLAUDE.md

This file provides guidance to Claude Code (claude.ai/code) when working with code in this repository.

## Project Overview

A static travel checklist web app with no build system or dependencies. Pure HTML/CSS/JavaScript.

## Development

No build or install steps required. Open `travel-checklist.html` directly in a browser.

## Architecture

Single-file architecture with embedded CSS and JavaScript:

- **Data**: Checklist items defined in `items` array (line ~233), organized by category objects with `category` name and `items` array
- **State**: `checkedItems` object stores checked state, persisted to localStorage under key `travelChecklist`
- **Rendering**: `render()` builds DOM from items array; `refreshSort()` re-renders with unchecked items first
- **Important items**: Items containing `!!!` or in "Dokumendid" category get `.important` class (red styling)

## Key Functions

- `toggleItem(itemId)` - Check/uncheck item, itemId format: `{category}-{itemName}`
- `clearAll()` / `refreshSort()` - Attached to window for onclick handlers
- `loadState()` / `saveState()` - localStorage persistence

## Adding New Items

Edit the `items` array in the `<script>` section. Each category object:
```javascript
{ category: 'Category Name', items: ['Item 1', 'Item 2'] }
```
