# Data

The raw database file is not included in this repository due to its size.

## Download

Download `barcelona_urban.db` from Google Drive:
[Download here](https://drive.google.com/file/d/12IFJiGeatOGfKS_sa21_GotuCp8T8Ot9/view?usp=sharing)

Once downloaded, place the file in this `/data` folder.

## What's inside

The DuckDB database contains three schema layers:

| Schema | Description |
|---|---|
| `bronze` | Raw ingested data — untouched source tables |
| `silver` | Cleaned and standardised tables |
| `gold` | Star schema with dimension and fact tables ready for BI |