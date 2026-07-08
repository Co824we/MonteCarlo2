# ALGO Edge Performance History

Streamlit app for historical trading performance, sit-out overlay analysis, and 1-year / 10-year Monte Carlo projections.

## Repository structure

```text
app.py
streamlit_app.py
requirements.txt
README.md
.gitignore
.streamlit/config.toml
montecarlo/streamlit_app.py
sample_data/sample_balance_history.csv
```

## Recommended Streamlit Cloud setting

Use this as the main file path:

```text
app.py
```

If your existing Streamlit app is still pointed at the old path, this repo also includes a compatible file at:

```text
montecarlo/streamlit_app.py
```

So either path will run the same app.

## Deployment steps

From the repository root:

```bash
git add app.py streamlit_app.py requirements.txt README.md .gitignore .streamlit/config.toml montecarlo/streamlit_app.py sample_data/sample_balance_history.csv
git commit -m "Deploy ALGO Edge sit-out overlay app"
git push
```

Then in Streamlit Cloud:

```text
Manage app -> Settings -> Main file path -> app.py
```

If your app is already configured to run `montecarlo/streamlit_app.py`, that will also work.

## CSV input format

Preferred format:

```csv
date,balance
2026-01-02,100000
2026-01-03,100450
```

The app also supports Date + Return or Date + P/L files.

## What the app does

- Upload historical balance / return / P&L CSVs
- Build a historical equity curve
- Compare full participation against a sit-out period
- Treat the sit-out period as cash, meaning returns are set to 0%
- Show opportunity cost or capital protected
- Run 1-year and 10-year Monte Carlo projections
- Compare full participation against sitting out for the first selected months
- Show ending-value distributions and percentile summary tables
