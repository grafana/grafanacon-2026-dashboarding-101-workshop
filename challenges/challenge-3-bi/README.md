# Challenge 3: Survey Feedback Visualizer

**Data source:** Business Intelligence (Google Sheets) · **Facilitator:** Yaëlle

---

## Context

> **TODO:** Confirm with Yaëlle — is this the exact Google Sheet attendees will connect to, or will they use their own? Add the Sheet URL / data source name once confirmed.

I have sent out a survey after delivering a Hands-on Lab at a conference.
I have set up a dashboard to visualise the feedback data from within my Grafana instance.

---

## Task 1

I added a new question to the form: "Would you recommend the lab to a colleague?"

> "I want to visualise that data in a meaningful way."

The response data is boolean (yes / no).

---

## Task 2

The data looks a bit messy. We have 2 types of people who look at the dashboard:

- The **events team**, focused on 100% completion
- The **facilitators**, interested in the actual feedback

> "I want to organise my dashboard in a cleaner and easier to read way."

---

## Hints

<details>
<summary>Task 1 hints</summary>

- The data is boolean (yes/no) — think about which visualization shows proportions well
- A **Pie chart** works great for yes/no distributions
- You will need to group and count the responses by value
- Use a **Transformation** to aggregate: group by the recommendation column and count occurrences

</details>

<details>
<summary>Task 2 hints</summary>

- Grafana supports **Tabs** inside a dashboard to separate content for different audiences
- Create two tabs: one for the events team (completion, attendance numbers), one for facilitators (scores, recommendations)
- This keeps the same data in one dashboard but presents it differently depending on who is looking

</details>

---

[View solution](./solution.md)
