# VSE LaTeX Devcontainer

Development container for writing LaTeX thesis with AI assistance.

## Prerequisites

- [Docker](https://www.docker.com/products/docker-desktop/)
- [VS Code](https://code.visualstudio.com/) with [Dev Containers extension](https://marketplace.visualstudio.com/items?itemName=ms-vscode-remote.remote-containers)

## Getting Started

1. Open this folder in VS Code
2. Click "Reopen in Container" when prompted (or run `Dev Containers: Reopen in Container` from command palette)
3. Wait for container to build
4. Start writing in `text/prace.tex`

## Commands

Run `task` in terminal to see all available commands:

```
task build       # Compile PDF
task watch       # Auto-rebuild on changes
task clean       # Remove auxiliary files
task wordcount   # Count words
```

## Live PDF Preview

1. Open any `.tex` file (e.g., `text/prace.tex`)
2. Press `Ctrl+Alt+V` to open PDF preview (or click the green play button)
3. Edit and save (`Ctrl+S`) — PDF rebuilds automatically

**Shortcuts:**
- `Ctrl+Alt+B` — Build PDF
- `Ctrl+Alt+V` — View PDF
- `Ctrl+Click` in PDF — Jump to source
- `Ctrl+Alt+J` — Jump from source to PDF

## Included Tools

- **LaTeX Workshop** - Syntax highlighting, auto-build on save, PDF preview
- **Claude Code** - AI assistant (`claude` in terminal)
- **Gemini** - AI assistant (VS Code sidebar)
- **LTeX** - Grammar checking (Czech + English)

## Disclaimer

The LaTeX template included in this repository is based on the official VSE FIS thesis template available on the faculty intranet. The author of this repository is not responsible for any deviations from or changes to the official template. **Users are responsible for verifying that their thesis adheres to the current official requirements and template specifications.**
