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

---

## Task 2: Add precipitation data

### Step 1 — Duplicate the temperature row

1. Click on the **Temperature** row header
2. Duplicate the entire row — this gives you 6 panels pre-configured with each city's coordinates

### Step 2 — Update the query for precipitation

For each panel in the new row, update the Infinity query URL to request precipitation data. Use the saved query **"Barcelona Precipitation"** as a starting point, then change the coordinates for the other cities.

The API parameter to add: `&daily=precipitation_sum&timezone=auto`

### Step 3 — Update the visualization

1. Change the **unit** to `mm` (millimeters)
2. Update the panel titles to reflect precipitation (e.g. `🇪🇸 Barcelona — Rain`)

### Step 4 — Rename the row

Rename the new row to something like `🌧️ Precipitation`.

### Result

You now have two rows: one for temperature across 6 cities, one for precipitation across 6 cities.
