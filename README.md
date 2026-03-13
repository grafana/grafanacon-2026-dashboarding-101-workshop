# Dashboarding 101: Best practices to build and edit Grafana dashboards

**GrafanaCON Barcelona 2026 · Hands-on Lab**
Facilitators: Yaëlle Chaudy · Alexa Vargas Ortega

---

## What you will learn

By the end of this workshop you will be able to:

- Understand the parts of a dashboard: panels, visualizations, queries, variables, time picker
- Use Suggested Dashboards to overcome blank-page anxiety
- Pick the right visualization for your data
- Create template variables to make a dashboard adapt to the viewer
- Apply best practices: naming, descriptions, layout

---

## Agenda

| Section | Facilitator | Duration |
|---|---|---|
| Welcome and setup | Yaëlle | 15 min |
| Basic concepts behind dashboarding | Alexa | 15 min |
| From data to insight: static data | Yaëlle | 30 min |
| From data to insight: live data | Alexa | 30 min |
| Break | | 15 min |
| Hands-on Challenges | Both | 1 hour |

---

## Your Grafana instance

- **Grafana URL:** https://afcb45.grafana.net/
- **Data sources available:**
  - `grafanacloud-prom` — Prometheus (Kubernetes metrics)
  - Infinity — public APIs (weather, open data)
  - Business Intelligence — Google Sheets

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

- [Challenge 1: The Manager's View](./challenges/challenge-1-managers-view/README.md) — K8s · Alexa
- [Challenge 2: Team Weather Dashboard](./challenges/challenge-2-weather/README.md) — Infinity · Yaëlle
- [Challenge 3: Survey Feedback Visualizer](./challenges/challenge-3-bi/README.md) — Google Sheets · Yaëlle
- [Challenge 4: The Deployment Watchdog](./challenges/challenge-4-deployment-watchdog/README.md) — K8s · Alexa
- [Stretch: Set up an Alert](./challenges/stretch-alert/README.md) — Alexa

---

> Solutions are in each challenge's `solution.md` file.
