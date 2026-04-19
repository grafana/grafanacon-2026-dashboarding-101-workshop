# Solution: Challenge 1 — Team Weather Dashboard

---

## Task 1: Add Barcelona

### Step 1 — Duplicate a temperature panel

1. Open the weather dashboard (your copy)
2. Find any existing temperature panel (e.g. Paris)
3. Click the panel menu (`⋮`) > **Duplicate**

### Step 2 — Update the coordinates

1. Open the duplicated panel in edit mode
2. In the Infinity query, change the URL parameters:
   - `latitude=41.3874`
   - `longitude=2.1686`

### Step 3 — Update the title

Change the panel title to something like `🇪🇸 Barcelona`.

### Step 4 — Adjust the row layout

You now have 6 cities. Update the row settings to allow **6 panels per row** (max column count) so they all fit on one line.

### Alternative approach

Instead of duplicating and editing, you can:
1. Add a new panel
2. Use the saved query **"Paris Temperature"**
3. Update the coordinates in the URL to Barcelona's


## Expert Mode

You can use a custom variable + repeats to improve the dashboard

### Step 1 - Create a custom variable

1. Name it **location**
2. Custom options leveraging key value pairs - use **JSON** format:

```json
[
  { "value": "🇫🇷 Paris", "latitude": 48.8566, "longitude": 2.3522 },
  { "value": "🇩🇪 Sankt Augustin", "latitude": 50.7753, "longitude": 7.1872 },
  { "value": "🇳🇴 Maura", "latitude": 60.3752, "longitude": 5.3358 },
  { "value": "🇬🇧 Westminster", "latitude": 51.4975, "longitude": -0.1357 },
  { "value": "🇨🇭 Zurich", "latitude": 47.3769, "longitude": 8.5417 },
  { "value": "🇪🇸 Barcelona", "latitude": 41.3874, "longitude": 2.1686 }
]
```

### Step 2 - Use it in panel 

1. In the Temperature row, remove all but 1 panel 
    - destructive actions are scary - feel free to duplicate the row first (or know that you can always restore a previous version of a dashboard in dashboard settings)

2. Use the **Tenmplated Temperature** query for the only panel there
3. Set the panel on **repeat** by location
4. Notice how you now just have to change the variable value to update the dashboard

---

## Task 2: Add precipitation data

### Step 1 — Duplicate the temperature row

1. Click on the **Temperature** row header
2. Duplicate the entire row

### Step 2 — Rename the row

Rename the new row to something like `🌧️ Precipitation`.

### Step 3 — Update the query for precipitation

Use the saved query **"Templated Precipitation"** for the panel in the new row

### Step 3 — Update the visualization

1. Change the **unit** to `mm` (millimeters)


### Result

You now have two rows: one for temperature across 6 cities, one for precipitation across 6 cities.

A solution dashboard JSON is available for reference, but try to complete the exercise on your own first.
- [View solution dashboard](https://acde96.grafana.net/goto/ffjjy0dhemwhsb?orgId=stacks-1597849)  
- [Get json to import](./challenge1-solution.json)


