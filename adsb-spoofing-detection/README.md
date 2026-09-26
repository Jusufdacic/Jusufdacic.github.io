# Beyond Accuracy: Robustness and Operational Relevance of ML/DL-based ADS-B Spoofing Detection

**Jusuf Dacić, Nejra Kapidžija**
Faculty of Traffic and Communications, University of Sarajevo
*International Conference on Advances in Traffic and Communication Technologies (ATCT), 2026*

📄 **[Read the full paper (PDF)](Jusuf_Nejra_ATCT.pdf)**

---

## Overview

ADS-B (Automatic Dependent Surveillance–Broadcast) is a core air traffic surveillance technology, but its messages are broadcast without cryptographic authentication. This makes false-message injection, identity impersonation, and trajectory manipulation possible.

Many machine learning and deep learning detectors report accuracy above 95% against these attacks. This paper asks a different question: **what evidence do these detectors actually provide about their robustness and operational relevance, beyond reported accuracy?**

## What I Did

- Conducted a **systematic literature review** following the PRISMA 2020 reporting principle
- Searched IEEE Xplore, ScienceDirect, and Google Scholar (255 records → 242 unique → **19 papers** in the final corpus, 2021–2026)
- Designed a **criterion-based assessment framework** with five research questions covering:
  - data and attack provenance
  - adversarial robustness
  - false-alarm reporting
  - timing performance
  - generalization to unseen routes, regions, and attacks
- Performed independent double screening and data extraction, with final classification by consensus
- Analyzed metric definitions (FPR vs. FAR vs. specificity) and illustrated how low attack prevalence collapses alert precision
- Formulated concrete recommendations for future evaluation practice

## Key Findings

| Research question | Finding |
|---|---|
| **Data provenance** | 17 of 18 papers with clear provenance use real flights with *constructed* attacks. No confirmed operational spoofing attack was found in any dataset. |
| **Adversarial robustness** | **0 of 17** detector papers test attacks targeting the model itself. In one attack study, LSTM accuracy dropped from 90.09% to 51.44% (near chance) and recovered only to 75.43% after adversarial training. |
| **False alarms & timing** | 10 of 17 report a false-alarm indicator, but definitions differ. 6 report computational timing; only 1 measures messages-to-detection. |
| **Generalization** | Only 1 paper performs external spatial evaluation; 2 more provide partial evidence. |
| **Evaluation gaps** | Unrealistic threat models, possible data leakage from random splits, inconsistent metrics, and no false-alerts-per-hour reporting. |

**Illustrative example:** with 99% recall and just 0.1% FPR, if only 0.1% of messages are attacks, **about half of all alerts are false** (precision ≈ 49.8%).

## Recommendations

- Separate benign data provenance from attack construction and state an explicit threat model
- Test detectors against adaptive attacks, including attacks aware of the defense
- Report false alerts per hour/flight and detection delay under realistic load
- Split data by flight, time, and region to avoid leakage; test on external routes and regions
- Share code, data versions, and variance across runs

## Keywords

`ADS-B` · `spoofing` · `machine learning` · `deep learning` · `adversarial robustness` · `generalization` · `aviation cybersecurity` · `systematic review`

## License

This work is licensed under a [Creative Commons Attribution 4.0 International License](https://creativecommons.org/licenses/by/4.0/).
