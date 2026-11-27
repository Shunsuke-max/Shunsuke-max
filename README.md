# Shunsuke

日本語 | [English](README.en.md)

**薬学・生命科学 × データサイエンス・AIエンジニアリング**  
*Building reproducible computational pipelines and evidence-linked scientific AI software for drug discovery.*

生命現象の理解と創薬研究の加速に向けて、**構造バイオインフォマティクス・計算タンパク質設計・AI研究エージェント**の領域で解析ワークフローとソフトウェア開発に取り組んでいます。予測モデルを「使うだけ」で終わらせず、**モデルの盲点を定量的に暴く独立検証・再現性・実験的検証との境界設計**を重視しています。

> **職種別・30秒の見どころガイド**
> - **データサイエンス／構造バイオインフォ志望軸** → [VAMP721–PICALM1a アンサンブル解析（Python / pytest / CI）](https://github.com/Shunsuke-max/vamp721-structural-ensemble) ・ [FoldLens 実AF3ケーススタディ](https://github.com/Shunsuke-max/foldlens-portfolio)
> - **AIエンジニア／ソフトウェア設計志望軸** → [FoldLens ライブデモ（ブラウザ内完結・実AF3搭載）](https://shunsuke-max.github.io/foldlens-portfolio/) ・ [Part5 Pro データ品質監査 & iOS運用](https://github.com/Shunsuke-max/part5-pro-portfolio)

---

## 独自に検知・解決したデータ品質／検証課題（Verified Findings）

| プロジェクト | 発見した課題・盲点 | 設計・実装による解決 |
| :--- | :--- | :--- |
| **[VAMP721–PICALM1a](https://github.com/Shunsuke-max/vamp721-structural-ensemble)** | BioEmu-2 公式 QC（`check_physicality`）が **8/8 合格**とした生成構造に局所立体障害が残存 | 独自の `SciPy cKDTree` 重原子クラッシュ検証を実装し、**2 フレーム（1.62 Å / 2.02 Å）の立体障害**を特定。`pytest` + GitHub Actions CI で自動検証化 |
| **[FoldLens](https://github.com/Shunsuke-max/foldlens-portfolio)** | 実 AF3 予測で単一スコア（`ipTM 0.79`）だけでは界面 PAE 乖離や局所低信頼領域・3鎖構造分岐を見落とす | Web Worker 決定論エンジンで **5/5 再現 vs PAE 11.0 Å の不一致**・**3鎖複合体の構造群崩壊（全体 RMSD 60.3 Å）**・重複座標を自動検出（[ライブデモ](https://shunsuke-max.github.io/foldlens-portfolio/)） |
| **[Part5 Pro](https://github.com/Shunsuke-max/part5-pro-portfolio)** | 実運用 iOS アプリの学習ログ・教材データにおける構造不整合と復習アルゴリズム仕様差 | **3,966問（59ファイル）の自動構造監査**と SM-2 仕様整合性改善・回帰テストを整備 |

---

## ビジュアル一覧 / Visual Showcase

<table>
  <tr>
    <td width="50%" valign="top">
      <a href="https://shunsuke-max.github.io/foldlens-portfolio/">
        <img src="https://raw.githubusercontent.com/Shunsuke-max/foldlens-portfolio/main/assets/real-af3-case1-overview.png" alt="FoldLens 実AF3解析ライブデモ" />
      </a>
      <br />
      <strong><a href="https://shunsuke-max.github.io/foldlens-portfolio/">▶ FoldLens Live Demo（実AF3 2ケース搭載）</a></strong><br />
      <sub>ブラウザ内 Web Worker で実 AF3 出力を解析。3D構造・PAE・モデル間 RMSD/Jaccard 比較を5秒で体験可能。</sub>
    </td>
    <td width="50%" valign="top">
      <a href="https://github.com/Shunsuke-max/vamp721-structural-ensemble">
        <img src="https://raw.githubusercontent.com/Shunsuke-max/vamp721-structural-ensemble/main/assets/interface_contact_map.png" alt="VAMP721–PICALM1a BioEmu-2 界面コンタクトマップ" />
      </a>
      <br />
      <strong><a href="https://github.com/Shunsuke-max/vamp721-structural-ensemble">VAMP721–PICALM1a 配座アンサンブル解析</a></strong><br />
      <sub>BioEmu-2 生成構造に対する DSSP・6/8/10 Å 感度分析・独立クラッシュ QC・pytest CI。</sub>
    </td>
  </tr>
</table>

---

## 主要プロジェクト / Featured Projects

### 1. Life Science & Drug Discovery AI（主軸）

#### [FoldLens — Evidence-Linked AlphaFold 3 Research Workspace](https://github.com/Shunsuke-max/foldlens-portfolio) · [▶ Live Demo](https://shunsuke-max.github.io/foldlens-portfolio/)
AlphaFold 3 の予測結果を研究者が解釈・比較・検証するための**ローカルファーストなAI研究支援ワークスペース**（OpenAI Build Week 2026 出展作から継続開発）。
- **実 AF3 ケーススタディ & ライブデモ**：公開野生型 2 ケース（`Arabidopsis PICALM1a–VAMP721` の高一貫性 vs PAE 乖離、`Human PICALM–HRB–VAMP7` の 3 鎖構造不一致・IDR 特定）を [GitHub Pages](https://shunsuke-max.github.io/foldlens-portfolio/) 上でブラウザ完結デモとして公開。
- **設計のポイント**：未公開の構造ファイル（CIF / PAE JSON）を外部送信せず Web Worker で解析し、決定論的な数値計算（重複座標検出・重原子接触 Jaccard・界面 RMSD・両方向 PAE）と 6 ツール選択型 AI エージェントを分離。
- **技術**：TypeScript, React, Express, 3Dmol.js, Web Workers, OpenAI Responses API, Zod, Electron, Vitest
- **リンク**：[**▶ Live Demo（ブラウザで触る）**](https://shunsuke-max.github.io/foldlens-portfolio/) · [プロダクト詳細・実AF3ケーススタディ](https://github.com/Shunsuke-max/foldlens-portfolio) · [初期版ソースコード](https://github.com/Shunsuke-max/foldlens) · [macOS 配布](https://github.com/Shunsuke-max/foldlens-releases/releases)

#### [VAMP721–PICALM1a Structural Ensemble Analysis（Python / BioEmu-2）](https://github.com/Shunsuke-max/vamp721-structural-ensemble)
拡散モデル **BioEmu-2** を用いたタンパク質複合体の配座アンサンブル探索と、独立 QC・感度分析・テスト済み Python モジュールを備えた再現可能な構造バイオインフォマティクス解析。
- **解析のポイント**：非拘束の `equilibrium` サンプリング（NVIDIA A100）に対し、公式 QC（`check_physicality`: 8/8 合格）通過後に独自の重原子クラッシュ検証で 2 フレーム（1.62 Å / 2.02 Å）の立体障害を検出。MDTraj DSSP・BSA、`SciPy cKDTree` 6/8/10 Å 感度分析、`pytest` + GitHub Actions CI まで一貫実装。
- **技術**：Python, Jupyter Notebook, Google Colab, BioEmu-2, PyTorch, MDTraj, SciPy, NumPy, pandas, Matplotlib, pytest
- **リンク**：[解析リポジトリ・実行済み Notebook](https://github.com/Shunsuke-max/vamp721-structural-ensemble)

#### [AI-driven Protein Design — Computational Research Portfolio](https://github.com/Shunsuke-max/protein-design-portfolio)
Anthropic × Adaptyv Protein Design Competition 2026（Open Track）に向けた、**オンコロジー・デリバリー関連標的（EGFR / TfR1 / KRAS G12D pMHC）の計算タンパク質設計と評価ワークフロー**の記録。
- **取り組みのポイント**：文献・公開構造に基づく科学的な課題設定から、複数モデル（RFdiffusion3 / LigandMPNN / ProteinMPNN / Boltz-2 / AlphaFold 3 等）を用いた計算フロー構築、失敗ログや計算限界の整理までを体系化。
- **技術**：Python, Jupyter Notebook, Google Colab, 各種生体分子設計・構造予測モデル
- **リンク**：[計算研究ポートフォリオ](https://github.com/Shunsuke-max/protein-design-portfolio)

---

### 2. Software Engineering & Data Quality（開発運用・品質監査）

#### [Part5 Pro — iOS Learning App & Data Quality Audit](https://github.com/Shunsuke-max/part5-pro-portfolio)
App Store で公開・継続運用している TOEIC Part 5 学習用 iOS アプリ。企画・実装・配信だけでなく、**SM-2 方式に基づく復習アルゴリズムの仕様整合性改善**や、**3,966問（59ファイル）の教材データに対する自動構造監査と回帰テスト整備**を通じて、実運用におけるデータ品質管理を実践しています。
- **技術**：Swift, SwiftUI, Core Data, Combine, GitHub Actions, Fastlane
- **リンク**：[開発ポートフォリオ](https://github.com/Shunsuke-max/part5-pro-portfolio) · [App Store](https://apps.apple.com/jp/app/part5-pro/id6748593708)

#### その他の制作物
- **[EIKEN Grade 1 Speaking](https://github.com/Shunsuke-max/eiken-grade1-speaking)**：外部依存ゼロの軽量 Web 学習教材（300表現・900例文の検索／フィルタ／ランダム出題）
- **Hitokoto English（ひとこと英語）**：日常表現の英作文に対して AI フィードバックを返す個人開発 iOS アプリ

---

## 技術スタック / Technical Stack

| 領域 | 主な技術・ツール |
| :--- | :--- |
| **データ解析・科学計算** | Python, Jupyter Notebook, Google Colab, NumPy, pandas, SciPy, Matplotlib, PyTorch, pytest |
| **構造生物学・分子解析** | MDTraj (DSSP / SASA / 接触解析), 3Dmol.js, py3Dmol |
| **生体分子AIモデル** | AlphaFold 3, Boltz-2, BioEmu-2, RFdiffusion3, ProteinMPNN, LigandMPNN |
| **AIエージェント・Web開発** | TypeScript, React, Express, Web Workers, OpenAI Responses API, Zod, Electron, Supabase, Stripe |
| **モバイル・品質管理・CI** | Swift, SwiftUI, Core Data, Combine, Vitest, GitHub Actions, Fastlane |

---

## 研究・開発で大切にしていること / Core Principles

1. **予測と実験的根拠の厳密な区別**：高い予測信頼度（pLDDT / ipTM）や計算上の接触一致を、そのまま結合親和性や生物学的機能の証明と混同せず、反証条件と不確実性を明示する。
2. **再現性とデータ品質**：使用環境・パラメータ・バージョン・失敗ログを記録し、モデル標準 QC を鵜呑みにせず独立した自動検査で妥当性を担保する。
3. **研究現場で信頼されるAI設計**：研究データの機密性を守りながら、数値計算と自然言語による推論を適切に役割分担させ、専門家が検証できる形で価値を届ける。
