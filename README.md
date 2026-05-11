# streamlit-keepalive

A GitHub Actions bot that prevents Streamlit Community Cloud apps from going to sleep due to inactivity.

## How it works

Streamlit Community Cloud shuts down apps after 12 hours without user activity. This repo runs a scheduled GitHub Action every 6 hours that uses a headless browser to visit the app and click the wake-up button if it appears.

## Setup

1. Clone or fork this repo
2. Set the `STREAMLIT_APP_URL` environment variable in your GitHub Actions secrets, or edit the default URL directly in `main.py`
3. Push to GitHub, the workflow will run automatically on schedule

## Files

- `main.py` — Selenium script that visits the app and clicks the wake-up button if needed
- `.github/workflows/workflow.yml` — GitHub Actions workflow that triggers every 6 hours
- `requirements.txt` — Python dependencies (`selenium`, `webdriver-manager`)
