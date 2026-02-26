# 🐭 Mouse Label Printer

A single-page web application for generating ZPL (Zebra Programming Language) labels for mouse sample identification. Designed to run on [GitHub Pages](https://pages.github.com/) with no server, database, or dependencies required.

## Overview

This tool replaces a manual Excel-based workflow for printing mouse sample labels on Zebra thermal printers. It generates ZPL commands that produce labels with three columns per physical label, each containing a mouse identifier (AS number), sample type, and date.

### Features

- **Harvest Labels** — Generate a full set of sample labels for a range of mice using the standard harvest template or custom sample names.
- **Manual Labels** — Create arbitrary labels with any text on two lines plus a date, with adjustable quantity per label.
- **Project Name** — Optional project name included in downloaded filenames for organization.
- **Print or Download** — Print directly to a Zebra printer via the browser print dialog, or download a `.txt` file to print from Notepad.
- **Length Warnings** — Visual warnings when label text exceeds the ~18 character column width of the ZPL layout.
- **No Dependencies** — Runs entirely in the browser as a single HTML file. No install, no build step, no server.

## Quick Start

1. Host `index.html` on GitHub Pages (or open it directly in a browser).
2. See [USAGE.md](USAGE.md) for detailed instructions.

## Deployment

To deploy on GitHub Pages:

1. Create a new GitHub repository.
2. Add `index.html` to the root of the repository.
3. Go to **Settings → Pages** and set the source to the `main` branch.
4. The app will be available at `https://<username>.github.io/<repo-name>/`.

Alternatively, open `index.html` directly in any modern browser — no web server needed.

## ZPL Format

Each physical label prints three columns at ZPL field positions x=240, x=440, and x=640. Each column contains three lines:

| Line | Y Position | Content        |
|------|-----------|----------------|
| 1    | y=20      | AS number      |
| 2    | y=50      | Sample name    |
| 3    | y=80      | Date           |

The ZPL uses `^AD` (Font D) and `^CFD` (default font D). This format is compatible with the existing Excel-based label workflow and produces byte-identical output.

## License

This project is licensed under the [MIT License](LICENSE).

## AI-Generated Code Disclaimer

This application was generated with the assistance of Claude, an AI assistant created by [Anthropic](https://www.anthropic.com/). The code, documentation, and usage instructions were produced through an iterative conversational process in which the developer described the requirements and the AI generated the implementation. The ZPL output was verified against the original Excel-based label template to ensure compatibility. The developer is responsible for reviewing, testing, and maintaining this code.
