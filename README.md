# Supporting simulation data and code

Supporting materials for **A competence-based multi-mode framework for human–machine decision-making in intelligent construction**.

**Author:** Hezheng Mao, School of Mechanical and Aerospace Engineering, Nanyang Technological University (NTU), Singapore.  
**Funding:** National Natural Science Foundation of China, grant 72301131.  
**Version:** 1.0

## Download

Download **`APIN_supporting_data.zip`** from the [latest release](https://github.com/RedPanda-mhz/APIN-intelligent-construction-data/releases/latest). The complete package is provided as a release asset and contains its own detailed `README.md`, metadata, terminology map and file-level checksum inventory.

| File | Size | SHA-256 |
|---|---:|---|
| `APIN_supporting_data.zip` | 41,578,983 bytes | `1e112db33523a8a12cce7d59b175bbb07a2f97a38f85c0033485d2e106dedfc6` |

The same archive checksum is provided in [SHA256SUMS.txt](SHA256SUMS.txt). The bundled `CHECKSUMS.sha256.json` records the size and SHA-256 of every other file in the package.

## Scope and contents

The package contains simulated construction-plan preferences, calculation and analysis code, parameter records, archived results, feedback trajectories, full-precision matrices for the illustrative case, and source data for Figures 2–5. It examines human-led cooperative coordination with static AI reference assessments. The inputs are synthetic; they are not observations collected at construction sites and do not identify an objectively correct construction plan.

- **360 cases:** two batches, `seen` and `confirmation`, with 180 cases each. Each batch comprises 90 randomization blocks identified by `(m, replicate)`; two scenarios in each block share unaffected random inputs. The global block key is `(split, m, replicate)`. These are not 360 independent random draws.
- Cases use 6, 12 or 24 humans, three static AI assessments and five complete construction plans, in the `balanced_preferences` and `minority_tradeoff` scenarios.
- The main archive records **8,200 method/setting runs**. The formula archive records **3,000 runs** on the same input cases. These repeated calculations do not represent additional independent samples.
- Both batches had been used before the formula/component analyses. The historical `confirmation` label does not indicate a newly unseen validation sample for those analyses.

AI preference matrices remain fixed within each coordination episode. The group center, consensus stopping criterion and final aggregation include humans only.

## Reproduction

Extract the complete ZIP and preserve its relative folder layout. The bundled `README.md` gives the environment, all commands, archived outputs, numerical comparison guidance and historical audit limitations. Run calculations in a working copy because scripts replace outputs beside their inputs.

Main entry points, run from the extracted package root:

```text
python 20260917_positive_trust_full/run_full.py
python 20260917_supplementary_acceptability/formula/run_formula.py
python 20260919_multimode_diagnosis/analyze_multimode.py
```

The first two commands recompute the main and formula runs. The third reconstructs recorded diagnostic states. The bundled README also documents summary analyses, structural-quality component replay and small-case engine checks. Existing results can be inspected without rerunning code.

The original main and formula manifests record Python 3.12.14 and NumPy 2.3.5 on Windows 64-bit. Analysis scripts also require pandas. The packaging import check used pandas 3.0.1; its historical run version was not recorded.

## Terminology

The manuscript's structural-quality measure `SQ` is stored as `CR` in the computational archive:

```text
SQ = CR = CD * NE / (1 + (1 - CD) * (1 - NE))
```

`CD` measures within-submission consistency; `NE` measures preference-priority discrimination. This measure is separate from task competence and is not a reliability probability. Legacy identifiers containing `credibility` refer to the same structural component. See the bundled `TERMINOLOGY_MAPPING.md` for the full mapping.

## Citation

Mao, H. (2026). *Simulation data and code for “A competence-based multi-mode framework for human–machine decision-making in intelligent construction”* (Version 1.0) [Data set and code]. GitHub. [Release v1.0](https://github.com/RedPanda-mhz/APIN-intelligent-construction-data/releases/tag/v1.0).

Cite the specific release version used in your analysis.
