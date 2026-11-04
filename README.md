# NAVPu_Date_Formatter

A lightweight, single-file browser tool that standardizes dates in NAVPu Excel exports to `MM/DD/YYYY` across all sheets, while keeping the original formatting.

## Why

NAVPu calculation exports mix padded dates (`10/01/2020`) and unpadded dates (`10/1/2020`). This causes inconsistencies when the data is used in Excel. This tool converts every date to `MM/DD/YYYY` in one click.

## Features

- Upload an `.xlsx` file and convert every date in **all sheets** at once
- Date cells are saved as **Text**, so Excel keeps the `MM/DD/YYYY` format
- Fonts, borders, column widths, and number formats are preserved
- Shows how many dates were converted in each sheet
- Paste box for converting a quick list of dates, with a **Copy to clipboard** button for pasting into Excel
- Runs entirely in your browser. Files are never uploaded anywhere

## Usage

1. Open `index.html` in your browser (an internet connection is needed to load the ExcelJS library).
2. Under **Option 1**, choose your Excel file and click **Convert & Download**.
3. Open the downloaded `<filename>_converted.xlsx`. Your original file is not changed.

For a quick list of dates, use **Option 2**: paste the dates, click **Convert**, then **Copy to clipboard** and paste into Excel.

## What gets converted

| Column         | Before       | After        |
| -------------- | ------------ | ------------ |
| Price Date     | `10/1/2020`  | `10/01/2020` |
| Inception Date | `2/14/2018`  | `02/14/2018` |

All other columns (NAV values, ROI, dividend rate, etc.) are left untouched.

## Project structure

```
.
├── index.html   # the whole app (HTML, CSS, JavaScript)
└── README.md
```

## Built with

- HTML, CSS, JavaScript
- [ExcelJS](https://github.com/exceljs/exceljs) (loaded from cdnjs)

## Hosting (optional)

To share it as a web page, push the repository to GitHub and enable **Settings → Pages**, then select the main branch. `index.html` will be served as the home page.

## Notes

- Converted dates are stored as text, so Excel will not sort or filter them as real dates.
- Supports `.xlsx` and `.xlsm` files.
