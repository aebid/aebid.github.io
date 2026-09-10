---
title: CMS Service
nav_order: 5
permalink: /service/
---

# CMS Service Work

What is CMS Service work.

## Projects

### GEM Alignment

Alignment is the process of adjusting the detector geometry in software to match where the detectors physically sit.
Nothing on the detector moves, the model of it does.

**Why it was needed.**

Every measured hit is compared against a software model of where the detector is supposed to be, so if that model is wrong then everything reconstructed from it is wrong.
The effect shows up directly in physics objects, and a misaligned geometry noticeably degrades the reconstructed di-muon mass of Z candidates.
Texas A&M is responsible for alignment of the CMS Muon System.
The standard technique, track-based muon alignment, propagates a muon outward from the inner tracker and measures the residual between the propagated position and the measured hit position.
That works well for absolute chamber positions, but the GEM-CSC bending angle depends on the position of GE1/1 relative to ME1/1 rather than on either absolute position.
Propagating from the inner tracker also crosses a large amount of material, and the resulting multiple scattering is worst for exactly the low momentum muons that dominate the sample.
The GEM subsystem needed an alignment method built around relative position instead.

**How it works.**

Rather than propagating outward from the inner tracker, the ME1/1 CSC segment is back-propagated to the GEM layer.
Far less material sits between those two detectors, so multiple scattering is much smaller, and the reference position becomes ME1/1 itself, which is the relative measurement the trigger actually depends on.
GEM strips are radial rather than rectangular, so the residual has to be measured in ΔRφ rather than in Δx alone.
Each GEM layer is then treated as a rigid body and three of its six degrees of freedom, δx, δy, and δφz, are fit using a MINUIT unbinned likelihood minimizer.
The procedure iterates: select muons, measure residuals, fit alignment constants, write a new geometry, and repeat until the residuals converge.
Layers are aligned individually rather than as SuperChambers, because cosmic data showed the two layers of a single SuperChamber can sit as much as 500 microns apart.

**My role.**

I developed this alignment method and produced the first alignment of the GE1/1 system.
I validated it first in simulation and then on three datasets with very different conditions: 2018 Slice Test collision data taken with four GE1/1 chambers installed during Run 2, 2021 CRUZET cosmic rays at zero magnetic field, and 2022 CRAFT cosmic rays at full field.
The wide angular range of cosmic muons turned out to be the useful part, letting me constrain degrees of freedom that collision muons alone could not reach.
[State the accuracy you reached here - your resume says 100 microns. It is the number that tells a reader whether the method worked, so it should not be left to the slides.]

**Where it stands.**

The alignment was ready for the start of Run 3 in 2022, and because it feeds CMS object reconstruction it benefits every analysis using muons rather than any single one.
[The 2025 DP note carries a GE1/1 alignment result from p-p collision data, so this clearly did not stop in 2022 - one sentence on where it went would close the gap between the defense and now.]
GE2/1 and ME0 are still to be installed, and both will need new algorithms of their own.

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
