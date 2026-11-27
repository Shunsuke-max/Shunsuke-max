# Shunsuke

[日本語](README.md) | English

**Pharmacy / Life Science × Data Science & AI Engineering**  
*Building reproducible computational pipelines and evidence-linked scientific AI software for drug discovery.*

I am a pharmacy student working at the intersection of **structural bioinformatics, computational protein design, and scientific AI agents**. Rather than treating predictive models as black boxes, I focus on **independent data-quality verification, reproducibility, and clear boundaries between computational predictions and experimental validation**.

> **30-Second Role Guide**
> - **Data Science / Structural Bioinformatics** → [VAMP721–PICALM1a Ensemble Analysis (Python / pytest / CI)](https://github.com/Shunsuke-max/vamp721-structural-ensemble/blob/main/README.en.md) · [FoldLens Real AF3 Case Studies](https://github.com/Shunsuke-max/foldlens-portfolio/blob/main/README.en.md) · [FoldLens Core Engine & Calibration](https://github.com/Shunsuke-max/foldlens-core/blob/main/README.en.md)
> - **AI Engineering / Software Architecture** → [FoldLens Core (6-Tool Grounded Agent · Zod · 125 Tests)](https://github.com/Shunsuke-max/foldlens-core/blob/main/README.en.md) · [FoldLens Interactive Live Demo (Client-Side, Real AF3)](https://shunsuke-max.github.io/foldlens-portfolio/) · [Part5 Pro Data Quality Audit & iOS Production](https://github.com/Shunsuke-max/part5-pro-portfolio)

---

## Verified Findings & Data-Quality Audits

| Project | Blind Spot / Problem Uncovered | Engineering & Scientific Solution |
| :--- | :--- | :--- |
| **[VAMP721–PICALM1a](https://github.com/Shunsuke-max/vamp721-structural-ensemble/blob/main/README.en.md)** | BioEmu-2's official QC (`check_physicality`) passed **8/8** frames despite residual interchain steric clashes | Implemented an independent `SciPy cKDTree` heavy-atom clash check that caught **2 frames (1.62 Å / 2.02 Å)**, packaged into a tested Python module with `pytest` + GitHub Actions CI |
| **[FoldLens](https://github.com/Shunsuke-max/foldlens-portfolio/blob/main/README.en.md)** | Relying on single summary scores (`ipTM 0.79`) hides interface PAE tension, local low-pLDDT overlap, and 3-chain divergence | Built a Web Worker deterministic engine that surfaces **5/5 geometric consensus vs. 11.0 Å PAE conflict**, **60.3 Å 3-chain ensemble divergence**, and duplicate-coordinate traps ([Live Demo](https://shunsuke-max.github.io/foldlens-portfolio/)) |
| **[Part5 Pro](https://github.com/Shunsuke-max/part5-pro-portfolio)** | Structural inconsistencies across production learning datasets and SM-2 scheduling edge cases | Built an **automated structural audit across 3,966 questions (59 files)** paired with SM-2 spec fixes and regression tests |

---

## Visual Showcase

<table>
  <tr>
    <td width="50%" valign="top">
      <a href="https://shunsuke-max.github.io/foldlens-portfolio/">
        <img src="https://raw.githubusercontent.com/Shunsuke-max/foldlens-portfolio/main/assets/real-af3-case1-overview.png" alt="FoldLens Live Demo with Real AF3 Data" />
      </a>
      <br />
      <strong><a href="https://shunsuke-max.github.io/foldlens-portfolio/">▶ FoldLens Live Demo (2 Real AF3 Cases Preloaded)</a></strong><br />
      <sub>Client-side Web Worker analysis of real AlphaFold 3 predictions—3Dmol.js, PAE, cross-model RMSD/Jaccard in 5 seconds.</sub>
    </td>
    <td width="50%" valign="top">
      <a href="https://github.com/Shunsuke-max/vamp721-structural-ensemble/blob/main/README.en.md">
        <img src="https://raw.githubusercontent.com/Shunsuke-max/vamp721-structural-ensemble/main/assets/interface_contact_map.png" alt="VAMP721–PICALM1a BioEmu-2 Interface Contact Map" />
      </a>
      <br />
      <strong><a href="https://github.com/Shunsuke-max/vamp721-structural-ensemble/blob/main/README.en.md">VAMP721–PICALM1a Conformational Ensemble Analysis</a></strong><br />
      <sub>BioEmu-2 sampling with DSSP, 6/8/10 Å contact sensitivity analysis, independent clash QC, and pytest CI.</sub>
    </td>
  </tr>
</table>

---

## Featured Projects

### 1. Life Science & Drug Discovery AI

#### [FoldLens — Evidence-Linked AlphaFold 3 Research Workspace](https://github.com/Shunsuke-max/foldlens-portfolio/blob/main/README.en.md) · [▶ Live Demo](https://shunsuke-max.github.io/foldlens-portfolio/)
A **local-first AI research workspace** for interpreting, comparing, and auditing AlphaFold 3 predictions (originally built for OpenAI Build Week 2026 and expanded into a full scientific software architecture).
- **Real AF3 Case Studies & Live Demo**: Published a zero-install [GitHub Pages interactive demo](https://shunsuke-max.github.io/foldlens-portfolio/) preloaded with two contrasting real AF3 ensembles (`Arabidopsis PICALM1a–VAMP721` geometry-vs-PAE conflict & `Human PICALM–HRB–VAMP7` 3-chain divergence / IDR isolation).
- **Key design decisions**: Parses source CIF/PAE JSON on-device inside Web Workers to protect unpublished sequences/coordinates, and separates deterministic metrics (duplicate-coordinate gate, heavy-atom Jaccard overlap, interface RMSD, reciprocal PAE) from a 6-tool AI research agent.
- **Stack**: TypeScript, React, Express, 3Dmol.js, Web Workers, OpenAI Responses API, Zod, Electron, Vitest
- **Links**: [**▶ Live Demo (Browser)**](https://shunsuke-max.github.io/foldlens-portfolio/) · [**Core Engine & Tests (`foldlens-core`)**](https://github.com/Shunsuke-max/foldlens-core/blob/main/README.en.md) · [Real AF3 Case Studies (EN)](https://github.com/Shunsuke-max/foldlens-portfolio/blob/main/README.en.md) · [macOS Releases](https://github.com/Shunsuke-max/foldlens-releases/releases) *(commercial auth/billing app kept private; live walkthrough available in interviews)*

#### [VAMP721–PICALM1a Structural Ensemble Analysis (Python / BioEmu-2)](https://github.com/Shunsuke-max/vamp721-structural-ensemble/blob/main/README.en.md)
A reproducible Python structural bioinformatics pipeline using **BioEmu-2** (`equilibrium` mode) to sample and quantitatively evaluate protein-complex conformational ensembles with independent post-hoc QC and CI-tested metrics.
- **Highlights**: Integrates construct validation, explicit MSA generation, unrestrained A100 sampling, independent `cKDTree` heavy-atom clash detection catching 2 residual clashes (`1.62 Å / 2.02 Å`) after `check_physicality` passed 8/8, MDTraj DSSP/BSA, 6/8/10 Å contact sensitivity analysis, and `pytest` + GitHub Actions CI.
- **Stack**: Python, Jupyter Notebook, Google Colab, BioEmu-2, PyTorch, MDTraj, SciPy, NumPy, pandas, Matplotlib, pytest
- **Links**: [Analysis Repository & Executed Notebook (EN)](https://github.com/Shunsuke-max/vamp721-structural-ensemble/blob/main/README.en.md)

#### [AI-driven Protein Design — Computational Research Portfolio](https://github.com/Shunsuke-max/protein-design-portfolio/blob/main/README.en.md)
Computational protein design workflows and hypothesis-testing documentation developed for the Anthropic × Adaptyv Protein Design Competition 2026 (Open Track), targeting oncology and delivery-relevant proteins (**EGFR, TfR1, and KRAS G12D pMHC**).
- **Highlights**: Covers literature and experimental structure review, multi-model workflow design (RFdiffusion3, LigandMPNN, ProteinMPNN, Boltz-2, AlphaFold 3), failure-mode logging, and disciplined separation of predicted confidence from experimental binding.
- **Stack**: Python, Jupyter Notebook, Google Colab, biomolecular design and structure prediction models
- **Links**: [Computational Research Portfolio (EN)](https://github.com/Shunsuke-max/protein-design-portfolio/blob/main/README.en.md)

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

## Technical Stack

| Area | Technologies & Tools |
| :--- | :--- |
| **Data Science & Scientific Computing** | Python, Jupyter Notebook, Google Colab, NumPy, pandas, SciPy, Matplotlib, PyTorch, pytest |
| **Structural Biology & Molecular Analysis** | MDTraj (DSSP / SASA / contact analysis), 3Dmol.js, py3Dmol |
| **Biomolecular AI Models** | AlphaFold 3, Boltz-2, BioEmu-2, RFdiffusion3, ProteinMPNN, LigandMPNN |
| **AI Agents & Web / Desktop** | TypeScript, React, Express, Web Workers, OpenAI Responses API, Zod, Electron, Supabase, Stripe |
| **Mobile, Testing & CI** | Swift, SwiftUI, Core Data, Combine, Vitest, GitHub Actions, Fastlane |

---

## Technical Writing

- **[UX Writing in Scientific AI Software (JP)](https://github.com/Shunsuke-max/foldlens-portfolio/blob/main/docs/ux-writing-in-scientific-ai.md)**: Treating UI copy and technical language as core software quality attributes—with real FoldLens before/after refinements and an [8-point content quality checklist](https://github.com/Shunsuke-max/foldlens-portfolio/blob/main/docs/ux-writing-checklist.md).

---

## Core Principles

1. **Separating Prediction from Experimental Proof**: Never equate confidence metrics (pLDDT / ipTM) or geometric contact agreement with experimental binding affinity or biological efficacy; always surface uncertainty and falsification conditions.
2. **Reproducibility & Data Integrity**: Record execution environments, parameters, provenance, and failure modes, and verify model outputs with independent automated checks rather than trusting default filters blindly.
3. **Trustworthy AI for Research Workflows**: Protect sensitive scientific data through local-first boundaries and ground LLM reasoning in deterministic computation so scientists can verify every conclusion.
4. **Treating Language & UI Copy as a Software Quality Attribute**: Audit naturalness, factual precision, terminology consistency, and signal-to-noise ratio alongside code readability and automated tests.
