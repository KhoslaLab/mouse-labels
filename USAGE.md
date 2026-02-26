# Usage Instructions

## Getting Started

Open the app in your browser. There are two modes, accessible via the tabs at the top of the page:

- **Harvest Labels** — For generating standard mouse sample labels by AS number range.
- **Manual Labels** — For creating labels with arbitrary text on each line.

---

## Harvest Labels

Use this mode when processing mice and you need the standard set of sample labels for each mouse.

### Step 1: Mouse Range, Date, & Project

- **First AS Number** — Enter the number (without the "AS" prefix) of the first mouse. For example, enter `2243` for AS2243.
- **Last AS Number** — Enter the last mouse number in the range. Leave blank if printing labels for a single mouse.
- **Date** — Defaults to today. This date prints on every label (unless unchecked — see below).
- **Project Name** — Optional. If provided, it will be included in the downloaded filename (e.g., `20260226_INK-ATTAC_AS2243-AS2250.txt`).
- **Include date on labels** — Checked by default. Uncheck to omit the date line from all labels.
- **Print project name on labels (4th line)** — When checked, the project name is printed as a fourth line on every label.

A character counter appears next to the project name field as you approach or exceed the 13-character limit. Text longer than 13 characters may not fit within a label column.

### Step 2: Sample Labels

Choose one of two options:

#### Standard Harvest Template

Click **Standard Harvest Template** (selected by default). This uses the predefined set of 11 sample labels per mouse:

| Label # | Sample Name   |
|---------|---------------|
| 1–3     | Plasma        |
| 4       | LFemur+L4-6   |
| 5       | LTibia+L1-3   |
| 6       | RFem+RTib      |
| 7       | Met            |
| 8       | Dia            |
| 9       | Vert           |
| 10      | Met            |
| 11      | Dia            |
| 12      | Vert           |
| 13      | Met/Dia        |
| 14      | Vert           |
| 15      | (blank)        |

These are printed 3-across, resulting in 5 physical labels per mouse.

#### Custom Labels

Click **Custom Labels** to define your own set of sample names:

1. Type a sample name in the text field and click **+ Add** (or press Enter). A character counter shows when you're near or over the 13-character limit.
2. Click **+ Blank** to add a label with just the AS number and date (no sample name).
3. Click **Load Standard Template** to pre-fill with the standard harvest labels — useful when you only need to change a few.
4. **Click** any label name to edit it in place. Press Enter to confirm, or Escape to cancel.
5. **Drag** labels to reorder them — grab any label chip and drop it in a new position.
6. Click the **×** on any chip to remove it.
7. Click **Clear** to remove all custom labels.

### Step 3: Generate & Print

1. Click **Generate Labels** to create the ZPL data and see a preview.
2. Use one of two methods to print:

   **Print to Zebra (recommended)**
   - Click **Print to Zebra**.
   - Your browser's print dialog will open.
   - Select your Zebra printer from the printer list.
   - Click Print.

   **Download and print from Notepad**
   - Click **Download .txt** to save the file.
   - Open the downloaded `.txt` file in Notepad.
   - Go to **File → Print**.
   - Select your Zebra printer from the printer list.
   - Click Print.

---

## Manual Labels

Use this mode to create labels with any text — not limited to AS numbers or standard sample names.

### Step 1: Create Labels

- **Date** — Shared across all labels. Prints on the third line of every label (unless unchecked).
- **Project Name** — Optional. Included in the downloaded filename.
- **Include date on labels** — Checked by default. Uncheck to omit the date line.
- **Print project name on labels (4th line)** — When checked, the project name prints on every label.

Each row in the table defines one label:

- **Line 1 (top)** — Any text for the first line (e.g., an AS number, a sample ID, or a name).
- **Line 2 (middle)** — Any text for the second line (e.g., a sample type, or a description).
- **Qty** — Number of copies of this label to print. Defaults to 1.

A character counter appears on each text field as you approach or exceed the 13-character limit.

Click **+ Add Row** to add more labels. Click the **×** button on any row to remove it. Click **Clear All** to start over.

### Step 2: Generate & Print

Same as Harvest Labels — click **Generate Labels**, then use **Print to Zebra** or **Download .txt**.

---

## Label Preview

After generating, a preview section shows how labels will be grouped on physical labels (3 columns per label). You can expand **Show raw ZPL** to see the exact ZPL commands that will be sent to the printer.

- Labels shown in **red text** in the preview have text that may be too long to fit.
- Blank label slots appear as empty space between the top line and date.
- When the project name is printed on labels, it appears as a gold-colored 4th line in the preview.

---

## Character Limits

Each label column is approximately 200 dots wide. Using Zebra Font D, this accommodates roughly **13 characters** comfortably. Character counters appear on all text inputs:

- The counter turns **amber** as you approach the limit.
- The counter turns **red** with a "may not fit" warning when you exceed it.
- Labels that exceed the limit are highlighted in red in the preview.

You can still generate and print labels with longer text, but the text may be clipped on the physical label.

---

## Downloaded Filename Format

Downloaded files are named with the date first in YYYYMMDD format:

| Mode    | Example Filename                          |
|---------|-------------------------------------------|
| Harvest | `20260226_INK-ATTAC_AS2243-AS2250.txt`    |
| Harvest (no project) | `20260226_AS2243-AS2250.txt`   |
| Manual  | `20260226_INK-ATTAC_manual_labels.txt`    |
| Manual (no project)  | `20260226_manual_labels.txt`   |

---

## Printer Setup

The Zebra printer must be installed on your computer as a standard Windows/Mac printer. No special software (such as Zebra Browser Print) is required.

### Verifying your printer is set up

- **Windows** — Go to **Settings → Devices → Printers & scanners** and confirm your Zebra printer appears in the list.
- **Mac** — Go to **System Settings → Printers & Scanners** and confirm your Zebra printer appears.

If the printer is not listed, install it using the Zebra printer driver for your model before using this app.

---

## Troubleshooting

| Problem | Solution |
|---------|----------|
| Labels print as plain text instead of formatted labels | Make sure you selected the Zebra printer (not a paper printer) in the print dialog. The Zebra interprets the ZPL commands directly. |
| Text is cut off on the right side of a label | The label text is too long. Shorten it to 13 characters or fewer. |
| Browser print dialog doesn't show the Zebra printer | The printer may not be installed. See Printer Setup above. |
| Nothing prints | Check that the Zebra printer is powered on, connected, and has labels loaded. |
| Labels are misaligned | Check that the correct label size is configured in the Zebra printer driver settings. |
