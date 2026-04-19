# harborton_frog_shuttle

## Getting Started

### Clone the repository:

Create a project folder for if you do not have one already. It does not matter what it is called. Navigate into that folder in your terminal or command prompt. You can do this by running the command `cd path/to/your/project/folder` (replace `path/to/your/project/folder` with the actual path to your project folder).

```
git clone https://github.com/georgiakirkpatrick/harborton_frog_shuttle.git
cd harborton_frog_shuttle
```

Ensure all raw Excel files are placed in the `/frog_data` folder.

File names should follow the `frog_log_YYYY_YY.xlsx` format (no spaces).

### Install dependencies:

Run the following command in your terminal to install the necessary packages (pandas and openpyxl):

Mac:
`pip3 install -r requirements.txt`

Windows:
`pip install -r requirements.txt`

### Verify Data:
Ensure the `frog_data/` folder contains all raw Excel files before running `frog_data_cleaner.qmd`

File names should follow the `frog_log_YYYY_YY.xlsx` format (no spaces).

## Cleaning Process

The `frog_data_cleaner.qmd` script automatically ignores non-data tabs like "Legend" or "Moon Phases."

It dynamically identifies the end of the data by looking for the last valid date, automatically skipping "Total" rows at the bottom of the sheets.
