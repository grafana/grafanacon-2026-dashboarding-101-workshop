# Section 2: From Data to Insight — Data That Changes Over Time

**Facilitator:** Alexa Vargas · **Duration:** 30 min

---

## A snapshot vs a story

| Static data — a snapshot | Time series — a story |
|---|---|
| "Barcelona WiFi: 142 points" | "CPU has been climbing for 3 hours" |
| A fact at a point in time. | A trend. A spike at 2am. A slow degradation before an outage. This is where the real insight lives. |

---

## The 3 layers — applied

| Layer | What it means | In this exercise |
|---|---|---|
| Collect | Gather the data | Prometheus scraping Kubernetes metrics |
| Connect | Make it available in Grafana | `grafanacloud-prom` data source (pre-configured) |
| Visualize | Build something meaningful | Suggested Dashboards |

---

## Grot Plushies: E-commerce monitoring

You're the tech lead for the **Payment Squad**, responsible for the **payment service** and the **cart service** at Grot Plushies — a microservices e-commerce platform.

Your job: build a single dashboard that gives you — and your team — everything needed to monitor your K8s infrastructure.

---

## Step 1 — Log in

Open your Grafana instance URL and log in with the provided credentials.

---

## Step 2 — Find Suggested Dashboards

1. Go to **Connections** in the left sidebar
2. Click **Data Sources**
3. Find and open the **`grafanacloud-prom`** data source
4. Click **Build dashboards** > **From suggestions**

A modal opens with dashboard suggestions based on the Prometheus data source type.

> Grafana does not detect what is inside your Prometheus. It suggests dashboards compatible with the Prometheus data source type. You still need to pick the one that fits your use case.

---

## Step 3 — Load the Kubernetes dashboard

1. In the suggestions modal, search for `Kubernetes/Views`
2. Select **Kubernetes / Views / Pods**
3. Click **View Dashboard**

You should now see a dashboard with live pod data.

**Checkpoint:** Raise your hand when you can see panels populated with live data. Staff will come to you if you are stuck.

---

## Step 4 — Tailor the default dashboard to your needs

The Kubernetes dashboard is a great starting point, but it is designed for a broad audience. Your goal is to reshape it so it serves your team's specific needs.

---

## Step 5 — Filter the data to your services

Before hiding variables, use them to narrow the dashboard down to the services your team owns.

1. In the variable bar at the top, find the **pod** dropdown
2. Select only the **payment** and **cart** pods
3. Confirm that the panels update to show data for those pods only

**Checkpoint:** Are the panels now showing data for the payment and cart pods only?

---

## Step 6 — Hide some variables to make the dashboard less overwhelming

The default dashboard exposes many variables that may not be relevant to your use case. Hiding unnecessary ones reduces noise and makes the dashboard easier to use. Keep only **pod** and **resolution** visible.

1. Click the **Edit** button (top right) to enter edit mode
2. Hover over a variable in the variable bar — an edit pencil icon appears
3. Click the pencil icon — a sidebar opens on the right
4. Under **Display**, set the value to **Hidden**
5. Repeat for each variable you want to hide, keeping only **pod** and **resolution** visible

**Checkpoint:** Is the variable bar at the top of your dashboard shorter and easier to read?

---

## Step 7 — Save the dashboard

1. Click the **Save** icon (top right)
2. Give it a meaningful name, for example: `Payment Squad / K8s Health`
3. Add a description — who is this dashboard for, and what question does it answer?
4. Click **Save**

---

## Step 8 — Change the layout from rows to tabs

Tabs make it easier to navigate between groups of panels without scrolling through an entire page.

1. Click the **Edit** button (top right) to enter edit mode
2. Click the **cog icon** on the right side of the toolbar (just below the **+** button)
3. Under **Layout**, select **Tabs**
4. Save the dashboard

---

## Step 9 — Reorganise the tabs

Arrange the tabs so your viewers can find what they need at a glance.

1. In edit mode, drag and drop the tabs to reorder them
2. Rename each tab to reflect its content clearly, for example: `Overview`, `CPU`, `Memory`, `Network`
3. Save the dashboard

**Checkpoint:** Does the tab order reflect the most common questions your team asks?

---

## Bonus

### Override the series colour scheme

Apply a consistent colour scheme to **CPU Usage Request** and **CPU Usage Limit** to distinguish them clearly.

1. Open the panel in edit mode
2. Go to the **Overrides** tab in the right panel
3. Click **Add field override** > **Fields with name**
4. Select the series you want to override (e.g. `CPU Usage Request`)
5. Click **Add override property** > **Standard options > Color scheme**
6. Choose a colour and apply
7. Repeat for `CPU Usage Limit`

> **Tip:** You can use **Panel styles presets** for quick, consistent styling across panels.

---

### Change thresholds for a time series

Apply custom thresholds to **Memory Usage / Requests & Limits by container** to highlight critical states visually.

1. Open the panel in edit mode
2. In the right panel, go to **Standard options** > **Thresholds**
3. Set the following thresholds:

| Value | Colour |
|---|---|
| Base | Blue |
| 20 % | Purple |
| 30 % | Green |
| 60 % | Orange |
| 80 % | Red |

4. Click **Apply** to save your changes

---

## What you learnt in this section

- **No need to reinvent the wheel** — use suggested dashboards
- **Tailor the default dashboard** to your needs:
  - Hide variables to make the dashboard less overwhelming
  - Change the layout from rows to tabs
  - Reorganise the tabs to make it easier for viewers to find what they need
- **Bonus:** override the series colour scheme, change thresholds for a time series

---

## Best practices

| Do | Do not |
|---|---|
| Name panels clearly: `Pod Restart Count` | Leave panels as `Panel 3` |
| Add a dashboard description | Leave the description blank |
| One panel, one question | Cram multiple unrelated metrics into one panel |
| Use units: `%`, `req/s`, `ms` | Leave values without context |
| Add a description — Grafana's AI assistant reads it | |

---

> **No peeking!** A solution dashboard is available for reference, but try to complete the exercise on your own first.
> When you're done: View solution dashboard — _link TBD_
