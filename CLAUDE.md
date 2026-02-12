# CLAUDE.md

This file provides guidance to Claude Code (claude.ai/code) when working with code in this repository.

## What This Is

A single-file interactive tutorial for value investing (价值投资学习路径). The entire app lives in `value.html` — no build tools, no dependencies, no server required. Open the file directly in a browser.

## Architecture

`value.html` is a self-contained HTML/CSS/JS page structured as:

- **Data**: A `modules` array (6 learning modules) defined at the top of the `<script>` block. Each module has: id, title, level, keywords, learning items, practice exercises, and output deliverables.
- **State**: `state` object tracks the active module and completed modules. Persisted to `localStorage` under key `vi_path_progress_v1`.
- **Rendering**: Two main render functions — `renderList()` for the left sidebar module list (supports keyword filtering) and `renderContent()` for the right detail panel.
- **Layout**: CSS Grid two-column layout (sidebar + detail), responsive to single-column below 900px. Dark theme with CSS custom properties on `:root`.

## Key Interactions

- Click sidebar items to switch modules
- Search bar filters modules by title, level, keywords, and description
- Checkbox marks modules complete (saved locally)
- "复制输出物清单" copies the module's output list to clipboard
- "重置进度" clears all progress from localStorage
