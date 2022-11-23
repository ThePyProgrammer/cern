# Intro to HEP Computing

> _by John Apostolakis_

## Past HEP Experiments
- Cyclotrons but very small (e.g. 69cm)
- Bubble Chamber (supercool fluid with charged particles sent, exploring the movement and reactions of said particles)

## Modern HEP Experiments

A lot of experiments:
- ATLAS
- CMS
- LHCb (also unusual cuz why not, archives data)
- ALICE
- newer ones


"cameras" (sub-detectors) take "snapshots" (event fragments), then we piece together said fragments to get an idea of the full event, full event image then pushed to storage for offline analysis.

### How do we determine if image is useful?
(thanks shanay) if the event isn't head-on, e.g. particles grazed past each other, data isn't useful. If head-on collision is useful, the computer system determines that the data is "interesting" (triggers based on thresholds).

### Why is there so much data?

Proton-Proton collisions in LHC have a crossing rate of 40 MHz, and a 7 TeV beam energy, hence we found that the collision rate is about $10^7 - 10^9$ Hz. Thus, the windows of recordings are around (sometimes smaller than) 50 ns. In addition, there are $10^4 - 10^5$ channels, which causes there to be a large amount of data produced for not enough storage space (even with WLCG).

How to avoid noise: High Pass-Filter moment.

## Selection

Frequenices vary a lot:

|Event|$f$|
|---|---|
|Inelastic Event|$10^9 \text{ Hz}$|
|$W \rightarrow l\text{  }v$|$10^2\text{ Hz}$|
|top quark production|$10 \text{ Hz}$|
|Higgs production of $m = 100 \text{ GeV/c}^2$|$1 \text{ Hz}$|
|Higgs production of $m = 600 \text{ GeV/c}^2$|$0.1 \text{ Hz}$|

### Level-1 Trigger

Always online, use ASIC and FPGA :thinking: to compute proper filtered values at a very fast rate ($t = 10^{-9} - 10^{-3}$ s). These hardware pieces are very expensive (thousands of bucks each), but they're worth it because the data is well-filtered (very obviously useless data does not waste time).


### High-Level Triggers

Large scale of processors that are also largely online, take a lot more time that Level-1 Triggers to process the data.

### Reconstruction and Analysis

Done days, months, years after data collection to look through said data, highest level since human is doing it. A very offline techique.


## Overall Data Processing Structure

1. Raw Data is determined from selected data and event simulation (which is fitted to the selected event probabilistically via something like Geant4)
2. Event is reconstructed via this raw data, and is stored with the original selected data into the Event Summary Data (ESD)
3. Physical analyses are applied in batches on these ESDs to form Analysis Object Data (AOD) which can be re-retrieved via an array of computers


## Technologies used
- LHC Collaboration Code
- OOP languages, frameworks
- Reuse generic and domain-specific open-source packages
- 

## Reconstruction

Reconstruction deals with translating a "soup" of data into a proper signature summary of how the motion takes place. Selectivity is roughly 1 in $10^{12}$. One can use 2 different detectors to determine the path of the particles (using a Kalman Filter)

## Simulation

They use Monte Carlo Simulations






### Question Bank





