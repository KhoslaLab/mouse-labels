# 🐭 Mouse Label Printer

A single-page web application for generating ZPL (Zebra Programming Language) labels for mouse sample identification. Designed to run on [GitHub Pages](https://pages.github.com/) with no server, database, or dependencies required.

## Overview

This tool replaces a manual Excel-based workflow for printing mouse sample labels on Zebra thermal printers. It generates ZPL commands that produce labels with three columns per physical label, each containing a mouse identifier (AS number), sample type, and date.

### Features

- **Harvest Labels** — Generate a full set of sample labels for a range of mice using the standard harvest template, or custom sample names.
- **Manual Labels** — Create arbitrary labels with any text on two lines plus a date, with adjustable quantity per label.
- **Import & Edit** — Import a previously downloaded `.txt` label file to edit and reprint. Drag and drop or click to browse. Harvest-compatible files automatically load into the Harvest Labels page; all others open in Manual Labels.
- **Custom Labels with Drag-and-Drop** — Reorder custom labels by dragging chips, and click any label name to edit it in place.
- **Load Standard Template** — Pre-fill the custom label editor with standard harvest labels so you can make small modifications without starting from scratch.
- **Project Name** — Optional project name included in downloaded filenames and optionally printed as a 4th line on every label.
- **Date Toggle** — Include or exclude the date from labels with a single checkbox.
- **Print or Download** — Print directly to a Zebra printer via the browser print dialog, or download a `.txt` file to print from Notepad.
- **Length Warnings** — Live character counters on all text inputs warn when text exceeds the ~13 character column width of the ZPL layout.
- **No Dependencies** — Runs entirely in the browser as a single HTML file. No install, no build step, no server.

## Quick Start

1. Host `index.html` on GitHub Pages (or open it directly in a browser).
2. See [USAGE.md](USAGE.md) for detailed instructions, or click the **Usage Guide** link in the app header.

## Deployment

To deploy on GitHub Pages:

1. Create a new GitHub repository.
2. Add `index.html`, `USAGE.html`, and any other files to the root of the repository.
3. Go to **Settings → Pages** and set the source to the `main` branch.
4. The app will be available at `https://<username>.github.io/<repo-name>/`.

Alternatively, open `index.html` directly in any modern browser — no web server needed.

## ZPL Format

Each physical label prints three columns at ZPL field positions x=240, x=440, and x=640. Each column contains up to four lines:

| Line | Y Position | Content                  |
|------|-----------|--------------------------|
| 1    | y=20      | AS number (or any text)  |
| 2    | y=50      | Sample name (or any text)|
| 3    | y=80      | Date (optional)          |
| 4    | y=110     | Project name (optional)  |

The ZPL uses `^AD` (Font D) and `^CFD` (default font D). The base 3-line format is compatible with the existing Excel-based label workflow and produces byte-identical output for the standard harvest template.

## License

This project is licensed under the [MIT License](LICENSE).

## AI-Generated Code Disclaimer

This application was generated with the assistance of Claude, an AI assistant created by [Anthropic](https://www.anthropic.com/). The code, documentation, and usage instructions were produced through an iterative conversational process in which the developer described the requirements and the AI generated the implementation. The ZPL output was verified against the original Excel-based label template to ensure compatibility. The developer is responsible for reviewing, testing, and maintaining this code.
