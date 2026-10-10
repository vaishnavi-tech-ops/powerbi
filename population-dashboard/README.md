# Population demographics dashboard

An interactive dashboard built from `data/Population_Demographics_Analysis_Dataset.csv` (99 records, 2000 to 2024).

Open `index.html` in any browser. No install or build step is needed. The data is embedded in the page, and the charts load Chart.js from a CDN, so you need an internet connection the first time.

## What's on the dashboard

**Filters:** Year from, Year to, Region, State, plus a reset button.

**5 KPIs**
1. Total population
2. Urban population % (urban / (urban + rural))
3. Average literacy rate
4. Average growth rate
5. Natural increase (average birth rate minus average death rate)

**6 charts**
1. Population by year (line)
2. Population by region (bar)
3. Urban vs rural population (donut)
4. Birth rate vs death rate by year (line)
5. Average literacy rate by state (bar)
6. Density vs growth rate (scatter)

All KPIs and charts update when you change a filter.

## Publish it with GitHub Pages

1. Push this folder to a GitHub repository.
2. Open **Settings → Pages**.
3. Under **Build and deployment**, choose **Deploy from a branch**, select `main` and `/ (root)`, then save.
4. After a minute the dashboard is live at `https://<your-username>.github.io/<repo-name>/`.

## Project structure

```
.
├── index.html                  Dashboard (data embedded)
├── data/
│   └── Population_Demographics_Analysis_Dataset.csv
├── docs/
│   └── dax_measures.md         Matching Power BI measures
├── README.md
└── .gitignore
```

## Data notes

- Blank Region, State or City values appear as "Unknown".
- Blank numeric values are ignored in sums and averages.
- Urban + Rural does not equal Population in the source rows, so urban share uses urban / (urban + rural).
- Region, State and City are independent columns in the data, so they don't form a real geographic hierarchy.
- There are no records for 2004.

## Updating the data

If you change the CSV, regenerate the embedded data in `index.html` (the `DATA` array near the bottom of the file), or load the CSV with `fetch` and serve the folder through GitHub Pages.
