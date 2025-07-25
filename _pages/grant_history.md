---
permalink: /grant-history/
title: "Grant History"
author_profile: true
---

<!--
```mermaid
timeline
    title Grant Histoty
    section Ph.D. candidate
        2016 : JSPS DC1 Fellowship ¥1,000,000
        2017 : JSPS DC1 Fellowship ¥900,000
        2018 : JSPS DC1 Fellowship ¥900,000
    section Postdoc
        2022 : JSPS PD Fellowship ¥1,200,000 (+Indirect ¥360,000)
             : DGD Fellowshipship ¥200,000
             : Yazaki Travel Grant ¥321,000
        2023 : JSPS PD Fellowship ¥1,100,000 (+Indirect ¥330,000)
             : JSPS ECS Grant ¥2,200,000 (+Indirect ¥660,000)
             : RIKEN SPDR Grant ¥1,410,916
        2024 : JSPS PD Fellowship ¥1,100,000 (+Indirect ¥330,000)
             : JSPS ECS Grant ¥400,000 (+Indirect ¥120,000)
             : RIKEN SPDR Grant ¥1,000,000
             : RIKEN Organoid Project ¥2,000,000
             : JST ACT-X ¥3,000,000 (+Indirect ¥900,000)
        2025 : RIKEN SPDR Grant ¥1,569,700
             : JSPS ECS Grant ¥900,000 (+Indirect ¥270,000)
             : JST ACT-X ¥1,500,000 (+Indirect ¥450,000)
        2026 : JST ACT-X ¥1,500,000 (+Indirect ¥450,000)
```

```mermaid
xychart-beta
    title "Grant History"
    x-axis [2016, 2017, 2018, 2019, 2020, 2021, 2022, 2023, 2024, 2025, 2026]
    y-axis "Blue: Direct cost; Green: Indirect cost (in ¥k1,000)" 0 --> 8000
    bar [1000, 900, 900, 0, 0, 0, 1721, 4711, 7500, 3969, 1500]
    line [0, 0, 0, 0, 0, 0, 360, 990, 1350, 720, 450]
```
-->


<div id="vis"></div>
<script>
    const spec = {
        "width": 640,
        "height": 640,
        "$schema": "https://vega.github.io/schema/vega-lite/v5.json",
        "description": "Grant history.",
        "data": {
            "values": [
                {"date": "2022-04-01", "type": "Indirect fee", "value": 360000},
                {"date": "2023-04-01", "type": "Indirect fee", "value": 990000},
                {"date": "2024-04-01", "type": "Indirect fee", "value": 1350000},
                {"date": "2025-04-01", "type": "Indirect fee", "value": 720000},
                {"date": "2026-04-01", "type": "Indirect fee", "value": 450000},
                {"date": "2016-04-01", "type": "JSPS DC1 Fellowship", "value": 1000000},
                {"date": "2017-04-01", "type": "JSPS DC1 Fellowship", "value": 900000},
                {"date": "2018-04-01", "type": "JSPS DC1 Fellowship", "value": 900000},
                {"date": "2019-04-01", "type": "", "value": 0},
                {"date": "2020-04-01", "type": "", "value": 0},
                {"date": "2021-04-01", "type": "", "value": 0},
                {"date": "2022-04-01", "type": "JSPS PD Fellowship", "value": 1200000},
                {"date": "2023-04-01", "type": "JSPS PD Fellowship", "value": 1100000},
                {"date": "2024-04-01", "type": "JSPS PD Fellowship", "value": 1100000},
                {"date": "2022-08-03", "type": "DGD Fellowship", "value": 200000},
                {"date": "2022-12-16", "type": "Yazaki Travel Grant", "value": 321000},
                {"date": "2023-04-01", "type": "JSPS ECS", "value": 2200000},
                {"date": "2024-04-01", "type": "JSPS ECS", "value": 400000},
                {"date": "2025-04-01", "type": "JSPS ECS", "value": 900000},
                {"date": "2023-04-01", "type": "RIKEN SPDR Grant", "value": 1410916},
                {"date": "2024-04-01", "type": "RIKEN SPDR Grant", "value": 1000000},
                {"date": "2025-04-01", "type": "RIKEN SPDR Grant", "value": 1569700},
                {"date": "2024-04-01", "type": "RIKEN Organoid Project", "value": 2000000},
                {"date": "2024-04-01", "type": "JST ACT-X", "value": 3000000},
                {"date": "2025-04-01", "type": "JST ACT-X", "value": 1500000},
                {"date": "2026-04-01", "type": "JST ACT-X", "value": 1500000},
                {"date": "2025-03-26", "type": "KatoKinen Travel Grant", "value": 300000}
            ]
        },
        "mark": "bar",
        "encoding": {
          "x": {
            "timeUnit": "year",
            "field": "date",
            "type": "ordinal",
            "title": "Year"
          },
          "y": {
            "field": "value",
            "type": "quantitative",
            "title": "Grant (yen)"
          },
          "color": {
            "field": "type",
            "type": "nominal",
            "scale": {
              "domain": ["Indirect fee",
                         "JSPS DC1 Fellowship", "JSPS PD Fellowship",
                         "DGD Fellowship", "Yazaki Travel Grant",
                         "JSPS ECS", "RIKEN SPDR Grant",
                         "RIKEN Organoid Project",
                         "JST ACT-X",
                         "KatoKinen Travel Grant"],
              "range": ["black",
                        "#e7ba52", "mediumaquamarine",
                        "gray", "silver",
                        "olive", "turquoise",
                        "khaki",
                        "tomato",
                        "lavender"]
            },
            "title": "Grant name"
          }
        }
    };
    vegaEmbed('#vis', spec);
</script>
