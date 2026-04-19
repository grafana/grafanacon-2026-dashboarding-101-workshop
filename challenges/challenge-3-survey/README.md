# Challenge 3: Survey Feedback Visualizer

**Data source:** TestData (CSV) · **Facilitator:** Yaëlle

**Starting dashboard:** _TBD_
_(Make a copy before editing — Save > Save as Copy > select your folder)_


**Submit your answer:** [Via this form](https://docs.google.com/forms/d/e/1FAIpQLSfoaIbrcuTWsPGgfZOuKOv8wm4wB8gSAtwTKm9WUuq8S8OMqw/viewform?usp=dialog)

---

## Context

I have sent out a survey after delivering a Hands-on Lab at a conference.
I have set up a dashboard to visualise the feedback data from within my Grafana instance.

---

## Task 1

The data looks a bit messy. We have 2 types of people who look at the dashboard:

- The **events team**, focused on 100% completion
- The **facilitators**, interested in the actual feedback

> "I want to organise my dashboard in a cleaner and easier to read way."

---

## Task 2

I added a new question to the form: "Would you recommend the lab to a colleague?"

> "I want to visualise that data in a meaningful way."

The response data is boolean (yes / no).

---

## Hints

<details>
<summary>Task 1 hints</summary>

- Grafana supports **Tabs** inside a dashboard to separate content for different audiences
- Create two tabs:
  - **Completion** — with the responses stat and responses over time panels
  - **Feedback** — with the bar chart panels (satisfaction, relevance)
- Notice how you can easily switch between tabs and row layouts!

</details>

<details>
<summary>Task 2 hints</summary>

- **Duplicate** one of the existing bar chart panels
- Go to the **Transformations** tab and update the **Group by** transformation to look at the recommendation question column
- Change the visualization to **Pie chart** — it's a natural fit for yes/no distributions
- Edit the panel name to something like "Would you recommend this lab?"

</details>

---

[View solution](./solution.md)
