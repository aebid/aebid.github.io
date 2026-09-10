---
title: CMS Service
nav_order: 5
permalink: /service/
---

# CMS Service Work

What is CMS Service work.

## Projects

### GEM Alignment

What it is, why it matters, and your contribution.

### GEM-CSC Integrated Trigger

{% comment %}
  Structure below: what it is -> why it was needed -> how it works ->
  what I did -> where it stands. Fill the [brackets] and delete these
  comments as you go.

  Everything unbracketed is scaffolding I drafted from public CMS
  context and your resume. Check it before publishing - I am not the
  authority on your subsystem.
{% endcomment %}

The GEM-CSC integrated trigger combines hits from the new GEM detectors with
segments from the CSCs to build a single, better muon trigger object in the
CMS endcap.

**Why it was needed.**
{% comment %}
  The reader here is a physicist outside your subsystem, or a hiring
  committee. Two or three sentences, no jargon that you have not unpacked.
  Worth covering: the endcap rate problem, and what happens to a
  single-detector trigger as luminosity climbs.
{% endcomment %}
[Why the CSC-only endcap muon trigger runs out of room at high luminosity, and
what that costs you in threshold or rate.]

**How it works.**
{% comment %}
  The mechanism, in plain language. The lever-arm/bending-angle story is
  the intuitive core - a reader who takes away only one idea should take
  away that one.
{% endcomment %}
GE1/1 sits directly in front of ME1/1 in the endcap. Because the two detectors
are separated, pairing a GEM hit with a CSC segment gives a much longer lever
arm than the CSC alone, which sharpens the bending-angle measurement and so the
momentum assigned to the muon at Level 1. [Add what that buys concretely - rate
reduction at fixed efficiency, a lower threshold, efficiency recovery when CSC
layers underperform. Numbers if they are public.]

The combined stubs are built in the [OTMB firmware / where exactly], which ties
into the CSC Optical Trigger Motherboard work in the section [above/below].
{% comment %} Cross-link this to your OTMB work - it is the same hardware path. {% endcomment %}

**My role.**
{% comment %}
  The most important block on the page, and the one only you can write.
  Be concrete and take credit. "Led integration and coordination" is a
  real leadership claim - show the scale that backs it.
{% endcomment %}
I led integration and coordination for the GEM-CSC integrated trigger,
coordinating a team of graduate students, post-docs, and research scientists
across [N] institutes. I also served as Level 3 Trigger Contact in the GEM
Detector Performance Group, the lead contact for trigger issues in the GEM-CSC
subsystem.

[What did *you* personally build, debug, or decide? One or two specifics beat
any amount of title. Good candidates: what was broken when you took it over,
the hardest bug, what you had to get working before a data-taking milestone.]

**Where it stands.**
[Commissioned and running in Run 3 since [date]? What is left for Phase-2 /
HL-LHC? What are you handing to whoever takes over?]

**References.**
{% comment %}
  You produced several public detector notes - link them. Public CMS
  results are citable and they make this page far more credible than
  prose alone. CMS DP notes live under cms-results.web.cern.ch.
{% endcomment %}
- [CMS DP-20XX/XXX, "Title"](https://cms-results.web.cern.ch/cms-results/public-results/detector-performance/)
- [Talk or poster, conference, year]

