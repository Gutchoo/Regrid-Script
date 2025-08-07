# 🗺️ Regrid-to-Airtable (and Google Sheets) Sync

This project automates the process of syncing property parcel data from **Regrid** with your internal database stored in **Airtable** (or optionally, **Google Sheets** for dashboard use in Looker Studio).

---

## 📌 Use Case

Real estate companies and analysts often need to track ownership data, property characteristics, and parcel-level metadata. This script:

- Pulls a list of APNs (Assessor Parcel Numbers) from your Airtable “Regrid Output” table.
- Queries the Regrid API to retrieve parcel-level data like lat/long, address, zoning, lot size, etc.
- Automatically filters for **currently owned** properties based on your internal ownership keywords.
- Cleans and normalizes APNs and formats the data.
- Updates the **Airtable** table (or **Google Sheets**) with the latest data:
  - Creates new records for new parcels.
  - Updates existing records if a parcel already exists.

---

## 🔧 Features

- ✅ Syncs with **Regrid API** using APNs
- ✅ Filters based on defined ownership strings
- ✅ Uploads data to **Airtable** or **Google Sheets**
- ✅ Clean formatting for geospatial dashboards (lat/long support)
- ✅ Supports Looker Studio for dashboard visualizations

---

## 🔐 Security & Privacy

Sensitive data like API keys and internal ownership terms are stored in a `.env` file and **never pushed to GitHub**. This project uses a `.gitignore` to avoid committing:

- `.env` (API keys)
- `google_creds.json` (Google Sheets credentials)
- `regrid_output.csv` (parcel data output)
- Jupyter cache files, virtual environments, and Python bytecode

---

## 📊 Ideal For

- Real estate investors or property managers tracking large portfolios
- Analysts creating automated geospatial dashboards (Looker Studio or custom)
- Teams collaborating via Airtable, Google Sheets, or a shared drive

---

## 📁 File Structure

- `regrid_api.ipynb` — main script for API sync and upload
- `.env` — stores API keys and secure config values (not pushed to GitHub)
- `google_creds.json` — credentials for Google Sheets (used only if exporting to Sheets)
- `requirements.txt` — list of Python dependencies

---

## 🚀 Future Plans

- Add support for pulling polygon data from Regrid
- Build an interactive web dashboard using Mapbox or Leaflet
- Allow multiple user accounts to manage their own portfolios

---
