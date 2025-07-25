---
permalink: /grant-history/
title: "Grant History"
author_profile: true
---

<div id="vis"></div>
<script>
    const spec = {
        "width": 720,
        "height": 512,
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
