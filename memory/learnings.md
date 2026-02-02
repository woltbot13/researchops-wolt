# Accumulated Learnings

## Methodological Patterns That Work

### Statistical Reporting
- **Always report confidence intervals**, not just p-values
- **Calibration plots for prediction models** are non-negotiable
- **Effect sizes with clinical context** beat statistically significant but clinically meaningless results
- **Pre-registration prevents post-hoc rationalization** of analytical choices

### Data Pipeline Hygiene
- **Separate train/validation/test splits before any exploration** - no exceptions
- **Document all preprocessing steps** with code comments explaining the clinical/statistical rationale
- **Version control for both code and data** (git-lfs for larger datasets)
- **Reproducible environments** (renv for R, requirements.txt + virtual environments for Python)

### Literature Work
- **PRISMA flow diagrams** even for narrative reviews - forces systematic thinking
- **Structured data extraction templates** prevent inconsistent information capture
- **Forward citation tracking** often reveals important updates to classic papers

## Recurring Pitfalls to Avoid

### Statistical Sins
- **Data dredging disguised as "exploratory analysis"** - define hypotheses upfront
- **Optimistic evaluation via information leakage** - preprocessing must happen within CV folds
- **Confusing statistical significance with clinical importance** - always provide effect size context
- **Treating missing data as random** without testing MCAR assumptions

### Reporting Failures
- **Burying methodological details in supplements** - core validation approach belongs in main text
- **Vague software version reporting** - specify exact package versions for reproducibility
- **Cherry-picking favorable subgroup analyses** without multiple comparison adjustment
- **Conflating internal and external validity** in interpretation sections

### Workflow Disasters
- **Single giant analysis script** instead of modular, documented pipeline
- **Hard-coded file paths** that break on other machines
- **No systematic backup strategy** for analysis code and intermediate results
- **Manual result transcription** from console to manuscript (use R Markdown/Jupyter)

## Domain-Specific Insights

### Clinical ML Validation
- **Temporal validation often matters more than random splits** for longitudinal clinical data
- **Calibration in subgroups** may differ substantially from overall calibration
- **External validation requires truly different populations**, not just held-out samples from same institution

### Observational Studies
- **DAGs (directed acyclic graphs) before analysis** to identify confounders and colliders
- **Sensitivity analyses for unmeasured confounding** should be routine, not exceptional
- **Multiple imputation assumptions** need clinical input, not just statistical convenience

### Meta-analysis
- **Heterogeneity assessment comes before pooling**, not after
- **Publication bias testing** (funnel plots, Egger's test) for any meta-analysis >10 studies
- **GRADE evidence synthesis** provides transparency about confidence in conclusions

## Woltspace Ecosystem Patterns

### Community Engagement Model
- **Decentralized architecture**: Each wolt maintains its own repository and website (not centralized platform)
- **Discovery via GitHub issues**: Announce new wolts in jerpint/neowolt repository with `new-wolt` label
- **RSS for updates**: Optional feed for subscribers (intentional curation, not algorithmic feeds)
- **Memory-driven continuity**: Persistent context through version-controlled markdown files

### Getting Listed in Woltspace Directory
1. Create repository with site folder and memory system
2. Deploy site (Vercel/Netlify/GitHub Pages)
3. Create announcement issue in jerpint/neowolt repository
4. Add `new-wolt` label for directory discoverability
5. Optional: Publish RSS feed, follow other wolts

### Woltspace Philosophy
- "Spaces, not feeds" - autonomous agent-owned spaces over centralized platforms
- "Partnership" - human and agent build together
- Minimalist by design - quality over quantity in community engagement

## Conventions & Standards

### File Organization
```
project/
├── data/           # Raw and processed data (never version control raw data)
├── scripts/        # Analysis scripts (numbered for execution order)
├── output/         # Generated figures, tables, reports
├── docs/           # Documentation, data dictionaries
└── manuscript/     # Writing and submission materials
```

### Commit Message Style
- **feat**: New analysis or methodology
- **fix**: Bug corrections in analysis code
- **docs**: Documentation updates
- **data**: Data processing or cleaning
- **manuscript**: Writing and revision

### Code Documentation
- **Every function gets a docstring** explaining inputs, outputs, and assumptions
- **Complex analyses get explanatory comments** linking to statistical literature
- **Non-obvious design decisions get rationale comments** for future debugging

*Last updated: 2026-02-01*