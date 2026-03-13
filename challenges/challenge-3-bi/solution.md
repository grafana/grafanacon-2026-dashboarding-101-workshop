# Solution: Challenge 3 — Survey Feedback Visualizer

---

## Task 1: Visualise the recommendation question

The new question "Would you recommend the lab to a colleague?" has boolean (yes/no) responses. A pie chart is the right choice — it shows proportion at a glance.

### Step 1 — Query the recommendation column

> **TODO:** Add the exact sheet name and column name once Yaëlle confirms the Google Sheet structure.

1. Add a new panel
2. Data source: **Business Intelligence** (Google Sheets)
3. Select the sheet containing your form responses
4. Select the column corresponding to the recommendation question

### Step 2 — Add a transformation to count responses

1. Go to the **Transformations** tab
2. Add **Group by**:
   - Group by: `recommendation` column
   - Calculate: **Count** on any field
3. This produces a table with two rows: `Yes` with a count, `No` with a count

### Step 3 — Set the visualization

1. Switch to **Pie chart** visualization
2. Configure:
   - **Value:** the count field
   - **Labels:** the recommendation column (Yes / No)
3. Panel title: `Would you recommend this lab?`

### Result

A pie chart showing the yes/no split. At a glance, facilitators and event teams can see recommendation rate.

---

## Task 2: Organise the dashboard with tabs

Two audiences, two views — same dashboard.

### Step 1 — Add tabs to the dashboard

1. In the dashboard, click **Add** > **Tab**
2. Name the first tab: `Events Team`
3. Add a second tab: `Facilitators`

### Step 2 — Organise panels into tabs

**Events Team tab** — focused on completion and attendance:
- Total responses / attendance count (Stat panel)
- Completion rate % (Gauge panel)
- Response trend over time (Time series)

**Facilitators tab** — focused on actual feedback:
- Overall satisfaction score (Stat panel)
- Score distribution (Bar chart)
- "Would you recommend?" pie chart (from Task 1)
- Open-ended responses table (Table panel)

### Step 3 — Move existing panels

Drag and drop existing panels into the appropriate tab. Each tab acts as an independent layout.

### Result

The dashboard now has two tabs. The events team opens the dashboard and immediately sees completion numbers. Facilitators switch to their tab and see the actual feedback. Same data, organised for the right audience.
