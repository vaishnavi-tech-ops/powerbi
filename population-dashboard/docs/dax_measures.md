# Power BI measures

Use these if you also want to build this dashboard in Power BI Desktop. Replace `Population_Data` with your table name.

```DAX
Total Population = SUM(Population_Data[Population])

Urban % =
DIVIDE(
    SUM(Population_Data[Urban_Population]),
    SUM(Population_Data[Urban_Population]) + SUM(Population_Data[Rural_Population])
)

Avg Literacy = AVERAGE(Population_Data[Literacy_Rate])

Avg Growth Rate = AVERAGE(Population_Data[Growth_Rate])

Avg Birth Rate = AVERAGE(Population_Data[Birth_Rate])

Avg Death Rate = AVERAGE(Population_Data[Death_Rate])

Natural Increase = [Avg Birth Rate] - [Avg Death Rate]
```

## Visual setup

| # | Visual | Axis / category | Values |
|---|--------|-----------------|--------|
| 1 | Line chart | Year | Total Population |
| 2 | Clustered bar | Region | Total Population |
| 3 | Donut | Urban/Rural helper table | Urban Rural Value |
| 4 | Line chart | Year | Avg Birth Rate, Avg Death Rate |
| 5 | Clustered bar | State | Avg Literacy |
| 6 | Scatter | X: Density_per_km2, Y: Growth_Rate | Details: City |

Slicers: Year, Region, State.

## Expected values with no filters

Total Population 936.8M, Urban % 49.4%, Avg Literacy 78.3, Avg Growth Rate 1.95, Natural Increase 10.0.
