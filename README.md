# Resources for a Hackathon around building structured Awkward Data

Held as part of the [HSF-India](https://research-software-collaborations.org/) series on the week of [2025-10-27 in Hyderabad](https://indico.cern.ch/event/1580053/timetable/).

## Hackathon Goals

Flat, jagged, ntuple data is written as as series of linear arrays. While this is I/O and computationally efficient - leading to expressive and fast code - it is not always intuitive. This is escpecially true in particle physics, where we group columns together by object. For example:

```text
    "TaggerTrackerReconstructedParticles.type": var * int32,
    "TaggerTrackerReconstructedParticles.energy": var * float32,
    "TaggerTrackerReconstructedParticles.momentum.x": var * float32,
    "TaggerTrackerReconstructedParticles.momentum.y": var * float32,
    "TaggerTrackerReconstructedParticles.momentum.z": var * float32,
    "TaggerTrackerReconstructedParticles.referencePoint.x": var * float32,
    "TaggerTrackerReconstructedParticles.referencePoint.y": var * float32,
    "TaggerTrackerReconstructedParticles.referencePoint.z": var * float32,
    "TaggerTrackerReconstructedParticles.charge": var * float32,
    "TaggerTrackerReconstructedParticles.mass": var * float32,
 ```

 You'd really like to refer to all tracks as `event.tracks.px` or similar, or `.pt`.

 In python one can use `behaviors` to implement this functionality. This hackathon focuses on building that code.

 1. Understanding how to use `ak.zip` and `ak.Record` to build a more sensible event data model
 1. Learning about `mixins` both built-in (from the `vector` package) to add functionality.
 1. Learning how `awkward-zipper` can do some of this automatically for us.
 1. Automation - both by writing out flat ntuples that better handle this and using LLM's to generate this EDM construction code.

## Data files

We are using the EIC simulation file `root://dtn-eic.jlab.org//volatile/eic/EPIC/RECO/25.10.0/epic_craterlake/DIS/NC/18x275/minQ2=10/pythia8NCDIS_18x275_minQ2=10_beamEffects_xAngle=-0.025_hiDiv_5.2623.eicrecon.edm4eic.root` for the actual hackathon, but anything from them could be used. It is 170 MB.

## Environment Setup

- Install [Miniconda](https://docs.conda.io/en/latest/miniconda.html) or [Anaconda](https://www.anaconda.com/products/distribution) if you don't have it already.
- Create a new conda environment with Python 3.12:
  ```bash
  conda create -n my-env python=3.12 -y
  conda activate my-env
  ```

- Install the required packages:
  ```bash
  pip install -r requirements.txt
  ```