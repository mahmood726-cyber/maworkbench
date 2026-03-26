# Meta-Analysis Workbench

A complete open-access toolkit for evidence synthesis -- from protocol to publication.

[![License: MIT](https://img.shields.io/badge/License-MIT-green.svg)](LICENSE)

## Overview

Meta-Analysis Workbench is the central landing page and navigation hub for a portfolio of 40+ browser-based tools, 8 R packages, and 21 companion papers covering the entire systematic review and meta-analysis pipeline. The workbench organizes tools across 8 workflow stages: Protocol, Search, Extract, Assess Quality, Analyse, Monitor, Validate, and HTA. All browser-based tools are single HTML files that run offline with no installation or server dependencies.

## Workflow Stages

### 1. Protocol
- **PRISMA Checker** -- PRISMA 2020 compliance (27 items, 6 extensions)
- **AdaptSim** -- Adaptive trial design simulator (rpact-validated)
- **MA Power** -- Power and sample size calculator for meta-analyses

### 2. Search
- **CT.gov Search Strategies** -- Clinical trials registry search
- **TrialRadar** -- Trial monitoring for living reviews
- **Rayyan Replacement** -- Browser-based title/abstract screening

### 3. Extract
- **RCT Extractor v10.3** -- Deterministic extraction pipeline (94.6% accuracy, 863 tests)
- **KMcurve** -- Kaplan-Meier curve digitizer with TrOCR neural OCR
- **MetaExtract** -- Study data extraction tool

### 4. Assess Quality
- **RoB Assessor** -- RoB 2 (5 domains) + ROBINS-I (7 domains)
- **AutoGRADE** -- Automated GRADE certainty of evidence
- **Bias Forensics** -- 8 publication bias methods across 307 Cochrane reviews

### 5. Analyse
- **Pooling Suite** -- 10 tau-squared estimators, 3 CI methods, GOSH, Baujat, influence diagnostics
- **PubBias Suite** -- 12 publication bias methods, 3 funnel plot types
- **Meta-Regression** -- Mixed-effects meta-regression with permutation tests
- **Bayesian MA** -- Normal-Normal hierarchical model with prior sensitivity
- **Component NMA** -- Additive component NMA with interaction terms
- **TruthCert PairwisePro** -- Proof-carrying pairwise meta-analysis (101 tests)
- **NMA Suite** -- 22 network meta-analysis variants
- **DTA Pro** -- Diagnostic test accuracy (bivariate GLMM, HSROC)
- **IPD-Meta-Pro** -- Individual patient data meta-analysis (30 modules, 473 tests)
- **Dose-Response NMA** -- GLS dose-response meta-analysis (120 R parity tests)
- **MultiverseMA** -- Multiverse meta-analysis (36K specifications)
- **CausalSynth** -- Causal evidence triangulation
- **MAPriors** -- MAP prior and dynamic borrowing
- And more

### 6. Monitor
- **Al-Mizan** -- Evidence equipoise monitor (cumulative MA + TSA + fragility)
- **Living-Meta** -- Living meta-analysis with CUSUM
- **CardioOracle** -- Cardiovascular trial outcome predictor

### 7. Validate
- **MetaReproducer** -- Automated reproducibility audit (501 Cochrane MAs)
- **Fragility Atlas** -- Multiverse robustness of 407 Cochrane MAs
- **Asa v2.0** -- Forensic data integrity screener (7 statistical tests, 85 tests)
- **BenfordMA** -- Benford's Law digit forensics
- **Evidence Half-Life** -- Cumulative multiverse stability analysis

### 8. HTA
- **HTA Artifact Standard** -- 41 decision-analytic engines (3,337 tests)
- **HTA Evidence Integrity** -- Evidence integrity suite
- **HTA Transportability** -- Cross-jurisdiction transportability engine

## Quick Start

1. Download `index.html`
2. Open in any modern browser
3. Click any tool card to navigate to the individual tool
4. No installation, no dependencies, works offline

## Cross-Tool Interoperability

All analysis tools support the **Meta-Analysis Interchange Format (MAIF)** -- a common JSON schema for exchanging study-level data. Export from one tool and import into the next for a seamless workflow.

## Screenshots

> Screenshots can be added by opening the tool and using browser screenshot.

## Stats

- 115+ projects in the portfolio
- 40+ browser-based tools
- 8 R packages
- 21 papers ready for submission

## Citation

If you use this workbench, please cite:

> Ahmad M. Meta-Analysis Workbench: A complete open-access toolkit for evidence synthesis. 2026. Available at: https://github.com/mahmood726-cyber/ma-workbench

## Author

**Mahmood Ahmad**
Royal Free Hospital, London, United Kingdom
ORCID: [0009-0003-7781-4478](https://orcid.org/0009-0003-7781-4478)

## License

MIT
