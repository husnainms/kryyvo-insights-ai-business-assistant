# Kryyvo Insights

![Kryyvo Insights](assets/cover.jpg)

> **An AI assistant that answers business questions from ERP data, without making up numbers.**
>
> This is a showcase repo for a Kryyvo product. The source code is private. A live demo or a code walkthrough is available on request.

**Client:** Kryyvo product  
**My role:** Architecture, design and full-stack development through Kryyvo  
**Status:** Pilot on a live ERPNext instance, nightly delivery trial under way

## The problem

Owners want quick answers, such as yesterday's sales or who owes them money, without opening an ERP. A chatbot that invents a figure is worse than no chatbot, because the owner stops trusting it.

## What I built

- **Chat questions** in English, Roman Urdu or Urdu, answered from 15 defined business metrics: sales, collections, receivables and payables, expenses, dormant customers and more.
- **Nightly digest and alerts** delivered at 9 pm in each recipient's own time zone.
- **A small add-on app inside the ERP** that returns only totals, never raw records.
- **Per-user permissions,** so a branch manager only ever sees their own branch.
- **An onboarding script** that checks metrics against the ERP's own standard reports before they are switched on.

## Engineering highlights

- **Number guard.** Every figure in a reply must match a result from a verified query, and anything else is blocked before it is sent.
- The metrics wired so far reconcile to the paisa against the ERP's own reports.
- A 70-case evaluation suite, 69 of which pass against a live ERPNext instance, re-run on every prompt change.
- Channel-neutral design: Discord today, WhatsApp next.

## Stack

| Layer | Technology |
|---|---|
| **Service** | Python 3.12, Pydantic v2, httpx, APScheduler |
| **AI** | LLM tool-calling with a deterministic number guard |
| **Integration** | ERPNext / Frappe custom app |
| **Quality** | pytest, strict mypy, ruff, Docker Compose |

---

[← More projects on my profile](https://github.com/husnainms) · Want a demo or a code walkthrough? Email [info@kryyvo.com](mailto:info@kryyvo.com).
