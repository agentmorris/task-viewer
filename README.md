# Task Viewer

A web-based interface for visualizing tasks in a structured markdown format.

## Why did I make this? 

...or rather, why did AI make this for me?

GitHub Issues is a great way to <i>view</i> issues, and a great way to <i>collaborate on issues that are actively being worked on</i>, but I don't like using GitHub Issues as a primary source of truth for open issues: I find it very cumbersome to edit, and also ironically changes you make to issues aren't tracked in git, which I find annoying.  So I wanted the convenience of a simple markdown file for tracking issues that aren't being actively worked on, with the visualization/sorting/filtering capabilities that GitHub Issues gives you.  So I made this tool, primarily to manage the [issue list for the MegaDetector repo](https://dmorris.net/task-viewer/?file=https://raw.githubusercontent.com/agentmorris/MegaDetector/refs/heads/main/TODO.md
).


## Usage

### Local testing

1. Start a local web server in the repo root:
   ```bash
   cd ~/git/task-viewer
   python -m http.server 8000
   ```

2. Open in browser with a file parameter:
   ```
   http://localhost:8000/?file=well-formatted-example.md
   ```

Only the current directory is available via python -m http.server, so, note to self, I made a link called "link-to-megadetector", so I can view the MegaDetector TODO list locally by running:

`python -m http.server 8000`

...then visiting:

<http://localhost:8000/?file=link-to-megadetector/TODO.md>


### Production use with GitHub

Use the raw GitHub URL as the file parameter:

```
https://yourserver.com/task-viewer/?file=https://raw.githubusercontent.com/user/repo/main/TODO.md
```

For example:

<https://dmorris.net/task-viewer/?file=https://raw.githubusercontent.com/agentmorris/MegaDetector/refs/heads/main/TODO.md>


## Features

- **Filtering**: Filter by priority range (P0-P4), effort range (E0-E4), and tags
- **Sorting**: Automatically sorts by priority (ascending), then effort (ascending)
- **Markdown rendering**: Full markdown support in task descriptions
- **Toggle descriptions**: Option to hide descriptions for a compact view
- **Responsive design**: Works on desktop and mobile devices

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
