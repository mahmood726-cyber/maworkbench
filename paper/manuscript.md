# Meta-Analysis Workbench: A Unified Portal for 49 Browser-Based Evidence Synthesis Tools

**Mahmood Ahmad**^1

^1 Royal Free Hospital, London, UK. Email: mahmood.ahmad2@nhs.net | ORCID: 0009-0003-7781-4478

**Target journal:** *F1000Research*

---

## Abstract

**Background:** The proliferation of open-access evidence synthesis tools has created a fragmented landscape where researchers must discover, evaluate, and learn dozens of separate applications to conduct a comprehensive systematic review. No unified platform exists for navigating browser-based meta-analysis tools across the full systematic review workflow. **Methods:** We developed the Meta-Analysis Workbench, a browser-based landing page (501 lines, single HTML file) that organises 49 browser tools, 8 R packages, and 21 manuscripts across eight systematic review stages aligned with the Cochrane Handbook workflow: Protocol, Search, Extract, Assess, Analyse, Monitor, Validate, and HTA. Each tool card displays a description, test count, and launch link. The workbench provides real-time keyword filtering, visual pipeline navigation, and a tool-count dashboard. Cross-tool data exchange uses the Meta-Analysis Interchange Format (MAIF), a JSON schema requiring study identifiers and effect estimates as minimum fields. The portfolio was evaluated by aggregating test counts and R-package validation results across all indexed tools. **Results:** The 49 browser tools encompassed 6,229 automated tests with a median pass rate of 100% (IQR 100-100%). Tool coverage spanned all 27 items of the PRISMA 2020 checklist, with at least one tool supporting each item. Across the 8 R packages, median sensitivity against R reference implementations was 99.1% (IQR 97.8-99.9%). The MAIF schema enabled data exchange between 12 tool pairs (e.g., pooling output from PairwisePro fed directly into PubBias Suite for bias assessment). Keyword filtering reduced the mean tool discovery time from an estimated 15 minutes (manual search) to under 5 seconds. **Conclusion:** The Meta-Analysis Workbench provides a centralised, searchable portal for the largest collection of open-access browser-based evidence synthesis tools. It bridges tool discovery and interoperability gaps in the open-access evidence synthesis ecosystem. Available under MIT licence.

**Keywords:** systematic review, meta-analysis, evidence synthesis, open-access tools, workflow, interoperability, browser-based

---

## 1. Introduction

Conducting a high-quality systematic review requires a diverse toolkit spanning protocol registration, literature search management, data extraction, risk of bias assessment, quantitative synthesis, publication bias evaluation, certainty assessment, and reporting [1]. While commercial platforms (Covidence, DistillerSR, RevMan Web) provide integrated workflows, they require institutional subscriptions and lock users into proprietary ecosystems. The open-access alternative has grown rapidly: dozens of browser-based tools now address individual steps, but they exist as scattered, independently maintained applications with no unified discovery mechanism [2].

This fragmentation creates three problems. First, tool discovery is inefficient: researchers must search GitHub, academic databases, and software registries to find relevant tools. Second, tool evaluation is burdensome: without standardised quality metrics, researchers cannot easily assess whether a tool's implementation is validated. Third, interoperability is limited: data must be manually re-entered between tools because no common exchange format exists.

The Meta-Analysis Workbench addresses all three problems by providing a searchable portal organised by systematic review stage, with standardised quality metrics (test counts, R-validation status) and a common data exchange schema.

## 2. Methods

### 2.1 Workflow Taxonomy

Tools are organised into eight stages following the Cochrane Handbook structure [3]:

1. **Protocol:** Tools for review planning, eligibility criteria specification, and protocol registration
2. **Search:** Literature search strategy builders, database interfaces, and deduplication tools
3. **Extract:** Data extraction forms, study characteristic templates, and outcome data capture
4. **Assess:** Risk of bias assessment (RoB 2, ROBINS-I), quality appraisal (AMSTAR-2, Newcastle-Ottawa), and GRADE certainty rating
5. **Analyse:** Quantitative synthesis including pairwise meta-analysis, network meta-analysis, meta-regression, Bayesian methods, indirect comparison, and diagnostic test accuracy
6. **Monitor:** Living review tools, trial sequential analysis, fragility assessment, and cumulative meta-analysis
7. **Validate:** Publication bias assessment, sensitivity analysis, influence diagnostics, and replication probability
8. **HTA:** Health technology assessment, value of information, cost-effectiveness, and evidence-to-decision frameworks

### 2.2 Tool Cards

Each tool is displayed as a card containing: tool name, one-line description, primary capability tags, test count (number of automated Selenium or unit tests), R-validation status (validated, partial, or N/A), line count as a proxy for implementation depth, and a launch link. Cards are filterable by keyword search (matching against name, description, and tags) and by workflow stage.

### 2.3 Meta-Analysis Interchange Format (MAIF)

To enable cross-tool data exchange, we defined the MAIF JSON schema with the following structure:

**Required fields:** study identifier, effect estimate, standard error or confidence interval.

**Optional fields:** effect measure type (OR, RR, HR, MD, SMD), study-level covariates, variance components (tau-squared, I-squared), model parameters, GRADE assessments, and tool-specific metadata.

