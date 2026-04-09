# Dashboarding 101: Best practices to build and edit Grafana dashboards

**GrafanaCON Barcelona 2026 · Hands-on Lab**
Facilitators: Yaëlle Chaudy · Alexa Vargas Ortega

---

## What you will learn

By the end of this workshop you will be able to:

- Understand the components of a dashboard: panels, visualizations, queries, variables, time picker
- Use Suggested Dashboards and Saved Queries to kick-start dashboard creation
- Iterate on a dashboard by refining layouts and adapting visualization types
- Create template variables to make a dashboard adapt to the viewer
- Apply best practices: naming, descriptions, layout
- Create an alert from a dashboard

---

## Agenda

| Section | Facilitator | Duration |
|---|---|---|
| Welcome and Introductions | Both | 15 min |
| Basic concepts behind dashboarding | Alexa | 15 min |
| From data to insight: static data | Yaëlle | 30 min |
| From data to insight: data that changes over time | Alexa | 30 min |
| Break | | 15 min |
| Hands-on Challenges | Both | 1 hour |

---

## Your Grafana instance

- **Grafana URL:** https://ecbf94.grafana.net/
- **Data sources available:**
  - `grafanacloud-prom` — Prometheus (Kubernetes metrics)
  - Infinity — public APIs (weather, open data)

---

## How challenges work

Each challenge gives you a starting dashboard. You work in your own copy:

1. **Make a copy** — Open the provided link, click **Edit**, then **Save** > **Save as Copy**, and select your personal folder (`@yourname`)
2. **Answer the challenge** — Explore panels, variables, and queries. Complete the tasks by adding or editing panels
3. **Check solutions** — Solutions and hints are available in this repo, or raise your hand to ask!

---

## Sections

- [Section 1: Static data hands-on — Barcelona WiFis](./section-1-static-data/README.md) — Yaëlle
- [Section 2: Live data hands-on — Kubernetes](./section-2-live-data/README.md) — Alexa

## Challenges

- [Challenge 1: Team Weather Dashboard](./challenges/challenge-1-weather/README.md) — Infinity · Yaëlle
- [Challenge 2: Service Level Monitoring](./challenges/challenge-2-service-level/README.md) — K8s / Prometheus · Alexa
- [Challenge 3: Survey Feedback Visualizer](./challenges/challenge-3-survey/README.md) — TestData · Yaëlle
- [Stretch: Set up an Alert](./challenges/stretch-alert/README.md) — Alexa

---

> Solutions are in each challenge's `solution.md` file.
