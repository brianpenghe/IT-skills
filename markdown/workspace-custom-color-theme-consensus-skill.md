---
name: workspace-custom-color-theme
description: Configure a specific Cursor or VS Code workspace with custom colors using .code-workspace settings or .vscode/settings.json. Use when the user wants one project window tinted a specific color without changing global editor settings, or when extending a theme from window chrome into the full editor, tabs, sidebar, panel, and terminal.
disable-model-invocation: true
---

# Workspace Custom Color Theme

Use this skill when a user wants one Cursor workspace or folder to have its own color identity without changing the global app theme.

## Goal

Apply a custom color palette to a single workspace window, including:

- title bar
- activity bar
- sidebar
- tabs
- editor background
- panel
- terminal
- lists, inputs, and accents

## Scope Rule

Use workspace settings, not global user settings.

| Scope | File | Affects |
| --- | --- | --- |
| Workspace file | `project.code-workspace` | Only when that workspace file is opened |
| Folder settings | `.vscode/settings.json` | Only when that folder is opened |
| Global user settings | `~/Library/Application Support/Cursor/User/settings.json` | Every Cursor window |

If it is unclear whether the user opens the project as a folder or via a `.code-workspace` file, update both the workspace file and `.vscode/settings.json`.

## Workflow

1. Read the existing workspace-level settings file if present.
2. Preserve unrelated settings.
3. Decide whether the palette should be dark-centered or light-centered.
4. Set `workbench.colorTheme` to a compatible base theme.
5. Add or update `workbench.colorCustomizations`.
6. Tell the user they may need one `Reload Window` for the current window.

## Choose the Base Theme Carefully

### Dark-centered palettes

For dark purple, navy, charcoal, or similar themes, a dark base is usually best:

```json
"workbench.colorTheme": "Default Dark Modern"
```

### Light-centered palettes

If the user wants pale yellow, cream, fog, pastel orange, or another light center background, use a light base theme so chat and editor text stay readable:

```json
"workbench.colorTheme": "Cursor Light"
```

This is important because Cursor chat text inherits theme-level foreground behavior. A light editor background paired with a dark base theme can make chat text hard to read.

## Full-Window Theming Rule

If the user wants the whole window themed, changing only the title bar and status bar is not enough.

Change these token groups together:

1. **Window chrome**
   - `titleBar.*`
   - `activityBar.*`
   - `statusBar.*`

2. **Navigation**
   - `sideBar.*`
   - `sideBarSectionHeader.*`
   - `list.*`

3. **Main work area**
   - `editor.*`
   - `editorGroupHeader.*`
   - `tab.*`
   - `panel.*`
   - `terminal.*`
   - `breadcrumb.*`

4. **Accents**
   - `focusBorder`
   - `button.*`
   - `badge.*`
   - `progressBar.*`
   - `input.*`
   - `dropdown.*`

## Minimal Workspace Example

```json
{
  "folders": [
    {
      "path": "."
    }
  ],
  "settings": {
    "workbench.colorTheme": "Default Dark Modern",
    "workbench.colorCustomizations": {
      "titleBar.activeBackground": "#5b3a8d",
      "titleBar.activeForeground": "#f6f0ff"
    }
  }
}
```

## Minimal Folder Settings Example

```json
{
  "workbench.colorTheme": "Default Dark Modern",
  "workbench.colorCustomizations": {
    "titleBar.activeBackground": "#5b3a8d",
    "titleBar.activeForeground": "#f6f0ff"
  }
}
```

## Dark Purple Palette Example

Use this for a dark, cohesive purple workspace:

