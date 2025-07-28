---
permalink: /funding-history/
title: "Funding History"
author_profile: true
---

<div id="vis"></div>
<script>
    const spec = {
      "width": 600,
      "height": 400,
      "$schema": "https://vega.github.io/schema/vega-lite/v6.json",
      "description": "Funding history",
      "data": {
        "values": [
          {"date": "2022-04-01", "type": "Indirect fee", "value": 360},
          {"date": "2023-04-01", "type": "Indirect fee", "value": 990},
          {"date": "2024-04-01", "type": "Indirect fee", "value": 1350},
          {"date": "2025-04-01", "type": "Indirect fee", "value": 720},
          {"date": "2026-04-01", "type": "Indirect fee", "value": 450},
          {"date": "2016-04-01", "type": "JSPS DC1 Fellowship", "value": 1000},
          {"date": "2017-04-01", "type": "JSPS DC1 Fellowship", "value": 900},
          {"date": "2018-04-01", "type": "JSPS DC1 Fellowship", "value": 900},
          {"date": "2019-04-01", "type": "", "value": 0},
          {"date": "2020-04-01", "type": "", "value": 0},
          {"date": "2021-04-01", "type": "", "value": 0},
          {"date": "2022-04-01", "type": "JSPS PD Fellowship", "value": 1200},
          {"date": "2023-04-01", "type": "JSPS PD Fellowship", "value": 1100},
          {"date": "2024-04-01", "type": "JSPS PD Fellowship", "value": 1100},
          {"date": "2022-08-03", "type": "DGD Fellowship", "value": 200},
          {"date": "2022-12-16", "type": "Yazaki Travel Grant", "value": 321},
          {"date": "2023-04-01", "type": "JSPS ECS", "value": 2200},
          {"date": "2024-04-01", "type": "JSPS ECS", "value": 400},
          {"date": "2025-04-01", "type": "JSPS ECS", "value": 900},
          {"date": "2023-04-01", "type": "RIKEN SPDR Grant", "value": 1410.916},
          {"date": "2024-04-01", "type": "RIKEN SPDR Grant", "value": 1000},
          {"date": "2025-04-01", "type": "RIKEN SPDR Grant", "value": 1569.7},
          {"date": "2024-04-01", "type": "RIKEN Organoid Project", "value": 2000},
          {"date": "2024-04-01", "type": "JST ACT-X", "value": 3000},
          {"date": "2025-04-01", "type": "JST ACT-X", "value": 1500},
          {"date": "2026-04-01", "type": "JST ACT-X", "value": 1500},
          {"date": "2025-03-26", "type": "KatoKinen Travel Grant", "value": 300}
        ]
      },
      "params": [
        {
          "name": "highlight",
          "select": {
            "type": "point",
            "on": "mouseover"
          }
        }
      ],
      "mark": {
        "type": "bar",
        "stroke": "white",
        "strokeWidth": 1
      },
      "encoding": {
        "x": {
          "timeUnit": "year",
          "field": "date",
          "type": "ordinal",
          "title": "Fiscal year"
        },
        "y": {
          "field": "value",
          "type": "quantitative",
          "title": "Amount of grant (thousand yen)",
          "axis": {
            "titlePadding": 10
          }
        },
        "color": {
          "field": "type",
          "type": "nominal",
          "scale": {
            "domain": [
              "Indirect fee",
              "JSPS DC1 Fellowship",
              "JSPS PD Fellowship",
              "DGD Fellowship",
              "Yazaki Travel Grant",
              "JSPS ECS",
              "RIKEN SPDR Grant",
              "RIKEN Organoid Project",
              "JST ACT-X",
              "KatoKinen Travel Grant"
            ],
            "range": [
              "black",
              "#e7ba52",
              "mediumaquamarine",
              "gray",
              "silver",
              "olive",
              "turquoise",
              "khaki",
              "tomato",
              "lavender"
            ]
          },
          "title": "Grant name",
          "legend": {
            "orient": "bottom",
            "columns": 4
          }
        },
        "opacity": {
          "condition": {
            "param": "highlight",
            "value": 1.0
          },
          "value": 0.8
        },
        "tooltip": [
          {
            "field": "type",
            "type": "nominal",
            "title": "Grant Type"
          },
          {
            "field": "value",
            "type": "quantitative",
            "title": "Amount of grant (thousand yen)",
            "format": ",.1f"
          }
        ]
      }
    };
    vegaEmbed('#vis', spec);
</script>

