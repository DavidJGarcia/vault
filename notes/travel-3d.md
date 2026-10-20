# Travel time splits, in 3D

Built Tuesday, October 20, 2026, from "Build me an interactive 3D graph of our travel time
splits where y is the length of travel time, direction we went is color-coded, x is
clustering by the time that we started, and z is clustering by day of the week."

The data is the ten `route_time` records - every run timed between Tuesday September 15 and
Tuesday October 20, 2026, and nothing from anywhere else. Rebuild it from
`records --kind route_time` when there are more.

## How to open it

The vault is Markdown only, so the graph lives here as its source. Copy the block under
**The file** at the bottom, save it as `travel-3d.html`, and open it in any browser. It
loads Plotly from a CDN, so it wants an internet connection the first time; it needs
nothing else, and no data leaves the file.

Drag to rotate, scroll to zoom, hover a point for its date and its times. The legend
switches a direction off. The drop lines (on by default) run from each point down to the
floor, which is what makes a 3D scatter readable - without them you cannot tell how far
back a point sits. The same ten runs are under the graph as a table, so nothing is
reachable only by hovering.

## The axes

| Axis | What it carries |
|---|---|
| **y**, vertical | the drive itself, 4:00 at the floor to 11:00 at the top |
| **colour** | the way taken at the fork: left is blue circles, right is orange diamonds |
| **x**, across | the time the drive started, 07:05 to 07:14 |
| **z**, into the screen | the day of the week, Monday to Friday |

Your y is drawn vertical and your z into the screen, which is how the letters read on a 2D
chart even though a 3D plotting library calls the vertical axis z. Friday is on the axis
and empty: you have never timed one.

**The start time is derived, and you never said it.** Each note gives the direction and the
length, and the ring stamps the moment you spoke, which is just after you arrived. So the
start is that stamp minus the drive. It is right to the second if you spoke as you pulled
up, and a little early if you waited a moment first. Everything below about start times
rests on that.

## The ten runs

| Date | Day | Started | Drive | Way | Start cluster |
|---|---|---|---|---|---|
| Sep 15 | Tue | 07:06:32 | 5:45 | left | early |
| Sep 28 | Mon | 07:08:03 | 5:20 | right | early |
| Sep 29 | Tue | 07:06:32 | 6:13 | left | early |
| Oct 1 | Thu | 07:05:51 | 7:22 | right | early |
| Oct 5 | Mon | 07:11:45 | 8:44 | left | late |
| Oct 6 | Tue | 07:07:56 | 6:02 | right | early |
| Oct 7 | Wed | 07:07:45 | 4:00 | left | early |
| Oct 8 | Thu | 07:06:38 | 5:53 | right | early |
| Oct 19 | Mon | 07:12:48 | 11:00 | left | late |
| Oct 20 | Tue | 07:09:52 | 5:22 | right | middle |

The clusters are the gaps in the start times, not round numbers: seven runs start between
07:05:51 and 07:08:03, then a gap of 1m 49s to Oct 20 alone at 07:09:52, then a gap of
1m 53s to the two late ones, 07:11:45 and 07:12:48.

## What the graph shows

**Start time is the strongest thing in it.** The early cluster averages 5:48, Oct 20 alone
is 5:22, and the two late starts average 9:52. Four extra minutes of drive for four extra
minutes in the house. As a correlation across all ten it is r = 0.68, which sounds firmer
than it is: drop Oct 19 and it falls to r = 0.34, so two mornings are carrying most of it.
Two more late starts would settle it either way.

**And it changes the answer to which way is faster.** On the raw averages right leads, 6:00
over five runs against 7:08 for left. But both late starts were left turns, and both were
Mondays. Hold the start time still and it reverses:

| | left | right |
|---|---|---|
| early starts, before 07:09 | **5:19** over 3 | 6:09 over 4 |
| late starts | 9:52 over 2 | never |
| all runs | 7:08 over 5 | 6:00 over 5 |

Left owns the fastest run on record (4:00, Oct 7) and both of the slowest (8:44 and 11:00).
Right has never been worse than 7:22 and never better than 5:20: it is the steadier way,
and on the evidence here it is not the faster one. The `vs_other_direction` note on each
`route_time` record compares raw averages and so says the opposite; this is the same data
with the late mornings separated out.

**Day of week is mostly those same two mornings again.** Monday averages 8:21 over three,
Tuesday 5:51 over four, Wednesday 4:00 over one, Thursday 6:38 over two. But two of the
three Mondays are the two late starts, and the third Monday, Sep 28 started at 07:08, was
5:20, the second-fastest run on record. So Monday is not slow; leaving at 07:12 on a Monday
is. Nothing has ever been timed on a Friday.

