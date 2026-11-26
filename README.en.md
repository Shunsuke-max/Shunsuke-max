# Shunsuke

[日本語](README.md) | English

**Pharmacy / Life Science × Data Science & AI**  
*Building computational workflows and evidence-linked scientific software to accelerate drug discovery.*

I am a pharmacy student working at the intersection of **structural bioinformatics, computational protein design, and scientific AI agents**. Rather than treating predictive models as black boxes, I focus on **evidence traceability, reproducibility, and clear boundaries between computational predictions and experimental validation**.

---

## Focus Areas

- **AI for Drug Discovery & Structural Bioinformatics**: Protein structure evaluation, conformational ensemble analysis, and quantitative interface characterization.
- **Computational Protein Design Workflows**: Integrating generative structure/sequence design and structure prediction models into reproducible hypothesis-testing pipelines.
- **Evidence-Linked AI Research Agents**: Designing local-first scientific workspaces that protect confidential research data while separating deterministic computation from LLM reasoning.
- **Data Quality & Production Software Engineering**: Automated data integrity audits, reproducibility metadata logging, regression testing, and CI/CD workflows.

---

## Technical Stack

| Area | Technologies & Tools |
| :--- | :--- |
| **Data Science & Scientific Computing** | Python, Jupyter Notebook, Google Colab, NumPy, pandas, SciPy, Matplotlib, PyTorch |
| **Structural Biology & Molecular Analysis** | MDTraj (DSSP / SASA / contact analysis), 3Dmol.js, py3Dmol |
| **Biomolecular AI Models** | AlphaFold 3, Boltz-2, BioEmu-2, RFdiffusion3, ProteinMPNN, LigandMPNN |
| **AI Agents & Web / Desktop** | TypeScript, React, Express, OpenAI Responses API, Zod, Electron, Supabase, Stripe |
| **Mobile, Testing & CI** | Swift, SwiftUI, Core Data, Combine, Vitest, GitHub Actions, Fastlane |

---

## Featured Projects

### 1. Life Science & Drug Discovery AI

#### [FoldLens — Evidence-Linked AlphaFold 3 Research Workspace](https://github.com/Shunsuke-max/foldlens-portfolio/blob/main/README.en.md)
A **local-first AI research workspace** for interpreting, comparing, and auditing AlphaFold 3 predictions (originally built for OpenAI Build Week 2026 and expanded into a broader scientific software project).
- **Key design decisions**: Keeps source structure files (CIF / PAE JSON) on-device to protect unpublished research data, separates deterministic numerical analysis (confidence metrics, atomic contacts, cross-model comparison) from a tool-using AI agent, and links every claim back to verifiable measurements.
- **Stack**: TypeScript, React, Express, 3Dmol.js, OpenAI Responses API, Zod, Electron, Vitest
- **Links**: [Product & Engineering Portfolio (EN)](https://github.com/Shunsuke-max/foldlens-portfolio/blob/main/README.en.md) · [Original Public Source](https://github.com/Shunsuke-max/foldlens) · [macOS Releases](https://github.com/Shunsuke-max/foldlens-releases/releases)

#### [AI-driven Protein Design — Computational Research Portfolio](https://github.com/Shunsuke-max/protein-design-portfolio)
Computational protein design workflows and hypothesis-testing documentation developed for the Anthropic × Adaptyv Protein Design Competition 2026 (Open Track), targeting oncology and delivery-relevant proteins (**EGFR, TfR1, and KRAS G12D pMHC**).
- **Highlights**: Covers literature and experimental structure review, multi-model workflow design (RFdiffusion3, LigandMPNN, ProteinMPNN, Boltz-2, AlphaFold 3), failure-mode logging, and disciplined separation of predicted confidence from experimental binding.
- **Stack**: Python, Jupyter Notebook, Google Colab, biomolecular design and structure prediction models
- **Links**: [Computational Research Portfolio (JP)](https://github.com/Shunsuke-max/protein-design-portfolio)

---

### 2. Software Engineering & Data Quality

#### [Part5 Pro — iOS Learning App & Data Quality Audit](https://github.com/Shunsuke-max/part5-pro-portfolio)
An iOS learning app for TOEIC Part 5 published and continuously maintained on the App Store. Demonstrates end-to-end product engineering, **SM-2 spaced-repetition modeling**, and an **automated structural quality audit across 3,966 questions (59 data files)** paired with regression testing and UX/accessibility audits.
- **Stack**: Swift, SwiftUI, Core Data, Combine, GitHub Actions, Fastlane
- **Links**: [Engineering Portfolio (JP)](https://github.com/Shunsuke-max/part5-pro-portfolio) · [App Store](https://apps.apple.com/jp/app/part5-pro/id6748593708)

#### Other Projects
- **[EIKEN Grade 1 Speaking](https://github.com/Shunsuke-max/eiken-grade1-speaking)**: Zero-dependency static web learning tool featuring 300 expressions and 900 example sentences with search, category filters, and randomized practice.
- **Hitokoto English**: Personal iOS app providing AI feedback on naturalness and intent for everyday English expression practice.

---

## Core Principles

1. **Separating Prediction from Experimental Proof**: Never equate confidence metrics (pLDDT / ipTM) or geometric contact agreement with experimental binding affinity or biological efficacy; always surface uncertainty and falsification conditions.
2. **Reproducibility & Data Integrity**: Record execution environments, parameters, provenance, and failure modes, and automate structural validation checks wherever possible.
3. **Trustworthy AI for Research Workflows**: Protect sensitive scientific data through local-first boundaries and ground LLM reasoning in deterministic computation so scientists can verify every conclusion.

---

## Vision

By combining domain grounding in pharmacy and life sciences with data science and AI engineering, I aim to contribute to uncovering disease mechanisms and accelerating data-driven drug discovery.