<div id="vis"></div>
<script>
    const spec = {
  "$schema": "https://vega.github.io/schema/vega-lite/v6.json",
  "width": 1000,
  "height": 550,
  "config": {
    "legend": {"disable": true}
  },
  "data": {
    "name": "myCV",
    "url": "https://raw.githubusercontent.com/ishibaki/ishibaki.github.io/refs/heads/master/_data/career.csv"
  },
  "transform": [
    {
      "window": [{"op": "row_number", "as": "row_index"}]
    },
    {
      "joinaggregate": [
        {
          "op": "count",    // カウント操作
          "field": "*",     // 全行を対象
          "as": "content_num"
        }
      ],
      "groupby": ["section"]  // section ごとに集計
    },
    {
      "calculate": "datum.section === 'Institution' ? 0: datum.section === 'Education' ? 1: datum.section === 'Work History' ? 2: datum.section === 'Publications' ? 3: datum.section === 'Awards' ? 4: 5", "as": "sectionID"
    },
    {
      "calculate": "datum.section === 'Institution' ? 0: datum.section === 'Education' ? -(+datum.order_id % 2)+1 + 1: datum.section === 'Work History' ? -(+datum.order_id % 2)+1 + 3: datum.section === 'Publications' ? (+datum.order_id-1) + 5: datum.section === 'Awards' ? (+datum.order_id-1) + 19: (+datum.order_id-1) + 26", "as": "contentBase"
    },
    {
      "joinaggregate": [
        {
          "op":   "min",
          "field":"contentBase",
          "as":   "min_cBase"
        },
        {
          "op":   "max",
          "field":"contentBase",
          "as":   "max_cBase"
        }
      ],
      "groupby": ["section"]
    },
    {
      "calculate": "+datum.max_cBase + 1",
      "as":        "max_cBase"
    },
    {
      "calculate": "-(+datum.min_cBase + +datum.max_cBase)/2",
      "as":        "sectionBase"
    },
    {
      "calculate":
        "datum.end != null ? (datum.start + datum.end)/2 : datum.start",
      "as": "midpoint"
    },
    {
      "calculate": "datum.end === null ? -datum.contentBase - 0.6 : -datum.contentBase",
      "as": "y"
    },
    {
      "calculate":
        "-datum.contentBase-1",
      "as": "y2"
    },
    {
      "calculate":
        "(datum.y + datum.y2)/2-0.2",
      "as": "y_midpoint"
    }
  ],
  "layer": [
    {
      "description": "Section backgrounds",
      "transform": [
        {
          "aggregate": [
            {
              "op": "min", "field": "contentBase", "as": "bgY"
            },
            {
              "op": "max", "field": "contentBase", "as": "bgY2"
            },
          ],
          "groupby": ["section"]
        },
        {"calculate": "-datum.bgY", "as": "bgY"},
        {"calculate": "-datum.bgY2-1", "as": "bgY2"}
      ],
      "mark": {"type": "rect", "opacity": 0.5, "stroke": null, "strokeWidth": 1},
      "encoding": {
        "x": {"value": 0},
        "x2": {"value": 1000},
        "y": {"field": "bgY", "type": "quantitative"},
        "y2": {"field": "bgY2", "type": "quantitative"},
        "color": {"field": "section", "type": "nominal", "scale": {"range": ["#e1f5fe", "#f3e5f5", "#e8f5e8", "#fff3e0", "#ffebee"]}}
      }
    },
    {
      "description": "Section labels",
      "transform": [
        {"aggregate": [{"op": "mean", "field": "sectionBase", "as": "labelY"}], "groupby": ["section"]}
      ],
      "mark": {"type": "text", "align": "right", "baseline": "middle", "fontSize": 12, "fontWeight": "bold", "dx": -10},
      "encoding": {
        "x": {"value": 0},
        "y": {"field": "labelY", "type": "quantitative"},
        "text": {"field": "section", "type": "nominal"}
      }
    },
    {
      "description": "Period events (rectangles)",
      "transform": [{"filter": "datum.end != null"}],
      "mark": {"type": "rect", "stroke": "#000", "strokeWidth": 1},
      "encoding": {
        "x": {"field": "start", "type": "temporal", "title": "Year"},
        "x2": {"field": "end", "type": "temporal"},
        "y": {"field": "y", "type": "quantitative"},
        "y2": {"field": "y2", "type": "quantitative"},
        "color": {
          "field": "section",
          "type": "nominal",
          "scale": {"range": ["#90caf9", "#ce93d8", "#a5d6a7", "#ffcc02", "#ffab91"]}
        },
        "tooltip": [
          {"field": "title", "type": "nominal"},
          {"field": "start", "type": "temporal", "format": "%Y-%m-%d"},
          {"field": "end", "type": "temporal", "format": "%Y-%m-%d"}
        ]
      }
    },
    {
      "description": "Period event labels",
      "transform": [{"filter": "datum.end != null"}],
      "mark": {"type": "text", "align": "center", "baseline": "center", "fontSize": 9},
      "encoding": {
        "x": {"field": "midpoint", "type": "temporal"},
        "y": {"field": "y_midpoint", "type": "quantitative"},
        "text": {"field": "title", "type": "nominal"}
      }
    },
    {
      "description": "Point events, Publication",
      "transform": [{"filter": "datum.end === null && datum.section === 'Publications'"}],
      "mark": {"type": "point", "size": 100, "strokeWidth": 2},
      "encoding": {
        "x": {"field": "start", "type": "temporal"},
        "y": {"field": "y", "type": "quantitative"},
        "shape": {
          "condition": {"test": "datum.crit === 'true'", "value": "diamond"},
          "value": "circle"
        },
        "color": {
          "condition": {"test": "datum.crit", "value": "#f00"},
          "value": "#00f"
        },
        "stroke": {
          "condition": {"test": "datum.crit === 'true'", "value": "#f00"},
          "value": "#000"
        },
        "tooltip": [
          {"field": "title", "type": "nominal"},
          {"field": "start", "type": "temporal", "format": "%Y-%m-%d"},
          {"field": "url", "type":"nominal"}
        ]
      }
    },
    {
      "description": "Point event labels, Publication",
      "transform": [{"filter": "datum.end === null && datum.section === 'Publications'"}],
      "mark": {"type": "text", "align": "right", "baseline": "middle", "fontSize": 8, "dx": -8},
      "encoding": {
        "x": {"field": "start", "type": "temporal"},
        "y": {"field": "y", "type": "quantitative"},
        "text": {"field": "title", "type": "nominal"},
        "href": {"field": "url", "type": "nominal"}
      }
    },
    {
      "description": "Point events, Awards",
      "transform": [{"filter": "datum.end === null && datum.section === 'Awards'"}],
      "mark": {"type": "point", "size": 100, "strokeWidth": 2},
      "encoding": {
        "x": {"field": "start", "type": "temporal"},
        "y": {"field": "y", "type": "quantitative"},
        "shape": {
          "value": "square"
        },
        "stroke": {
          "value": "#000"
        },
        "tooltip": [
          {"field": "title", "type": "nominal"},
          {"field": "start", "type": "temporal", "format": "%Y-%m-%d"},
          {"field": "url"}
        ]
      }
    },
    {
      "description": "Point event labels, Awards",
      "transform": [{"filter": "datum.end === null && datum.section === 'Awards'"}],
      "mark": {"type": "text", "align": "right", "baseline": "middle", "fontSize": 8, "dx": -8},
      "encoding": {
        "x": {"field": "start", "type": "temporal"},
        "y": {"field": "y", "type": "quantitative"},
        "text": {"field": "title", "type": "nominal"},
        "href": {"field": "url", "type":"nominal"}
      }
    },
    {
      "description": "Point events, Fuding",
      "transform": [{"filter": "datum.end === null && datum.section === 'Funding'"}],
      "mark": {"type": "point", "size": 100, "strokeWidth": 2},
      "encoding": {
        "x": {"field": "start", "type": "temporal"},
        "y": {"field": "y", "type": "quantitative"},
        "shape": {
          "value": "triangle"
        },
        "stroke": {
          "value": "#000"
        },
        "tooltip": [
          {"field": "title", "type": "nominal"},
          {"field": "start", "type": "temporal", "format": "%Y-%m-%d"}
        ]
      }
    },
    {
      "description": "Point event labels, Funding",
      "transform": [{"filter": "datum.end === null && datum.section === 'Funding'"}],
      "mark": {"type": "text", "align": "right", "baseline": "middle", "fontSize": 8, "dx": -8},
      "encoding": {
        "x": {"field": "start", "type": "temporal"},
        "y": {"field": "y", "type": "quantitative"},
        "text": {"field": "title", "type": "nominal"}
      }
    },
  ],
  "encoding": {
    "x": {
      "field": "start",
      "type": "temporal",
      "scale": {
        "domain": ["2009-12-31", "2028-01-01"],
      },
    "axis": {"format": "%Y"}
    },
    "y": {
      "field": "y",
      "type": "quantitative",
      "scale": {
        "domain": {
          "data": "myCV",
          "field": "y"
        }
      },
      "axis": {
        "ticks": false,
        "labels": false,
        "domain": false,
        "title": false
      }
    },
  }
};
    vegaEmbed('#vis', spec);
</script>
