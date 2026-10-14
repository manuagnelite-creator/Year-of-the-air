# A Year of Air

A scrolling, interactive particle story about India's air in 2021. Every dot is one day in one city: 171 cities × 365 days = 62,415 particles. As you scroll, the dots regroup into a 3D cloud, three spheres, a grid of city discs, a map, and a 3D skyline of smog. A second layer overlays a 2024 study on indoor smoke, sleep and cognition among older adults.

## Run it

It is a single static file with no build step. Open `index.html` in a browser, or serve the folder:

```
python3 -m http.server
```

To publish with GitHub Pages: push this repo, then go to **Settings → Pages → Deploy from a branch → main / root**.

## Data

| File | What it is |
|---|---|
| `data/aqi-days-2021.json` | The original dataset: good days (AQI 0–200) and bad days (AQI > 200) per city in 2021. |
| `data/cities.csv` | The same counts, plus unrecorded days and the approximate coordinates used for the map. |
| `data/study-state-bands.csv` | State bands (1–4) for cooking smoke, sleep problems and cognition, read from Fig. 2 of the study below. |

AQI bands follow India's National AQI: 0–200 covers Good, Satisfactory and Moderate; above 200 covers Poor, Very Poor and Severe. Vijayawada and Loni Dehat have no data.

## Notes and limits

- City coordinates were entered by hand and are approximate (about ±0.3°). Map discs are pushed apart so they don't overlap.
- The study does not publish per-state values. Its bands were read by eye from its maps. Delhi, Chandigarh and Puducherry are too small to read, and the northeast is the least certain.
- The two datasets differ in year (2017–18 vs 2021), unit (households vs city monitors) and kind of air (indoor vs outdoor). The overlay shows shared geography, not cause.

## Source

Shaw S, Kundu S, Chattopadhyay A, Rao S. Indoor air pollution and cognitive function among older adults in India: a multiple mediation approach through depression and sleep disorders. *BMC Geriatrics* 2024;24:81. https://doi.org/10.1186/s12877-024-04662-6 (CC BY 4.0)

## Tech

Plain HTML, CSS and Canvas 2D, with no libraries. Fonts load from Google Fonts: Bricolage Grotesque, Source Serif 4 and IBM Plex Mono.