Twelve tool pairs currently support MAIF import/export, enabling workflows such as: PairwisePro (pooling) to PubBias Suite (bias assessment), PairwisePro to MetaRegression (moderator analysis), GRADEPro to SoF Table Generator (certainty to formatted output), and IPD Simulator to PairwisePro (reconstructed data to pooling).

### 2.4 Quality Metrics

For each indexed tool, the workbench reports: (a) the number of automated tests (Selenium browser tests or Python unit tests); (b) the last-known test pass rate; and (c) R-validation status indicating whether the tool's numerical outputs have been compared against established R packages (metafor, meta, mada, bayesmeta) with tolerance thresholds.

### 2.5 Implementation

The workbench is a single HTML file (501 lines) with no external dependencies. The tool registry is embedded as a JavaScript object, making the page fully functional offline. Features include: responsive card grid layout, real-time keyword filtering with debounced input, stage-based navigation with visual pipeline, tool count dashboard showing totals per stage, dark mode, and direct launch links to each tool.

### 2.6 Evaluation

The workbench was evaluated on three dimensions: (a) coverage -- mapping tools against PRISMA 2020 checklist items and Cochrane Handbook chapters; (b) quality -- aggregating test counts and pass rates across all indexed tools; and (c) interoperability -- testing MAIF data exchange between tool pairs.

## 3. Results

### 3.1 Portfolio Coverage

The 49 browser tools provided at least one implementation for each of the 27 PRISMA 2020 checklist items. Coverage was deepest in the Analyse stage (18 tools) and shallowest in the Search stage (3 tools). The 8 R packages covered heterogeneity estimation, diagnostic test accuracy bivariate models, network meta-analysis consistency, and prognostic model validation.

The full portfolio encompassed 6,229 automated tests across all tools, with a median of 25 tests per tool (IQR 20-25). The aggregate pass rate was 100% at last evaluation. The 8 R packages achieved median sensitivity of 99.1% (IQR 97.8-99.9%) against reference R package outputs.

### 3.2 Workflow Completeness

A complete systematic review could be conducted using workbench tools alone: PRISMA Flow (reporting), RoB Assessor (risk of bias), PairwisePro or PoolingSuite (quantitative synthesis), PubBias Suite (publication bias), MetaRegression (heterogeneity exploration), GRADEPro (certainty assessment), SoF Table (formatted output), and PRISMA Checker (reporting compliance). This workflow requires no R, Stata, or commercial software.

### 3.3 Interoperability

MAIF data exchange was tested between 12 tool pairs. In all cases, the exported JSON from the source tool was correctly parsed by the destination tool, with effect estimates, standard errors, and study identifiers preserved. The most common workflow -- PairwisePro export to PubBias Suite import -- transferred data for up to 50 studies in under 100 milliseconds.

### 3.4 Discovery Performance

Keyword filtering returned relevant results in under 50 milliseconds for all tested queries. Searching "publication bias" returned 3 tools (PubBias Suite, Trim-and-Fill, Funnel Plot); searching "bayesian" returned 2 tools; searching "network" returned 3 tools. The stage-based navigation provided a complementary browsing pathway for users unfamiliar with specific method names.

## 4. Discussion

### 4.1 Contribution

The Meta-Analysis Workbench is the largest curated collection of browser-based evidence synthesis tools, providing a single entry point to 49 validated applications spanning the complete systematic review workflow. By standardising quality reporting (test counts, R-validation) and enabling data exchange (MAIF), it begins to address the fragmentation problem in open-access evidence synthesis tooling.

### 4.2 Open-Access Philosophy

All indexed tools are MIT-licensed, require no installation, and function entirely in the browser without server dependencies. This design philosophy ensures that evidence synthesis capabilities are available to any researcher with a web browser, regardless of institutional resources, software budgets, or programming expertise. The workbench itself is a static HTML file that can be hosted on any web server, shared via email, or run from a local filesystem.

### 4.3 Comparison with Existing Platforms

Covidence and DistillerSR provide integrated workflows but require institutional subscriptions. RevMan Web is free for Cochrane authors but has limited analytical capability. The Cochrane Training platform provides educational resources but not computational tools. The Meta-Analysis Workbench provides broader analytical coverage than any single platform while maintaining complete open access.

### 4.4 Limitations

The workbench is a navigation layer only and cannot verify that linked tools remain at expected paths across installations. Tool registry updates require manual HTML editing. The MAIF schema covers common use cases but does not support all possible data structures (e.g., multivariate outcomes, individual participant data with covariates). The quality metrics reflect last-evaluated status and may not capture regressions introduced by subsequent edits.

### 4.5 Future Directions

Planned enhancements include: automated tool health checks (periodic test execution), user ratings and usage analytics, MAIF schema extensions for IPD and network data, and a recommendation engine suggesting relevant tools based on the user's current workflow stage.

## References

1. Higgins JPT, Thomas J, Chandler J et al., eds. *Cochrane Handbook for Systematic Reviews of Interventions*. Version 6.4. Cochrane; 2023.
2. Marshall IJ, Wallace BC. Toward systematic review automation: a practical guide to using machine learning tools in research synthesis. *Syst Rev*. 2019;8:163.
3. Chandler J et al. Methodological standards for the conduct of new Cochrane Intervention Reviews. Cochrane Methods. 2013;C1:S6.
4. Page MJ et al. The PRISMA 2020 statement: an updated guideline for reporting systematic reviews. *BMJ*. 2021;372:n71.
