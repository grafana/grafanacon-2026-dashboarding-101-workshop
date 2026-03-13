# Section 2: From Data to Insight — Live Data

**Facilitator:** Alexa Vargas · **Duration:** 30 min

---

## The RED framework

Before we build, a mental model for what to look for in a service:

| Signal | Question |
|---|---|
| **R**ate | How many requests per second is this service handling? |
| **E**rrors | How many of those requests are failing? |
| **D**uration | How long are requests taking? Are they getting slower? |

If Rate is normal, Errors are low, and Duration is stable — your service is healthy.

---

## The 3 layers — applied

| Layer | What it means | In this exercise |
|---|---|---|
| Collect | Gather the data | Prometheus scraping Kubernetes metrics |
| Connect | Make it available in Grafana | `grafanacloud-prom` data source (pre-configured) |
| Visualize | Build something meaningful | Suggested Dashboards |

---

## Step 1 — Log in

Open your Grafana instance URL from the pre-event email and log in with the provided credentials.

---

## Step 2 — Find Suggested Dashboards

1. Go to **Connections** in the left sidebar
2. Click **Data Sources**
3. Find and open the **`grafanacloud-prom`** data source

A modal opens with dashboard suggestions based on the Prometheus data source type.

> Grafana does not detect what is inside your Prometheus. It suggests dashboards compatible with the Prometheus data source type. You still need to pick the one that fits your use case.

---

## Step 3 — Load the Kubernetes dashboard

1. In the suggestions modal, search for `Kubernetes/Views`
2. Select **Kubernetes / Views / Pods**
3. Click **Use Dashboard**

You should now see a dashboard with live pod data.

**Checkpoint:** Raise your hand when you can see panels populated with live data. Staff will come to you if you are stuck.

---

## Step 4 — Explore what is there

Do not edit anything yet. Just look.

1. Find a panel showing **request rate** — which RED signal is this?
2. Find a panel showing **errors** or failed pods
3. Change the time range (top-right) from `Last 1h` to `Last 3h`
4. Watch the panels update — does the trend tell a different story?

**Checkpoint:** Did your panels update when you changed the time range?

---

## Step 5 — Edit a panel

1. Click the `⋮` menu on any panel and select **Edit**
2. Change the panel title to something descriptive, for example: `Pod Restart Count`
3. Look at the query — this is PromQL. You do not need to write it today, just observe.
4. Click **Apply** to save the panel change

---

## Step 6 — Add a variable

Variables make a dashboard reusable. Instead of one static view, the dashboard adapts to whoever is looking at it.

1. Open **Dashboard settings** (gear icon, top right)
2. Go to **Variables** and click **Add variable**
3. Configure it:
   - **Type:** Query
   - **Name:** `namespace`
   - **Data source:** `grafanacloud-prom`
   - **Query:** `label_values(kube_pod_info, namespace)`
4. Click **Run query** to preview the values, then **Apply**
5. Go back to the dashboard — you should see a namespace dropdown at the top

**Checkpoint:** Can you see the namespace dropdown? Try changing it and watch the panels update.

---

## Step 7 — Save your dashboard

1. Click the **Save** icon (top right)
2. Give it a meaningful name: `ops / system-health`
3. Add a description: who is this dashboard for and what question does it answer?
4. Click **Save**

---

## Best practices

| Do | Do not |
|---|---|
| Name panels clearly: `Pod Restart Count` | Leave panels as `Panel 3` |
| Add a dashboard description | Leave the description blank |
| One panel, one question | Cram multiple unrelated metrics into one panel |
| Use units: `%`, `req/s`, `ms` | Leave values without context |
| Add a description — Grafana's AI assistant reads it | |