```json
{
  "workbench.colorTheme": "Default Dark Modern",
  "workbench.colorCustomizations": {
    "titleBar.activeBackground": "#5b3a8d",
    "titleBar.activeForeground": "#f6f0ff",
    "titleBar.inactiveBackground": "#3d295f",
    "titleBar.inactiveForeground": "#d8c8f0",
    "activityBar.background": "#4a2f73",
    "activityBar.foreground": "#f6f0ff",
    "activityBarBadge.background": "#c084fc",
    "activityBarBadge.foreground": "#1f1233",
    "sideBar.background": "#241633",
    "sideBar.foreground": "#efe7fb",
    "sideBarSectionHeader.background": "#2b1b3d",
    "sideBarSectionHeader.foreground": "#f3ecff",
    "editor.background": "#1b1326",
    "editorGroupHeader.tabsBackground": "#20162d",
    "editorGroupHeader.tabsBorder": "#3b2854",
    "tab.activeBackground": "#312045",
    "tab.activeForeground": "#f8f4ff",
    "tab.inactiveBackground": "#241633",
    "tab.inactiveForeground": "#cdbcdf",
    "tab.border": "#3b2854",
    "panel.background": "#1d1528",
    "panel.border": "#3b2854",
    "panelTitle.activeForeground": "#f3ecff",
    "panelTitle.inactiveForeground": "#bcaed3",
    "panelTitle.activeBorder": "#a855f7",
    "list.activeSelectionBackground": "#4a2f73",
    "list.activeSelectionForeground": "#f8f4ff",
    "list.inactiveSelectionBackground": "#37244f",
    "list.hoverBackground": "#2e1f43",
    "input.background": "#261a36",
    "input.foreground": "#f3ecff",
    "input.border": "#6d4aa6",
    "dropdown.background": "#261a36",
    "dropdown.foreground": "#f3ecff",
    "dropdown.border": "#6d4aa6",
    "statusBar.background": "#5b3a8d",
    "statusBar.foreground": "#f6f0ff",
    "statusBar.debuggingBackground": "#7c3aed",
    "statusBar.debuggingForeground": "#fdfaff"
  }
}
```

## Light Warm Palette Example

Use this pattern for yellow, cream, orange, coral, or fog-inspired themes:

```json
{
  "workbench.colorTheme": "Cursor Light",
  "workbench.colorCustomizations": {
    "foreground": "#000000",
    "descriptionForeground": "#222222",
    "titleBar.activeBackground": "#E8C547",
    "titleBar.activeForeground": "#000000",
    "titleBar.inactiveBackground": "#D4B03A",
    "titleBar.inactiveForeground": "#222222",
    "activityBar.background": "#E8C547",
    "activityBar.foreground": "#000000",
    "activityBar.inactiveForeground": "#444444",
    "activityBarBadge.background": "#8B6914",
    "activityBarBadge.foreground": "#FFFFFF",
    "sideBar.background": "#F5E6A3",
    "sideBar.foreground": "#000000",
    "sideBarTitle.foreground": "#000000",
    "sideBarSectionHeader.background": "#E8C547",
    "sideBarSectionHeader.foreground": "#000000",
    "editor.background": "#FFF8DC",
    "editor.foreground": "#000000",
    "editorGroupHeader.tabsBackground": "#E8C547",
    "editorGutter.background": "#FFF8DC",
    "input.background": "#FFFCE8",
    "input.foreground": "#000000",
    "input.border": "#D4B03A",
    "tab.activeBackground": "#FFF8DC",
    "tab.activeForeground": "#000000",
    "tab.inactiveBackground": "#E8C547",
    "tab.inactiveForeground": "#222222",
    "panel.background": "#F5E6A3",
    "panel.border": "#D4B03A",
    "panelTitle.activeForeground": "#000000",
    "terminal.background": "#FFF8DC",
    "terminal.foreground": "#000000",
    "breadcrumb.background": "#FFF8DC",
    "breadcrumb.foreground": "#000000",
    "list.activeSelectionForeground": "#000000",
    "list.inactiveSelectionForeground": "#000000",
    "statusBar.background": "#E8C547",
    "statusBar.foreground": "#000000"
  }
}
```

## Readability Rule

For light palettes:

- keep editor, input, terminal, list, and chat-adjacent text dark
- prefer black or near-black foregrounds
- avoid pairing a pale editor background with a dark base theme

For dark palettes:

- use light foregrounds on dark surfaces
- keep borders and accents saturated, but keep large background surfaces muted

## Troubleshooting

- **Colors do not show in the current window:** Reload once with `Developer: Reload Window`.
- **Workspace file settings do not apply:** The user may have opened the folder instead of the `.code-workspace` file.
- **Folder settings do not apply:** Confirm `.vscode/settings.json` is in the opened folder root.
- **Only the top and bottom bars changed:** Add `editor.*`, `tab.*`, `panel.*`, `terminal.*`, and `breadcrumb.*`.
- **Chat or input text is hard to read on a pale background:** Switch to `Cursor Light` and explicitly set dark foreground tokens.

## Response Guidance

After making changes:

- say whether you updated `.code-workspace`, `.vscode/settings.json`, or both
- mention if the palette is built on a dark or light base theme
- mention that one reload may be needed for the current window
- say that newly opened windows for that workspace should pick up the colors automatically

## Notes

- Prefer subtle background tints so the UI remains readable.
- Stronger colors usually work best as accents rather than full-surface fills.
- Do not overwrite unrelated workspace settings.
