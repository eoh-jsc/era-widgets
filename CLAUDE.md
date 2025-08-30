# CLAUDE.md

This file provides guidance to Claude Code (claude.ai/code) when working with code in this repository.

## Project Overview

This is a widget library for Era systems, containing reusable HTML/CSS/JavaScript components that integrate with the Era Widget framework. The widgets are self-contained HTML files that can be deployed to GitHub Pages.

## Architecture

- **Static Site**: Uses Jekyll for GitHub Pages deployment
- **Widget Registry**: `list.json` contains metadata for all available widgets
- **Widget Structure**: Each widget is a standalone HTML file with embedded CSS and JavaScript
- **Era Integration**: Widgets use the `@eohjsc/era-widget` library from unpkg CDN for Era system integration

## Widget Development Pattern

Each widget follows this structure:
- Complete HTML document with embedded styles and scripts
- Uses Era Widget library (`EraWidget` class) for configuration and data binding
- Implements `onConfiguration()` and `onValues()` callbacks for real-time data updates
- Calls `eraWidget.ready()` to initialize the widget

## Deployment

The repository automatically deploys to GitHub Pages via Jekyll workflow (`.github/workflows/jekyll-gh-pages.yml`) when changes are pushed to the main branch.

## Adding New Widgets

1. Create new HTML file with complete widget implementation
2. Add entry to `list.json` with name, file, and preview image
3. Create preview image (PNG format)
4. Commit changes to trigger automatic deployment