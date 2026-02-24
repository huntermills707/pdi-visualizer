# PDI Visualizer

A minimal Dash app that displays **two synchronized choropleth maps** of U.S. counties:

* **Left map** – Social Determinants of Health (SDoH) index.
* **Right map** – CDC‑reported condition prevalence (diabetes, stroke, mental‑health metrics, etc.).

Both maps share a viewport store, so zoom/pan on one instantly mirrors the other. The UI is pure Dash/HTML; no custom JavaScript.

Available at [pdi‑visualizer.onrender.com](pdi‑visualizer.onrender.com), and may take a moment to warm up.

## Features

* **Dual synchronized maps**: Pan/zoom one map → the other follows.
* **State filter**: Drop‑down to focus on a single state or view the whole U.S.
* **Dynamic index/outcome selectors**: Choose from 4 deprivation indexes and 22 health outcomes.
* **Hover details**: County name, index value, and outcome rate.
* **Simple deployment**: Works with Gunicorn locally or on Render.com.

## Prerequisites

* Python 3.10+

## Installation & Setup

```
# Clone the repo 
git clone https://github.com/yourname/pdi-visualizer.git
cd pdi-visualizer

# Install dependencies
pip install -r requirements.txt

# start it
gunicorn -w 4 -b 0.0.0.0:8050 app:server
```

## Repo Structure

```
├── app.py                     # Main Dash app
├── requirements.txt           # Exact pip pins
├── geojson-counties-fips-post-2024.json   # County geometries (FIPS IDs)
├── county_results.csv         # Pre‑computed indexes + CDC condition rates
├── README.md                  # This file
└── .gitignore                 # Standard ignores (venv, __pycache__, etc.)
```

## License

MIT – feel free to fork, tweak, and ship it. Just keep the license file in the repo.

That’s it. Plug the files in, spin it up, and you’ll have a functional county‑level SDoH visualizer without any nonsense. Good luck!