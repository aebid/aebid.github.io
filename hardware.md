---
title: CMS Service
nav_order: 5
permalink: /service/
---

# CMS Service Work

What is CMS Service work.

## Projects

### GEM Alignment

The GEM subsystem is an upgrade and after a successful slice test in Run 2, the full GE1/1 system was installed during Long-Shutdown 2.
All subsystems in CMS need to have a proper alignment so our measured positions match our expected positions for proper particle reconstruction, and as a new subsystem something needed to be developed for GEMs.

**Why it was needed.**

The CMS experiment's particle reconstruction relies on the idea that we know where the measured hits actually came from.
If the detectors become misaligned we may see unphysical effects in the data from things that we know for certain.
One example is the reconstructed di-muon mass of a Z decay.
In a misaligned scenario the very sharp 91 GeV peak of a Z boson would be smeared or shifted purely due to failures in alignment and their effect on reconstruction.
Texas A&M is responsible for alignment of the CMS Muon System, and this included the newly installed GEMs.
The standard technique, track-based muon alignment, propagates a muon from the inner tracker to the desired chamber and measures the difference in positions between propagated and measured hits.
This works well for absolute chamber positions, but the GEM-CSC system is motivated by having a precise relative position to properly measure the bending between chambers.
This meant that the GEM subsystem needed a new alignment method built around the relative GEM-CSC position instead.

**How it works.**

I developed the GEM alignment by propagating CSC segments from ME1/1 backwards to the GEM chamber rather than the standard inner tracker outwards to GEM.
This was motivated by two main components:
First there is much less material between GEM and CSC than there is between the tracker and GEM, greatly reducing the effects of multiple scattering.
Second the reference position becomes the ME1/1 chamber itself, mimicking the relative measurement the trigger system will eventually depend on.

Since GEM strips are radial instead of rectangular, the residual was measured in ΔRφ rather than in Δx.
Each GEM layer was treated as a rigid body with 6 degrees of freedom. Due to the topology of particles traveling through a single plane, the alignable degrees were only δx, δy, and δφz.
This is because the other 3 degrees are weakly constrained by a point measurement.
The 3 alignable degrees are fit using MINUIT in an unbinned likelihood minimizer.

Overall procedure was:
1. Select Muons
2. Measure Residuals
3. Fit Alignments
4. Set Geometry and Repeat

**My role.**

At the start of my Ph.D. there was no alignment plan in place for the GE1/1 system yet.
I developed this method using simulation and 3 available datasets during the Long Shutdown 2:
1. The 2018 Slice Test collision data that included four test GE1/1 chambers installed during Run 2.
2. 2021 CRUZET cosmic ray muons at zero magnetic field.
3. 2022 CRAFT cosmic ray muons at full field.

Through these samples I was able to provide a first alignment for the full system before any collision data was taken with all chambers installed.
From the start of Run 3 the GEM system has had a stable alignment plan.

**Where it stands.**

Since Run 3 has started a new student has taken over the GEM Alignment responsibilities.
The procedure is still running as the default GEM Alignment setup, and I have pushed to the next step of a working GEM-CSC system.
After a reasonable alignment had been measured with collision data, we had the first look into the bending angle of the GEM-CSC system.
This was a step closer to proper trigger integration.

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
- [CMS DP-2025/057, "Measurement of pT Dependent Bending Angles in the CMS GE1/1-ME1/1 system and GE1/1 Alignment Result using 2025 p-p collision data"](https://gem-dpg-public-results.docs.cern.ch/results/cms-dp-2025-057.html)
- [Masters defense, "Alignment of the CMS Gas Electron Multiplier Detector" (July 2022)]({{ '/assets/pdf/devin-aebi-gem-alignment-defense.pdf' | relative_url }})
- [2025 CMS Awards](https://cms.cern/index.php/news/cms-awards-2025)
