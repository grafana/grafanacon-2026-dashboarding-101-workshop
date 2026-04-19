# Solution: Challenge 3 — Survey Feedback Visualizer

---

## Task 1: Organise the dashboard with tabs

Two audiences, two views — same dashboard.

### Step 1 — Create tabs

1. Group the panels into a Tab clicking the **group to tab** button
2. Name the first tab: `Completion`
3. Create a second tab (click **add tab** button), name it: `Feedback`

### Step 2 — Organise panels into tabs

**Completion tab** — focused on attendance and response rates:

- Responses stat panel (response rate %)
- Responses over time (time series)

**Feedback tab** — focused on actual survey results:

- Event Satisfaction (bar chart)
- Session Satisfaction (bar chart)
- Raw responses (table)

### Step 3 — Move existing panels

Drag and drop existing panels into the appropriate tab. Each tab acts as an independent layout.

Notice how you can easily switch between tabs and row layouts!

### Result

The dashboard now has two tabs. The events team opens the dashboard and immediately sees completion numbers. Facilitators switch to their tab and see the actual feedback.

---

## Task 2: Visualise the recommendation question

The new question "Would you recommend the lab to a colleague?" has boolean (yes/no) responses.

### Step 1 — Duplicate a bar chart panel

1. Find one of the existing bar chart panels (e.g. Session Satisfaction)
2. Click the panel menu (`⋮`) > **Duplicate**

### Step 2 — Update the transformation

1. Open the duplicated panel in edit mode
2. Go to the **Transformations** tab
3. Find the **Group by** transformation
4. Change the group-by field to the recommendation question column: `Would you recommend the lab to a colleague?`

### Step 3 — Change the visualization

1. Switch the visualization to **Pie chart**
2. Set Value options > Show to **all values**
3. This now shows the yes/no proportion at a glance

### Step 4 — Update the title

Change the panel title to: `Lab Recommendation`


### Result

A pie chart showing the yes/no split. At a glance, facilitators and event teams can see the recommendation rate.


A solution dashboard JSON is available for reference, but try to complete the exercise on your own first.
- [View solution dashboard](https://acde96.grafana.net/goto/afjk5rzai1m2ob?orgId=stacks-1597849)  
- [Get json to import](./challenge3-solution.json)
