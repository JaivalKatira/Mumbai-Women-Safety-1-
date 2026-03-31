# 🛡️ Mumbai Women Safety Risk Map

Interactive dark-mode Streamlit dashboard that visualizes locality-wise women safety risk across Mumbai using heatmaps, circle markers, and live analytics.

---

## 🚀 Quick Start

### 1. Install dependencies
```bash
pip install -r requirements.txt
```

### 2. Make sure your data file is in the same folder
The app expects `data.csv` (your uploaded file, already included).

### 3. Run the app
```bash
streamlit run app.py
```

The app will open at **http://localhost:8501** in your browser.

---

## 📦 Project Structure

```
mumbai_safety_app/
├── app.py              ← Main Streamlit application
├── data.csv            ← Source dataset (538 Mumbai localities)
├── requirements.txt    ← Python dependencies
├── README.md           ← This file
└── safety_data.db      ← SQLite database (auto-created on first run)
```

---

## 🗺️ Features

| Feature | Description |
|---|---|
| **Interactive Map** | Folium dark-mode map centered on Mumbai with zoom/pan |
| **Heatmap Layers** | Separate red/amber/green heatmaps for High/Medium/Safe zones |
| **Circle Markers** | Per-locality pins with hover tooltips |
| **Tooltips** | Locality name, risk index, crimes against women, police density |
| **Layer Toggle** | Show/hide High / Medium / Safe zones independently |
| **Risk Slider** | Filter localities by risk index range |
| **Density Slider** | Filter by population density |
| **Locality Zoom** | Dropdown to fly to any locality on the map |
| **Analytics Charts** | Distribution bar charts, top crimes, police density |
| **Data Table** | Sortable top-25 riskiest localities with color coding |
| **CSV Upload** | Add new data via file upload → stored in SQLite |
| **CSV Export** | Download filtered data as CSV |
| **SQLite Backend** | Persistent storage with auto-seed from CSV |

---

## 🎨 Risk Classification

| Risk Index | Category | Map Color |
|---|---|---|
| ≥ 15 | High Risk | 🔴 Red heatmap |
| 7 – 15 | Medium Risk | 🟡 Amber heatmap |
| < 7 | Safe Zone | 🟢 Green heatmap |

---

## 🔄 Uploading New Data

1. Prepare a CSV with the same columns as the original dataset
2. In the sidebar, click **Upload New Data (CSV)**
3. The app appends the new rows to the SQLite database
4. The map and analytics refresh automatically

---

## 🛠️ Tech Stack

- **Streamlit** — UI framework
- **Folium + streamlit-folium** — Interactive maps
- **Pandas / NumPy** — Data processing
- **SQLite** — Persistent backend database
- **CartoDB Dark Matter** — Dark base map tiles

---

## 💡 Notes

- Geocoding is pre-built for all 538 localities using OSM-verified coordinates
- Unknown locality names fall back to zone-based approximate coordinates
- The SQLite DB is auto-seeded from `data.csv` on first launch
- All coordinates are within Mumbai's geographic bounding box
