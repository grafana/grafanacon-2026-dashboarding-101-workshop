# Hands-on #1: Barcelona Public WiFis

**Section:** From data to insight: static data · **Facilitator:** Yaëlle
**Data source:** Infinity · **Duration:** 30 min

---

## What you will build

A dashboard showing Barcelona's public Wi-Fi hotspots — a map of locations and a count per district. You will learn the anatomy of a dashboard, how to connect to a public API with Infinity, and how to make your dashboard interactive with a template variable.

**Expected outcome:** A saved dashboard with a GeoMap panel, a Stat count panel, and a district filter variable.

---

## Anatomy of a Dashboard

Before building, take a moment to recognize the parts you will be using:

| Element | What it does |
|---|---|
| **Panels / grid** | Individual visualizations arranged on a canvas |
| **Variables** | Dropdowns at the top that filter the whole dashboard |
| **Time range picker** | Controls the time window for all panels |
| **Data (auto)refresh** | Keeps panels updated on a schedule |
| **Collapsible rows** | Group panels into sections |

---

## Anatomy of a Panel (edit mode)

When you open a panel in edit mode, there are 6 areas:

1. **Queries** — where you define what data to fetch
2. **Transforms** — post-process the data before rendering
3. **Field/series config** — units, decimals, display name
4. **Field/series overrides** — apply config to specific fields only
5. **Panel options** — legend, tooltip, title
6. **Render area** — the live preview of your visualization

---

## Step 1: GeoMap — where are the hotspots?

### 1. Create a new blank dashboard

Go to **Dashboards** > **New** > **New Dashboard**. Save it immediately in your personal folder (`@yourname`) with a meaningful name, e.g. `Barcelona Public WiFis`.

### 2. Add a new panel

Click **Add** > **Visualization**.

- **Data source:** Infinity
- **URL:**
  ```
  https://opendata-ajuntament.barcelona.cat/data/api/action/datastore_search?resource_id=a_d6f8-b33d-4091-94ae-c14b8bb0ecbb
  ```
- **Parsing options:**
  - Rows/Root: `.result.records[]`
  - Columns:

  | Selector | Alias | Format |
  |---|---|---|
  | `geo_epgs_4326_lat` | `latitude` | String |
  | `geo_epgs_4326_lon` | `longitude` | String |
  | `name` | `Title` | String |

### 3. Select the GeoMap visualization

Switch the visualization type (top right) to **Geomap**.

Grafana will plot a dot on the map for each record using the `latitude` and `longitude` columns, with `Title` as the label.

**Checkpoint:** Can you see dots on a map of Barcelona?

---

## Step 2: Stat panel — how many hotspots?

### 1. Add another panel

Click **Add** > **Visualization**. Use the **exact same query** as Step 1 (same data source, same URL, same parsing options).

### 2. Select the Stat visualization

Switch to **Stat**.

- Under **Value options**, set **Show** to `Calculate`
- Set **Calculation** to `Distinct Count`
- Set **Fields** to `name`

### 3. Play around with options

Try changing colors, adding a unit label, or toggling the graph sparkline.

**Checkpoint:** Does the number match the count of dots on your map?

---

## Template Variables — make it interactive

Variables let viewers filter the dashboard without editing it. Grafana supports several types:

**Basic:**

| Type | When to use |
|---|---|
| **Query** | Values come from a data source query (e.g. list of namespaces) |
| **Custom** | Static list you define manually |
| **Textbox** | Free-text input from the viewer |
| **Switch** | A boolean toggle (on/off) |

**Advanced:**

| Type | When to use |
|---|---|
| **Constant** | Hidden value injected into queries (e.g. a metric prefix) |
| **Data source** | Dynamically switch the data source across panels |
| **Interval** | Time grouping values (1m, 1h, 1d) |
| **Ad hoc filters** | Key/value filters added on the fly by the viewer |

---

## Bonus task: filter by district

### 1. Add a Custom variable

Go to **Dashboard settings** > **Variables** > **Add variable**.

- **Type:** Custom
- **Name:** `addresses_district_id`
- **Custom options:** `1, 2, 3, 4, 5, 6, 7, 8, 9`

Apply and go back to the dashboard. You should see a **District id** dropdown at the top.

### 2. Add a transformation to filter panels

Open either panel in edit mode and go to the **Transform data** tab.

- Add transformation: **Filter data by values**
- **Filter type:** Include
- **Field:** `addresses_district_id`
- **Match:** Is equal
- **Value:** `$addresses_district_id`

Now when the viewer picks a district, both panels filter to only show hotspots in that district.

**Checkpoint:** Change the district dropdown — does the count and map update?

---

## Summary

You went through all 3 layers with real data:

| Layer | What happened |
|---|---|
| **Collect** | Barcelona Open Data API publishes Wi-Fi hotspot records |
| **Connect** | Infinity data source fetched and parsed the JSON |
| **Visualize** | GeoMap + Stat panels + a variable for interactivity |
