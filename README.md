# Power Map Analyzer

**An interactive tool that maps any company's stakeholders by leverage and risk — built to systematize the stakeholder analysis behind operational due diligence.**

🔗 **Live demo:** `https://RishabVenkataraman.github.io/power-map`  

---

## The problem it solves

When a private equity firm evaluates a company — before buying it, and again while improving it — one question keeps mattering: **who does this company depend on, who holds the power, and where are the single points of failure?** A dangerously sole-sourced supplier, a customer that's 35% of revenue, a plant manager who alone knows the main line — these are the things that sink a deal or block a turnaround.

Sharp operators do this analysis informally, on a whiteboard. **This tool systematizes it.**

---

## What it does

- **Input any company** and its stakeholders (suppliers, customers, key people, regulators…).
- **Scores each party's power** on a 0–10 scale using a custom composite formula.
- **Flags chokepoints** (single points of failure) in a *separate* risk register.
- **Draws a visual map** — node size & color = power, red ring = risk, arrows = direction of dependence.
- **Click any node** to see its detail and *why* it scored that way.

---

## How it works — the thinking behind the score

The interesting part isn't the code; it's the model. The core design decisions:

- **Power is relational and derived, not guessed.** A party's power is computed from how much others depend on it and how irreplaceable it is — not typed in by gut.
- **A composite blend, not a single formula.** Power requires *both* a critical dependence *and* irreplaceability, so the score multiplies those (an "AND"). But pure multiplication is brittle, so it's blended with an average for robustness — each method cancels the other's weakness.
- **Leverage and fragility are kept separate.** A chokepoint is about *risk* ("if this breaks, how bad?"), not just *power* ("how much can they squeeze us?"). So chokepoints get their own risk register — a dangerous-but-low-power dependency can't hide inside an averaged score.
- **Diminishing returns across dependencies.** Breadth counts, but with a decay, so a pile of trivial dependencies can't outrank one critical chokepoint.
- **A hybrid override.** The tool computes a baseline; an analyst can adjust it — but only with a documented reason. This is where qualitative, non-systematic factors (geopolitics, key-person dynamics) live, without becoming a silent fudge.

---

## How to use it

1. Open the live demo (or `index.html`).
2. Set the **company** name.
3. **Add stakeholders** — name, strength of dependence (1–5), irreplaceability (1–5), and whether it's a chokepoint.
4. Watch the map build. **Click any node** for its breakdown.
5. **Clear all** to start a fresh company.

---

## What this is — and isn't

This is an **analysis tool**: the analyst supplies the judgment (the scores), and the tool computes and visualizes the resulting leverage-and-risk picture. It is *not* a black box that claims to know everything about any company — because the most important diligence facts are private and judgment-based. The value is the **structured thinking**, which mirrors how real operational diligence actually works.

---

## Built with

Plain **HTML, CSS, and JavaScript** (SVG for the map). Zero dependencies, single self-contained file — runs in any browser, hosts free on GitHub Pages.

---

## About this project

I designed the framework and scoring model, directed the build, and understand every line. It's a working artifact of how I think about operational value and risk — the intersection of industrial-engineering systems thinking and operational private equity.
