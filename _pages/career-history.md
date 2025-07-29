---
permalink: /career-history/
title: "Career History"
author_profile: true
---

<div id="vis"></div>

<script src="https://cdn.jsdelivr.net/npm/vega@5"></script>
<script src="https://cdn.jsdelivr.net/npm/vega-lite@5"></script>
<script src="https://cdn.jsdelivr.net/npm/vega-embed@6"></script>

<script type="text/javascript>
    console.log('▶︎ career-history script start');   // ① これが出るか？
    console.log('vegaEmbed:', typeof vegaEmbed);     // ② vegaEmbed が定義されているか？
    const spec = {
  "$schema": "https://vega.github.io/schema/vega-lite/v6.json",
  "width": 1000,
  "height": 550,
  "config": {
    "legend": {"disable": true}
  },
  "data": {
    "name": "myCV",
    "values": [
      {
          "order_id": 1,
          "section": "Institution",
          "title": "Osaka University",
          "start": "2010-04-01",
          "end": "2019-03-31",
          "crit": false,
          "url": ""
      },
      {
          "order_id": 2,
          "section": "Institution",
          "title": "Kyoto University",
          "start": "2019-04-01",
          "end": "2021-04-30",
          "crit": false,
          "url": ""
      },
      {
          "order_id": 3,
          "section": "Institution",
          "title": "RIKEN BDR",
          "start": "2021-05-01",
          "end": "2026-03-31",
          "crit": false,
          "url": ""
      },
      {
          "order_id": 1,
          "section": "Education",
          "title": "B.S.",
          "start": "2010-04-01",
          "end": "2014-03-25",
          "crit": false,
          "url": ""
      },
      {
          "order_id": 2,
          "section": "Education",
          "title": "M.S.",
          "start": "2014-04-01",
          "end": "2016-03-28",
          "crit": false,
          "url": ""
      },
      {
          "order_id": 3,
          "section": "Education",
          "title": "Ph.D.",
          "start": "2016-04-01",
          "end": "2019-03-25",
          "crit": false,
          "url": ""
      },
      {
          "order_id": 1,
          "section": "Work History",
          "title": "Lab tech.",
          "start": "2011-04-01",
          "end": "2012-03-31",
          "crit": false,
          "url": ""
      },
      {
          "order_id": 2,
          "section": "Work History",
          "title": "JSPS DC1",
          "start": "2016-04-01",
          "end": "2019-03-31",
          "crit": false,
          "url": ""
      },
      {
          "order_id": 3,
          "section": "Work History",
          "title": "Post-doc",
          "start": "2019-04-01",
          "end": "2021-04-30",
          "crit": false,
          "url": ""
      },
      {
          "order_id": 4,
          "section": "Work History",
          "title": "Researcher",
          "start": "2021-05-01",
          "end": "2022-03-31",
          "crit": false,
          "url": ""
      },
      {
          "order_id": 5,
          "section": "Work History",
          "title": "JSPS PD",
          "start": "2022-04-01",
          "end": "2023-03-31",
          "crit": false,
          "url": ""
      },
      {
          "order_id": 6,
          "section": "Work History",
          "title": "SPDR",
          "start": "2023-04-01",
          "end": "2026-03-31",
          "crit": false,
          "url": ""
      },
      {
          "order_id": 1,
          "section": "Publications",
          "title": "Nakayama et al. (2014) BMC Genet.",
          "start": "2014-04-16",
          "end": "",
          "crit": false,
          "url": "https://doi.org/10.1186/1471-2156-15-46"
      },
      {
          "order_id": 2,
          "section": "Publications",
          "title": "Inaki et al. (2018) eLife",
          "start": "2018-06-12",
          "end": "",
          "crit": false,
          "url": "https://doi.org/10.7554/eLife.32506"
      },
      {
          "order_id": 3,
          "section": "Publications",
          "title": "Ishibashi et al. (2019) Genes Cells",
          "start": "2019-01-09",
          "end": "",
          "crit": true,
          "url": "https://doi.org/10.1111/gtc.12669"
      },
      {
          "order_id": 4,
          "section": "Publications",
          "title": "Utsunomiya et al. (2019) Symmetry",
          "start": "2019-04-08",
          "end": "",
          "crit": false,
          "url": "https://doi.org/10.3390/sym11040505"
      },
      {
          "order_id": 5,
          "section": "Publications",
          "title": "Doysabas et al. (2020) J. Vet. Med. Sci.",
          "start": "2020-02-12",
          "end": "",
          "crit": false,
          "url": "https://doi.org/10.1292/jvms.20-0021"
      },
      {
          "order_id": 6,
          "section": "Publications",
          "title": "Takata et al. (2020) Insectes Soc.",
          "start": "2020-09-22",
          "end": "",
          "crit": false,
          "url": "https://doi.org/10.1007/s00040-020-00785-2"
      },
      {
          "order_id": 7,
          "section": "Publications",
          "title": "Ishibashi et al. (2020) Symmetry",
          "start": "2020-12-02",
          "end": "",
          "crit": true,
          "url": "https://doi.org/10.3390/sym12121991"
      },
      {
          "order_id": 8,
          "section": "Publications",
          "title": "Ishibashi & Matsuno (2022) microPubl. Biol.",
          "start": "2022-03-18",
          "end": "",
          "crit": true,
          "url": "https://doi.org/10.17912/micropub.biology.000526"
      },
      {
          "order_id": 9,
          "section": "Publications",
          "title": "Lai et al. (2023) Development",
          "start": "2023-03-02",
          "end": "",
          "crit": false,
          "url": "https://doi.org/10.1242/dev.201224"
      },
      {
          "order_id": 10,
          "section": "Publications",
          "title": "Ishibashi et al. (2023) Dev. Growth Differ.",
          "start": "2023-06-25",
          "end": "",
          "crit": true,
          "url": "https://doi.org/10.1111/dgd.12873"
      },
      {
          "order_id": 11,
          "section": "Publications",
          "title": "Hondo et al. (2024) Virus Res.",
          "start": "2024-01-02",
          "end": "",
          "crit": false,
          "url": "https://doi.org/10.1016/j.virusres.2023.199248"
      },
      {
          "order_id": 12,
          "section": "Publications",
          "title": "Katoh et al. (2024) Microscopy",
          "start": "2024-06-01",
          "end": "",
          "crit": true,
          "url": "https://doi.org/10.1093/jmicro/dfad059"
      },
      {
          "order_id": 13,
          "section": "Publications",
          "title": "Takata et al. (2025) PNAS",
          "start": "2025-06-13",
          "end": "",
          "crit": false,
          "url": "https://doi.org/10.1073/pnas.2509506122"
      },
      {
          "order_id": 14,
          "section": "Publications",
          "title": "Yamamoto et al. (2025) eLife",
          "start": "2025-07-08",
          "end": "",
          "crit": true,
          "url": "https://doi.org/10.7554/eLife.102296"
      },
      {
          "order_id": 1,
          "section": "Awards",
          "title": "Best Presentation Award",
          "start": "2015-12-20",
          "end": "",
          "crit": false,
          "url": "https://ishibaki.github.io/awards/2015-Dec-Best-Presentation-Award"
      },
      {
          "order_id": 2,
          "section": "Awards",
          "title": "Best Popularity Award & Excellent Award",
          "start": "2016-09-25",
          "end": "",
          "crit": false,
          "url": "https://ishibaki.github.io/awards/2016-Nov-Excellent-Award"
      },
      {
          "order_id": 3,
          "section": "Awards",
          "title": "1st Place for Outstanding Presentation",
          "start": "2017-11-01",
          "end": "",
          "crit": false,
          "url": "https://ishibaki.github.io/awards/2017-Oct-First-Place-for-Outstanding-Presentation"
      },
      {
          "order_id": 4,
          "section": "Awards",
          "title": "Outstanding Poster Presentation Award",
          "start": "2023-06-15",
          "end": "",
          "crit": false,
          "url": "https://ishibaki.github.io/awards/2023-Jun-Outstanding-Poster-Presentation"
      },
      {
          "order_id": 5,
          "section": "Awards",
          "title": "Young Scientist Award for Presentation",
          "start": "2023-06-29",
          "end": "",
          "crit": false,
          "url": "https://ishibaki.github.io/awards/2023-June-PresentationAward-JSCB"
      },
      {
          "order_id": 6,
          "section": "Awards",
          "title": "Best Science Pitch Award",
          "start": "2023-12-08",
          "end": "",
          "crit": false,
          "url": "https://ishibaki.github.io/awards/2023-December-SciPitchAward-MBSJ"
      },
      {
          "order_id": 7,
          "section": "Awards",
          "title": "DGD Young Investigator Paper Award",
          "start": "2024-06-21",
          "end": "",
          "crit": false,
          "url": "https://ishibaki.github.io/awards/2024-Jun-YoungInvestigatorPaperAward-JSDB"
      },
      {
          "order_id": 1,
          "section": "Funding",
          "title": "JSPS Fellows (DC1)",
          "start": "2016-04-22",
          "end": "2019-03-31",
          "crit": false,
          "url": ""
      },
      {
          "order_id": 2,
          "section": "Funding",
          "title": "JSPS Fellows (PD)",
          "start": "2022-04-22",
          "end": "2025-03-31",
          "crit": false,
          "url": ""
      },
      {
          "order_id": 3,
          "section": "Funding",
          "title": "DGD Fellowship",
          "start": "2022-11-04",
          "end": "",
          "crit": false,
          "url": ""
      },
      {
          "order_id": 4,
          "section": "Funding",
          "title": "Yazaki Fellowship",
          "start": "2022-11-04",
          "end": "",
          "crit": false,
          "url": ""
      },
      {
          "order_id": 5,
          "section": "Funding",
          "title": "JSPS Grant-in-Aid for ECS",
          "start": "2023-04-01",
          "end": "2026-03-31",
          "crit": false,
          "url": ""
      },
      {
          "order_id": 6,
          "section": "Funding",
          "title": "RIKEN Organoid PJ",
          "start": "2024-04-01",
          "end": "2025-03-31",
          "crit": false,
          "url": ""
      },
      {
          "order_id": 7,
          "section": "Funding",
          "title": "ACT-X",
          "start": "2024-10-01",
          "end": "2027-03-31",
          "crit": false,
          "url": ""
      },
      {
          "order_id": 8,
          "section": "Funding",
          "title": "Kato Kinen Fellowhip",
          "start": "2025-04-03",
          "end": "",
          "crit": false,
          "url": ""
      }
    ]
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
    vegaEmbed('#vis', spec, {renderer:'canvas', actions:false});
</script>
