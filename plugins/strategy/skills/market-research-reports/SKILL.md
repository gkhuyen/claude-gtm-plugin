---
name: market-research-reports
description: "Use this skill when generating comprehensive market research reports (50+ pages) in the style of top consulting firms (McKinsey, BCG, Gartner). Features professional LaTeX formatting, visual generation, and multi-framework analysis including Porter's Five Forces, PESTLE, SWOT, TAM/SAM/SOM, and BCG Matrix."
allowed-tools: [Read, Write, Edit, Bash]
---

# Market Research Reports

## Overview

Generates professional-grade market research reports (50+ pages) modeled on McKinsey, BCG, Gartner, and Forrester deliverables. Reports are data-driven, visual-rich, and formatted in LaTeX using the `market_research.sty` style package.

**Key features:** Multi-framework analysis (Porter's Five Forces, PESTLE, SWOT, BCG Matrix, TAM/SAM/SOM), 5-6 core diagrams generated upfront, consulting-quality typography, actionable recommendations with implementation roadmaps.

**Use when:** creating market analysis for investment decisions, competitive landscapes, market sizing, M&A due diligence, GTM strategy, or product launch business cases.

---

## Visual Generation

Generate **6 priority visuals before writing**. Use `scientific-schematics` for diagrams and `generate-image` for infographics.

| Priority | Visual | Tool |
|----------|--------|------|
| 1 | Market growth trajectory (bar chart, historical + projected) | scientific-schematics |
| 2 | TAM/SAM/SOM concentric circles | scientific-schematics |
| 3 | Porter's Five Forces (High/Medium/Low ratings) | scientific-schematics |
| 4 | Competitive positioning matrix (2x2) | scientific-schematics |
| 5 | Risk heatmap (probability vs impact) | scientific-schematics |
| 6 | Executive summary infographic | generate-image |

```bash
# Example: TAM/SAM/SOM diagram
python skills/scientific-schematics/scripts/generate_schematic.py \
  "TAM SAM SOM concentric circles: TAM $50B outer, SAM $15B middle, SOM $3B inner, blue gradient" \
  -o figures/02_tam_sam_som.png --doc-type report

# Batch generate all visuals
python skills/market-research-reports/scripts/generate_market_visuals.py \
  --topic "[MARKET NAME]" --output-dir figures/
```

Additional visuals to generate per section as needed: ecosystem/value chain, regional breakdown, PESTLE diagram, market share chart, customer segmentation, technology roadmap, regulatory timeline, opportunity matrix, implementation Gantt, financial projections.

---

## Report Structure (50+ Pages)

### Front Matter (~5 pages)
- **Cover page**: title, hero visual, date, prepared for/by
- **Table of Contents** (auto-generated with List of Figures, List of Tables)
- **Executive Summary** (2-3 pages): market snapshot box, investment thesis, key findings, top 3-5 recommendations, executive infographic

### Core Analysis (~35 pages)

| Chapter | Pages | Required Visuals | Key Frameworks |
|---------|-------|-----------------|----------------|
| 1. Market Overview & Definition | 4-5 | Ecosystem/value chain, industry structure | — |
| 2. Market Size & Growth | 6-8 | Growth chart, TAM/SAM/SOM, regional breakdown, segment growth | TAM→SAM→SOM |
| 3. Industry Drivers & Trends | 5-6 | Trends timeline, driver impact matrix, PESTLE diagram | PESTLE |
| 4. Competitive Landscape | 6-8 | Porter's Five Forces, market share, positioning matrix, strategic groups | Porter's, BCG |
| 5. Customer Analysis | 4-5 | Segmentation chart, attractiveness matrix, customer journey | Value Prop Canvas |
| 6. Technology & Innovation | 4-5 | Technology roadmap, adoption/hype cycle | TRL, Hype Cycle |
| 7. Regulatory & Policy | 3-4 | Regulatory timeline | — |
| 8. Risk Analysis | 3-4 | Risk heatmap, mitigation matrix | Risk Register |

### Strategic Recommendations (~10 pages)

| Chapter | Pages | Key Frameworks |
|---------|-------|----------------|
| 9. Strategic Opportunities | 4-5 | Opportunity matrix, Build/Buy/Partner, Impact vs Effort |
| 10. Implementation Roadmap | 3-4 | Phased Gantt, milestone tracker |
| 11. Investment Thesis & Projections | 3-4 | Scenario analysis, sensitivity |

### Back Matter (~5 pages)
- Appendix A: Methodology & data sources
- Appendix B: Detailed market data tables
- Appendix C: Company profiles
- References/Bibliography (BibTeX)

---

## Workflow

### Phase 1: Research (T-12 to T-8 weeks)
1. Define scope: market definition, geography, time horizon, key questions
2. Use `research-lookup` for market size/CAGR, competitive landscape, trends, regulatory data
3. Organize into `sources/` folder; identify and close data gaps

### Phase 2: Analysis
4. Apply frameworks: TAM→SAM→SOM with clear assumptions; Porter's Five Forces (rate each High/Medium/Low); PESTLE per dimension; SWOT; competitive positioning (define axes, plot competitors)
5. Synthesize insights, develop prioritized recommendations

### Phase 3: Visual Generation
6. Generate all 6 priority visuals before writing; add section-specific visuals during writing

### Phase 4: Writing
7. Initialize project structure:
```
writing_outputs/YYYYMMDD_HHMMSS_market_report_[topic]/
├── progress.md
├── drafts/v1_market_report.tex
├── references/references.bib
├── figures/
├── sources/
└── final/
```
8. Use `assets/market_report_template.tex` as base. Write fully — no abbreviations, all claims sourced, consulting-style active voice, insights first then data.

### Phase 5: Compilation & Review
9. Compile:
```bash
cd writing_outputs/[project]/drafts/
xelatex v1_market_report.tex && bibtex v1_market_report
xelatex v1_market_report.tex && xelatex v1_market_report.tex
```
10. Quality check: 50+ pages, all visuals render, bibliography complete, no orphaned figures, all data sourced

---

## Quality Standards

**Page targets:** Front matter 5, Market Overview 5, Market Size 7, Drivers 6, Competitive 7, Customer 5, Technology 5, Regulatory 4, Risk 4, Recommendations 5, Roadmap 4, Investment 4, Back matter 5 = **66 pages target**

**Data:** No older than 2 years; all statistics attributed; cross-referenced; projections state assumptions; limitations acknowledged.

**Writing:** Balanced/objective; avoid jargon; specific numbers over vague qualifiers; clear headings and transitions; actionable recommendations.

**Visuals:** 300 DPI minimum; colorblind-friendly palette; consistent color scheme; all axes/legends labeled; sources in captions.

---

## LaTeX Formatting

```latex
\documentclass[11pt,letterpaper]{report}
\usepackage{market_research}

% Colored box environments
\begin{keyinsightbox}[Key Finding]...\end{keyinsightbox}      % blue
\begin{marketdatabox}[Market Snapshot]...\end{marketdatabox}  % green
\begin{riskbox}[Critical Risk]...\end{riskbox}                % orange
\begin{recommendationbox}[Recommendation]...\end{recommendationbox} % purple
\begin{calloutbox}[Definition]...\end{calloutbox}             % gray

% Figure
\includegraphics[width=0.9\textwidth]{../figures/market_growth.png}

% Table: use booktabs + \rowcolor{tablealt} for alternating rows
```

See `assets/FORMATTING_GUIDE.md` for complete reference.

---

## Integration

- **research-lookup**: market data, competitive intelligence
- **scientific-schematics**: all diagrams and charts
- **generate-image**: infographics and cover imagery
- **peer-review**: evaluate completeness and quality
- **citation-management**: BibTeX reference management

---

## Pre-Submission Checklist

**Structure:** Cover page, ToC, List of Figures/Tables, Executive Summary, all 11 chapters, 3 appendices, bibliography.

**Core visuals (6):** Market growth, TAM/SAM/SOM, Porter's Five Forces, competitive positioning, risk heatmap, exec infographic.

**Content quality:** All statistics sourced, projections include assumptions, frameworks properly applied, recommendations actionable, no placeholder sections.

**Technical:** PDF compiles without errors, all figures render, cross-references work, page count >50.

---

## Troubleshooting

| Problem | Solution |
|---------|----------|
| Under 50 pages | Expand appendix data tables, add regional breakdowns, more company profiles |
| Visuals not rendering | Check file paths, ensure images in `figures/`, verify extensions |
| Missing bibliography | Run `bibtex` after first `xelatex` pass; check `.bib` syntax |
| Table/figure overflow | Use `\resizebox` or `adjustbox`, reduce image width |
| Poor visual quality | Add `--doc-type report`; try `--iterations 5` |