**What would settle it:** a left run and a right run started inside the same minute, and a
late-start right turn. Right has never once started after 07:09:52, so the two directions
have never been compared on equal footing.

## The file

Save everything between the fences as `travel-3d.html`.

```html
<!doctype html>
<html lang="en">
<head>
<meta charset="utf-8">
<meta name="viewport" content="width=device-width,initial-scale=1">
<title>Travel time splits, in 3D</title>
<script src="https://cdn.plot.ly/plotly-2.35.2.min.js" charset="utf-8"></script>
<style>
  :root { color-scheme: light dark; }
  .viz-root {
    --surface-1: #fcfcfb;
    --surface-2: #f3f3f1;
    --pane:      #f7f7f5;
    --grid:      #d9d9d4;
    --text-1:    #0b0b0b;
    --text-2:    #52514e;
    --left:      #2a78d6;
    --right:     #eb6834;
  }
  @media (prefers-color-scheme: dark) {
    :root:where(:not([data-theme="light"])) .viz-root {
      --surface-1: #1a1a19;
      --surface-2: #22272f;
      --pane:      #202020;
      --grid:      #3a3a38;
      --text-1:    #ffffff;
      --text-2:    #c3c2b7;
      --left:      #3987e5;
      --right:     #d95926;
    }
  }
  :root[data-theme="dark"] .viz-root {
    --surface-1: #1a1a19;
    --surface-2: #22272f;
    --pane:      #202020;
    --grid:      #3a3a38;
    --text-1:    #ffffff;
    --text-2:    #c3c2b7;
    --left:      #3987e5;
    --right:     #d95926;
  }
  html, body { margin: 0; }
  body {
    font: 15px/1.5 -apple-system, "Segoe UI", Roboto, Helvetica, Arial, sans-serif;
    background: var(--surface-1);
    color: var(--text-1);
  }
  .viz-root { max-width: 60rem; margin: 0 auto; padding: 1.5rem 1.25rem 3rem; background: var(--surface-1); }
  h1 { font-size: 1.35rem; margin: 0 0 .25rem; letter-spacing: -.01em; }
  p.sub { margin: 0 0 1.25rem; color: var(--text-2); font-size: .9rem; max-width: 46rem; }
  .controls { display: flex; flex-wrap: wrap; gap: .9rem; align-items: center; margin: 0 0 .75rem; font-size: .85rem; }
  .controls button, .controls label {
    font: inherit; color: var(--text-2); background: var(--surface-2);
    border: 1px solid var(--grid); border-radius: 5px; padding: .3rem .6rem; cursor: pointer;
  }
  .controls label { display: inline-flex; align-items: center; gap: .4rem; }
  .controls button:hover, .controls label:hover { color: var(--text-1); }
  .controls input { accent-color: var(--left); margin: 0; }
  #plot { width: 100%; height: 34rem; }
  h2 { font-size: 1rem; margin: 2rem 0 .5rem; }
  table { border-collapse: collapse; width: 100%; font-size: .85rem; }
  th, td { text-align: left; padding: .35rem .6rem; border-bottom: 1px solid var(--grid); }
  th { color: var(--text-2); font-weight: 600; }
  td.num, th.num { text-align: right; font-variant-numeric: tabular-nums; }
  .key { display: inline-block; width: .6rem; height: .6rem; border-radius: 50%; margin-right: .45rem; }
  .key.right { border-radius: 1px; transform: rotate(45deg); }
  tfoot td { color: var(--text-2); border-bottom: 0; padding-top: .7rem; }
  noscript { color: var(--text-2); }
</style>
</head>
<body>
<div class="viz-root">
  <h1>Travel time splits</h1>
  <p class="sub">Ten timed runs, Sep 15 to Oct 20 2026. Vertical is the drive, across is
  when it started, into the screen is the day of the week, colour is the way taken at the
  fork. Start times are derived: the moment reported, minus the drive.</p>

  <div class="controls">
    <label><input type="checkbox" id="stems" checked> Drop lines</label>
    <button id="reset" type="button">Reset view</button>
    <button id="theme" type="button">Dark / light</button>
  </div>

  <div id="plot" role="img" aria-label="Three-dimensional scatter of ten timed drives: drive length against start time and day of the week, coloured by direction. Every value is in the table below."></div>
  <noscript>This graph needs JavaScript. The table below holds every value in it.</noscript>

  <h2>The ten runs</h2>
  <table id="tbl">
    <thead><tr><th>Date</th><th>Day</th><th>Started</th><th class="num">Drive</th><th>Way</th><th>Start cluster</th></tr></thead>
    <tbody></tbody>
    <tfoot><tr><td colspan="6">Early starts average 5:48; Oct 20 alone 5:22; the two late
    starts 9:52. Before 07:09, left averages 5:19 against 6:09 for right.</td></tr></tfoot>
  </table>
</div>

<script>
(function () {
  "use strict";

  // Started is the reported moment minus the duration; see travel-3d.md. startMin is
  // minutes past 07:00, day is 1 for Monday.
  var RUNS = [
    { date: "2026-09-15", dayName: "Tue", day: 2, dir: "left",  dur: 345, startMin:  6.533, started: "07:06:32", cluster: "early"  },
    { date: "2026-09-28", dayName: "Mon", day: 1, dir: "right", dur: 320, startMin:  8.050, started: "07:08:03", cluster: "early"  },
    { date: "2026-09-29", dayName: "Tue", day: 2, dir: "left",  dur: 373, startMin:  6.533, started: "07:06:32", cluster: "early"  },
    { date: "2026-10-01", dayName: "Thu", day: 4, dir: "right", dur: 442, startMin:  5.850, started: "07:05:51", cluster: "early"  },
    { date: "2026-10-05", dayName: "Mon", day: 1, dir: "left",  dur: 524, startMin: 11.750, started: "07:11:45", cluster: "late"   },
    { date: "2026-10-06", dayName: "Tue", day: 2, dir: "right", dur: 362, startMin:  7.933, started: "07:07:56", cluster: "early"  },
    { date: "2026-10-07", dayName: "Wed", day: 3, dir: "left",  dur: 240, startMin:  7.750, started: "07:07:45", cluster: "early"  },
    { date: "2026-10-08", dayName: "Thu", day: 4, dir: "right", dur: 353, startMin:  6.633, started: "07:06:38", cluster: "early"  },
    { date: "2026-10-19", dayName: "Mon", day: 1, dir: "left",  dur: 660, startMin: 12.800, started: "07:12:48", cluster: "late"   },
    { date: "2026-10-20", dayName: "Tue", day: 2, dir: "right", dur: 322, startMin:  9.867, started: "07:09:52", cluster: "middle" }
  ];

  var DIRS = [
    { key: "left",  label: "Left",  symbol: "circle"  },
    { key: "right", label: "Right", symbol: "diamond" }
  ];

  var FLOOR = 180;                  // 3:00, below the fastest run, so the stems are visible
  var HOME  = { x: 1.75, y: -1.55, z: 0.75 };
  var plot  = document.getElementById("plot");
  var root  = document.querySelector(".viz-root");

  function mmss(s) {
    return Math.floor(s / 60) + ":" + String(s % 60).padStart(2, "0");
  }

  function theme() {
    var css = getComputedStyle(root), t = {};
    ["surface-1", "surface-2", "pane", "grid", "text-1", "text-2", "left", "right"]
      .forEach(function (name) { t[name] = css.getPropertyValue("--" + name).trim(); });
    return t;
  }

  function traces(t) {
    var out = [], stems = document.getElementById("stems").checked;

    DIRS.forEach(function (d) {
      var pts = RUNS.filter(function (r) { return r.dir === d.key; });
      var colour = t[d.key];

      if (stems) {                      // depth is guesswork in a 3D scatter; these fix it
        var sx = [], sy = [], sz = [];
        pts.forEach(function (r) {
          sx.push(r.startMin, r.startMin, null);
          sy.push(r.day, r.day, null);
          sz.push(FLOOR, r.dur, null);
        });
        out.push({
          type: "scatter3d", mode: "lines", x: sx, y: sy, z: sz,
          line: { color: colour, width: 2 }, opacity: 0.35,
          showlegend: false, hoverinfo: "skip"
        });
      }

      out.push({
        type: "scatter3d", mode: "markers", name: d.label,
        x: pts.map(function (r) { return r.startMin; }),
        y: pts.map(function (r) { return r.day; }),
        z: pts.map(function (r) { return r.dur; }),
        marker: {
          size: 9, symbol: d.symbol, color: colour,
          line: { color: t["surface-1"], width: 2 }
        },
        customdata: pts.map(function (r) {
          return [mmss(r.dur), r.dayName + " " + r.date.slice(5), r.started, d.label, r.cluster];
        }),
        hovertemplate:
          "<b>%{customdata[0]}</b> going %{customdata[3]}<br>" +
          "%{customdata[1]}, started %{customdata[2]}<br>" +
          '<span style="opacity:.65">%{customdata[4]} start</span>' +
          "<extra></extra>"
      });
    });
    return out;
  }

  function layout(t) {
    var axis = {
      showbackground: true, backgroundcolor: t.pane,
      gridcolor: t.grid, zerolinecolor: t.grid, showspikes: false,
      tickfont: { color: t["text-2"], size: 11 }
    };
    function titled(text) { return { text: text, font: { color: t["text-1"], size: 12 } }; }

    return {
      paper_bgcolor: t["surface-1"],
      font: { color: t["text-2"], size: 13 },
      margin: { l: 0, r: 0, t: 8, b: 0 },
      showlegend: true,
      legend: {
        orientation: "h", x: 0, y: 1.02, xanchor: "left", yanchor: "bottom",
        bgcolor: "rgba(0,0,0,0)", font: { color: t["text-1"] }
      },
      hoverlabel: {
        bgcolor: t["surface-2"], bordercolor: t.grid,
        font: { color: t["text-1"], size: 13 }
      },
      scene: {
        aspectmode: "cube",
        camera: { eye: HOME },
        xaxis: Object.assign({}, axis, {
          title: titled("x - start time"), range: [5, 14],
          tickvals: [6, 8, 10, 12, 14],
          ticktext: ["07:06", "07:08", "07:10", "07:12", "07:14"]
        }),
        yaxis: Object.assign({}, axis, {
          title: titled("z - day of week"), range: [0.4, 5.6],
          tickvals: [1, 2, 3, 4, 5],
          ticktext: ["Mon", "Tue", "Wed", "Thu", "Fri"]
        }),
        zaxis: Object.assign({}, axis, {
          title: titled("y - drive length"), range: [FLOOR, 700],
          tickvals: [240, 300, 360, 420, 480, 540, 600, 660],
          ticktext: ["4:00", "5:00", "6:00", "7:00", "8:00", "9:00", "10:00", "11:00"]
        })
      }
    };
  }

  function draw() {
    var t = theme();
    Plotly.react(plot, traces(t), layout(t), {
      responsive: true, displaylogo: false, scrollZoom: true,
      modeBarButtonsToRemove: ["toImage"]
    });
  }

  function table() {
    var body = document.querySelector("#tbl tbody");
    RUNS.forEach(function (r) {
      var tr = document.createElement("tr");
      [r.date, r.dayName, r.started, mmss(r.dur), r.dir, r.cluster].forEach(function (v, i) {
        var td = document.createElement("td");
        if (i === 3) { td.className = "num"; }
        if (i === 4) {                        // identity is never colour alone: key, then word
          var k = document.createElement("span");
          k.className = "key " + r.dir;
          k.style.background = "var(--" + r.dir + ")";
          td.appendChild(k);
          td.appendChild(document.createTextNode(r.dir === "left" ? "Left" : "Right"));
        } else {
          td.textContent = v;
        }
        tr.appendChild(td);
      });
      body.appendChild(tr);
    });
  }

  document.getElementById("stems").addEventListener("change", draw);

  document.getElementById("reset").addEventListener("click", function () {
    Plotly.relayout(plot, { "scene.camera.eye": HOME });
  });

  document.getElementById("theme").addEventListener("click", function () {
    var dark = theme()["text-1"] === "#ffffff";
    document.documentElement.setAttribute("data-theme", dark ? "light" : "dark");
    draw();
  });

  window.matchMedia("(prefers-color-scheme: dark)").addEventListener("change", function () {
    if (!document.documentElement.hasAttribute("data-theme")) { draw(); }
  });

  table();
  draw();
})();
</script>
</body>
</html>
```

## Notes on how it was drawn

- Two categorical colours, slots 1 and 2 of the documented palette: blue `#2a78d6` and
  orange `#eb6834`, re-stepped to `#3987e5` and `#d95926` for the dark surface. That is the
  pair that clears the colour-blindness floors on all pairs in both modes. Direction is
  carried by the marker shape too - circle and diamond - so it never rests on colour alone,
  and the legend and the table name it in words.
- A 3D scatter hides depth: how far back a point sits is guesswork from a still image. The
  drop lines are the fix, and the table is there for every value the rotation makes hard to
  read.
- The palette validator could not be run from the job that built this, because its shell
  runs only the relay client. The colours are the documented pair rather than a fresh
  validation, and the graph has not been opened in a browser from here either - say so if
  anything in it is off.
