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

The GEM-CSC Integrated Trigger is the combination of hits from the new GEM detectors with the segments from the CSC detectors to build a single better trigger object in the CMS endcap.

**Why it was needed.**

The LHC provides collisions at 40 MHz, or 1 per 25 nanoseconds.
If every collision was saved we would run out of disk space very quickly, so a trigger system is implemented to decide what data to save and what to ignore.
This system works on quickly and coarsely reconstructing the event to see if anything interesting exists.
With the upgrades to the LHC to increase luminosity, all experiments are preparing for the High-Luminosity LHC (HL-LHC).
In this new chapter with increased collision rates, the current existing trigger system would become unmanageable.
The addition of the GEM subsystem to CMS has been an upgrade designed to help attack this incoming problem.

**How it works.**

Current Level 1 muon triggering is mostly driven by a p<sub>T</sub> measurement of the trigger objects.
This is done in the endcap of CMS by taking measured points over the 4 CSC stations and building a track.
Measuring the curvature of this track allows us to calculate the momentum of the muon as it bends through the magnetic field.
To get a more accurate p<sub>T</sub> measurement, we would need more data points in the track, and an important one would be measuring the angle of the hit on a chamber instead of only the position.
CSCs alone do not have a good enough resolution to measure the angle of the track accurately for use in the Level 1 trigger.
GEMs are installed on the first station, GE1/1, and sit directly in front of the existing CSCs, ME1/1.
By being placed a short distance away, this effectively makes the CSC system larger and can measure the angle of the track in this combined system, giving a more refined measurement for the eventual p<sub>T</sub> calculation.
To achieve this the two subsystems must be coordinated very carefully.

**My role.**

I produced the first analysis of the successfully working integrated GEM-CSC system.
Using data taken from CMS Run 3 proton-proton collisions I produced an offline analysis showing the effect of using the combined system compared to the previous CSC alone system.
My work showed with very simple integration, the trigger rate could be reduced by roughly a factor of 2 while maintaining the same signal efficiency.
For this work I was awarded a 2025 CMS Award.

**Where it stands.**

Now I manage a team of Ph.D. students working on the CSC Optical Trigger Motherboard putting these algorithms into real firmware and validating the firmware to software agreement.
Open issues involve appropriate timing and spatial alignments between the two systems, correct conversions between different strip topologies, and appropriate matching latency to avoid causing issues downstream.

**References.**
- [CMS DP-2025/069, "Early Look at GEM-CSC Bending Angle Integration into the Level 1 Trigger"](https://gem-dpg-public-results.docs.cern.ch/results/cms-dp-2025-069.html)
- [2025 CMS Awards](https://cms.cern/index.php/news/cms-awards-2025)
