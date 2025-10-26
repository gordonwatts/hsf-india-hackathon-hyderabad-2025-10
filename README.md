# Resources for a Hackathon around building structured Awkward Data

Held as part of the [HSF-India](https://research-software-collaborations.org/) series on the week of [2025-10-27 in Hyderabad](https://indico.cern.ch/event/1580053/timetable/).

## Hackathon Goals

Flat, jagged, ntuple data is written as as series of linear arrays. While this is I/O and computationally efficient - leading to expressive and fast code - it is not always intuitive. This is escpecially true in particle physics, where we group columns together by object. For example:

## Data files

We are using the EIC simulation file `root://dtn-eic.jlab.org//volatile/eic/EPIC/RECO/25.10.0/epic_craterlake/DIS/NC/18x275/minQ2=10/pythia8NCDIS_18x275_minQ2=10_beamEffects_xAngle=-0.025_hiDiv_5.2623.eicrecon.edm4eic.root` for the actual hackathon, but anything from them could be used. It is 170 MB.
