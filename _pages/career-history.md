---
permalink: /career-history/
title: "Career History"
author_profile: true
---

<div id="vis" style="width: 100%; height: 600px;"></div>

<script type="text/javascript">
document.addEventListener('DOMContentLoaded', function() {
    console.log('▶︎ career-history script start');
    console.log('vegaEmbed:', typeof vegaEmbed);
    
    const spec = {
        "$schema": "https://vega.github.io/schema/vega-lite/v6.json",
        "width": 1000,
        "height": 550,
        "padding": {"left": 20, "top": 10, "right": 10, "bottom": 10},
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
                        "op": "count",
                        "field": "*",
                        "as": "content_num"
                    }
                ],
                "groupby": ["section"]
            },
            {
                "calculate": "datum.section === 'Institution' ? 0: datum.section === 'Education' ? 1: datum.section === 'Work History' ? 2: datum.section === 'Publications' ? 3: datum.section === 'Awards' ? 4: 5", 
                "as": "sectionID"
            },
            {
                "calculate": "datum.section === 'Institution' ? 0: datum.section === 'Education' ? -(+datum.order_id % 2)+1 + 1: datum.section === 'Work History' ? -(+datum.order_id % 2)+1 + 3: datum.section === 'Publications' ? (+datum.order_id-1) + 5: datum.section === 'Awards' ? (+datum.order_id-1) + 19: (+datum.order_id-1) + 26", 
                "as": "contentBase"
            },
            {
                "joinaggregate": [
                    {
                        "op": "min",
                        "field": "contentBase",
                        "as": "min_cBase"
                    },
                    {
                        "op": "max",
                        "field": "contentBase",
                        "as": "max_cBase"
                    }
                ],
                "groupby": ["section"]
            },
            {
                "calculate": "+datum.max_cBase + 1",
                "as": "max_cBase"
            },
            {
                "calculate": "-(+datum.min_cBase + +datum.max_cBase)/2",
                "as": "sectionBase"
            },
            {
                "calculate": "datum.end != null && datum.end != '' ? (datum.start + datum.end)/2 : datum.start",
                "as": "midpoint"
            },
            {
                "calculate": "(datum.end === null || datum.end === '') ? -datum.contentBase - 0.6 : -datum.contentBase",
                "as": "y"
            },
            {
                "calculate": "-datum.contentBase-1",
                "as": "y2"
            },
            {
                "calculate": "(datum.y + datum.y2)/2-0.2",
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
                            }
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
                "transform": [{"filter": "datum.end != null && datum.end != ''"}],
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
                "transform": [{"filter": "datum.end != null && datum.end != ''"}],
                "mark": {"type": "text", "align": "center", "baseline": "center", "fontSize": 9},
                "encoding": {
                    "x": {"field": "midpoint", "type": "temporal"},
                    "y": {"field": "y_midpoint", "type": "quantitative"},
                    "text": {"field": "title", "type": "nominal"}
                }
            },
            {
                "description": "Point events, Publication",
                "transform": [{"filter": "(datum.end === null || datum.end === '') && datum.section === 'Publications'"}],
                "mark": {"type": "point", "size": 100, "strokeWidth": 2},
                "encoding": {
                    "x": {"field": "start", "type": "temporal"},
                    "y": {"field": "y", "type": "quantitative"},
                    "shape": {
                        "condition": {"test": "datum.crit === 'true'", "value": "diamond"},
                        "value": "circle"
                    },
                    "color": {
                        "condition": {"test": "datum.crit === 'true'", "value": "#f00"},
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
                "transform": [{"filter": "(datum.end === null || datum.end === '') && datum.section === 'Publications'"}],
                "mark": {"type": "text", "align": "right", "baseline": "middle", "fontSize": 8, "dx": -8},
                "encoding": {
                    "x": {"field": "start", "type": "temporal"},
                    "y": {"field": "y", "type": "quantitative"},
                    "text": {"field": "title", "type": "nominal"},
                    "href": {
                        "condition": {
                            "test": "datum.url != null && datum.url != ''",
                            "field": "url",
                            "type": "nominal"
                        }
                    }
                }
            },
            {
                "description": "Point events, Awards",
                "transform": [{"filter": "(datum.end === null || datum.end === '') && datum.section === 'Awards'"}],
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
                "transform": [{"filter": "(datum.end === null || datum.end === '') && datum.section === 'Awards'"}],
                "mark": {"type": "text", "align": "right", "baseline": "middle", "fontSize": 8, "dx": -8},
                "encoding": {
                    "x": {"field": "start", "type": "temporal"},
                    "y": {"field": "y", "type": "quantitative"},
                    "text": {"field": "title", "type": "nominal"},
                    "href": {
                        "condition": {
                            "test": "datum.url != null && datum.url != ''",
                            "field": "url",
                            "type": "nominal"
                        }
                    }
                }
            },
            {
                "description": "Point events, Funding",
                "transform": [{"filter": "(datum.end === null || datum.end === '') && datum.section === 'Funding'"}],
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
                "transform": [{"filter": "(datum.end === null || datum.end === '') && datum.section === 'Funding'"}],
                "mark": {"type": "text", "align": "right", "baseline": "middle", "fontSize": 8, "dx": -8},
                "encoding": {
                    "x": {"field": "start", "type": "temporal"},
                    "y": {"field": "y", "type": "quantitative"},
                    "text": {"field": "title", "type": "nominal"}
                }
            }
        ],
        "encoding": {
            "x": {
                "field": "start",
                "type": "temporal",
                "scale": {
                    "domain": ["2009-12-31", "2028-01-01"]
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
            }
        }
    };
    
    vegaEmbed('#vis', spec, {
        renderer: 'svg', 
        actions: false
    }).then(function(result) {
        console.log('✅ Vega-Lite chart rendered successfully');
        setTimeout(() => {
            try {
                const container = result.view.container();
                const svg = container.querySelector('svg');
                
                if (svg) {
                    const links = svg.querySelectorAll('a[href], a[xlink\\:href]');
                    console.log('Links found:', links.length);
                    
                    // 属性設定とクリックイベント両方
                    links.forEach((link, index) => {
                        // 属性設定
                        link.setAttribute('target', '_blank');
                        link.setAttribute('rel', 'noopener noreferrer');
                        
                        // クリックイベントで確実に新しいタブで開く
                        link.addEventListener('click', function(e) {
                            e.preventDefault();
                            const url = this.getAttribute('href') || this.getAttribute('xlink:href');
                            if (url) {
                                window.open(url, '_blank', 'noopener,noreferrer');
                            }
                        });
                    });
                    console.log(`✅ ${links.length} links set to open in new tab`);
                }
            } catch (error) {
                console.error('SVG processing error:', error);
            }
        }, 200);
    }).catch(function(error) {
        console.error('❌ Error rendering chart:', error);
    });
});
</script>
