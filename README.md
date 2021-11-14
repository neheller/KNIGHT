# KNIGHT

The official repository holding the data for the [ISBI 2022 KNIGHT Challenge](https://research.ibm.com/haifa/Workshops/KNIGHT/)

## About

The KNIGHT Challenge asks teams to develop models to classify patients with kidney tumors in terms of their "risk score" as defined by the recently-release [American Urological Association (AUA) Guidelines for Renal Masses](https://www.auanet.org/guidelines/guidelines/renal-mass-and-localized-renal-cancer-evaluation-management-and-follow-up). KNIGHT makes use of the imaging and clinical data from the [MICCAI KiTS21 Challenge](https://kits21.kits-challenge.org/).

## Accessing the Data

A JSON file with each patient's clinical data lives in this repository at `/knight/data/knight.json`. The imaging associated with each of the 300 patients can be downloaded with the `/knight/scripts/get_imaging.py` script.

If you wish to make use of the segmentations used for the KiTS21 challenge, you can access those by cloning the [official KiTS21 repository](https://github.com/neheller/kits21).

The prediction target for the KNIGHT challenge is the attribute entitled `"aua_risk_group"` in the `knight.json` file. The primary task is a binary classification between the two higher-risk groups (`"high_risk"` and `"very_high_risk"`) versus the three lower-risk groups (`"benign"`, `"low_risk"`, and `"intermediate_risk"`). A secondary task is the five-way classification problem for each group individually.

Participants are encouraged to make use of the clinical data as well as the imaging in order to make their predictions. The following clinical attributes will be made available at inference time for cases in the test set.

- `"age_at_nephrectomy"`
- `"gender"`
- `"body_mass_index"`
- `"comorbidities"`
- `"smoking_history"`
- `"age_when_quit_smoking"`
- `"pack_years"`
- `"chewing_tobacco_use"`
- `"alcohol_use"`
- `"last_preop_egfr"`
- `"radiographic_size"`
- `"voxel_spacing"`

All other attributes will NOT be made available and participants should not train models that take as inputs any clinical attributes not listed above.
