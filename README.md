# StowNest B2C Lead Performance Dashboard

Monthly B2C valid / invalid lead analytics, read live from the leads Google Sheet.

**Live dashboard:** https://tabish188.github.io/LEADS/

## How the data updates

The page reads the Google Sheet every time it is opened, every 15 minutes while open,
when you return to the tab, and when you click **Refresh data**. Add a new row to the
sheet (Date, B2C Valid, B2C Invalid) and it appears on the next refresh. No redeploy needed.

The sheet must stay shared as **Anyone with the link can view**.

## Pointing at a different sheet

Edit `CONFIG.SHEET_CSV_URL` near the top of the script in `index.html`:

```
https://docs.google.com/spreadsheets/d/<SHEET_ID>/gviz/tq?tqx=out:csv&gid=<TAB_GID>
```

## Sheet format

| Column | Header | Example |
|---|---|---|
| A | Date | 8/1/2025 (= August 2025) |
| B | B2C Valid | 1481 |
| C | B2C Invalid | 1608 |

Rows with a date but no numbers yet are skipped until values are entered.
Duplicate months are summed and flagged with a warning on the page.
