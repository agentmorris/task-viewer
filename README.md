# Task Viewer

A web-based interface for visualizing tasks in a structured markdown format.

## Usage

### Local testing

1. Start a local web server in the parent directory:
   ```bash
   cd ..
   python -m http.server 8000
   ```

2. Open in browser with a file parameter:
   ```
   http://localhost:8000/task-viewer/?file=TODO.md
   ```

### Production use with GitHub

Use the raw GitHub URL as the file parameter:

```
https://yourserver.com/task-viewer/?file=https://raw.githubusercontent.com/user/repo/main/TODO.md
```

For example:

```
https://dmorris.net/task-viewer/?file=https://raw.githubusercontent.com/agentmorris/MegaDetector/refs/heads/main/TODO.md
```


## Features

- **Filtering**: Filter by priority range (P0-P4), effort range (E0-E4), and tags
- **Sorting**: Automatically sorts by priority (ascending), then effort (ascending)
- **Markdown Rendering**: Full markdown support in task descriptions
- **Toggle Descriptions**: Option to hide descriptions for a compact view
- **Responsive Design**: Works on desktop and mobile devices

## File format

The tool expects a markdown file with:

1. A level-1 header called "Issues" 
2. Level-2 headers for each task
3. Each task must have:
   - Description (markdown text)
   - Priority: `P[0-4]` on its own line
   - Effort: `E[0-4]` on its own line  
   - At least one tag: `!tag-name`

## Dependencies

- [marked.js](https://marked.js.org/) for markdown parsing (loaded from CDN)
- No build process required - single HTML file with embedded CSS/JS
