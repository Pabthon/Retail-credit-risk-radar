# Retail Credit Risk — Early-Warning Radar

A lightweight monitoring tool for a retail credit portfolio: eight indicators checked against risk-appetite thresholds, with a trend check that flags emerging risk before any limit is actually breached.

## What it does

* Tracks 8 indicators across the four areas a retail credit risk function typically monitors: **credit performance** (delinquency, charge-offs), **behavioural \& affordability signals** (utilisation, minimum-payment reliance), **concentration** (geography, thin-file origination), and **macro/external pressure** (unemployment sensitivity, cost-of-living).
* Each indicator carries a standard green/amber/red threshold structure, consistent with a typical risk appetite statement.
* A **trend check** flags indicators still inside the green zone as `Watch` if they show three consecutive months of meaningful deterioration — a lead signal ahead of any actual breach. This is the core idea: a static RAG check only tells you about a problem once it has already arrived; this catches it earlier.
* Every indicator maps to an owner and an escalation tier (first line / second line / Risk Committee), reflecting a three-lines-of-defence governance structure.
* Each indicator can be viewed as a trend chart or as a plain table of the underlying 12-month history.

## Why I built this

I wanted to demonstrate how I think about risk monitoring in practice, applied to a context (retail credit) that isn't my direct background — rather than just describe it on a CV. The interesting design decision is the trend-based `Watch` tier: it's simple arithmetic (a threshold check plus a 3-month trend check), not a model, but it's the difference between an early-warning framework and a dashboard that only reacts after the fact.

## Data

All data in this tool is **synthetic and illustrative**. No real customer, portfolio, or company data has been used anywhere.

## Built with

Single self-contained HTML/CSS/JavaScript file — no build step, no dependencies beyond two Google Fonts. Built with assistance from Claude (Anthropic), as a deliberate way of pairing AI-assisted development with domain judgement rather than hiding one behind the other.

