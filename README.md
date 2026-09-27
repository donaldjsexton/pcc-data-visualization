# Python Crash Course — Data Visualization Projects

My work following along with **Python Crash Course, 2nd Edition** by Eric Matthes
(No Starch Press). This folder covers **Part II, Project 1: Data Visualization** —
chapters 15–17, working through Matplotlib, Plotly, CSV/JSON parsing, and
pulling live data from web APIs.

Code here is written by hand as I work through the book's examples and
"Try It Yourself" exercises, so it includes my own tweaks and experiments
rather than being a copy of the book's finished listings.

## Projects

### Matplotlib basics (Ch. 15)

| File | What it does |
| --- | --- |
| [mpl_squares.py](mpl_squares.py) | First Matplotlib plot — a line graph of the first five square numbers. Covers `subplots()`, titles, axis labels, and tick styling. |
| [scatter_squares.py](scatter_squares.py) | Scatter plot of 1,000 square numbers, colored with a `Blues` colormap to show sequential values. Also sets explicit axis ranges. |

### Random walks (Ch. 15)

| File | What it does |
| --- | --- |
| [random_walk.py](random_walk.py) | The `RandomWalk` class — generates a walk by repeatedly choosing a random direction and distance for each step, rejecting steps that go nowhere. |
| [rw_visual.py](rw_visual.py) | Plots a 50,000-point random walk as a scatter, coloring points by step number so the path's chronology is visible. Start and end points are highlighted, axes hidden, and it loops so you can generate walk after walk. |

### Rolling dice with Plotly (Ch. 15)

| File | What it does |
| --- | --- |
| [die.py](die.py) | A simple `Die` class with a configurable number of sides and a `roll()` method. |
| [die_visual.py](die_visual.py) | Rolls two D6 a thousand times, tallies the frequency of each total, and renders an interactive Plotly bar chart — showing the triangular distribution you get from summing two dice. |

### Downloading data: CSV (Ch. 16)

| File | What it does |
| --- | --- |
| [sitka_highs.py](sitka_highs.py) | Reads a year of NOAA weather CSV data, parses dates with `datetime.strptime()`, and plots daily highs and lows with the range shaded between them. Uses `try`/`except` to survive missing readings. |
| [death_valley_highs_lows.py](death_valley_highs_lows.py) | Prints the CSV header row with its column indexes — the reconnaissance step for figuring out which columns hold dates and temperatures before plotting a new dataset. |

### Downloading data: JSON and maps (Ch. 16)

| File | What it does |
| --- | --- |
| [eq_explore_data.py](eq_explore_data.py) | Parses a USGS GeoJSON earthquake feed, pulls magnitude, longitude, latitude, and title out of each nested feature dict, and plots them on an interactive Plotly `Scattergeo` world map. Marker size and color both scale with magnitude, with hover text naming each quake. |

## Data

[data/](data/) holds the datasets used above:

- **NOAA weather** — Sitka, Alaska and Death Valley, 2018 (simple and full variants)
- **USGS earthquakes** — 1-day, 7-day, and 30-day feeds of magnitude 1+ quakes
- **World fires** — 1-day and 7-day satellite fire detection data

## Running these

```bash
python3 -m venv .venv
source .venv/bin/activate
pip install matplotlib plotly

python mpl_squares.py
```

Matplotlib scripts open a window directly. Plotly scripts write an
interactive `.html` file into this folder — those are generated output and
are gitignored.
