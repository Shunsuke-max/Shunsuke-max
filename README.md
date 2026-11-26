# Shunsuke

日本語 | [English](README.en.md)

**薬学・生命科学 × データサイエンス・AI**  
*Pharmacy / Life Science × Data Science & AI — Building computational workflows and evidence-linked scientific software for drug discovery.*

生命現象の理解と創薬研究の加速に向けて、**構造バイオインフォマティクス・計算タンパク質設計・AI研究エージェント**の領域で解析ワークフローとソフトウェア開発に取り組んでいます。予測モデルを「使うだけ」で終わらせず、**計算根拠の追跡・再現性・実験的検証との境界設計**を重視しています。

---

## 取り組んでいる領域 / Focus Areas

- **AI創薬・構造バイオインフォマティクス**：タンパク質立体構造の予測・解釈、配座アンサンブル解析、分子間界面の定量評価
- **計算タンパク質設計ワークフロー**：生成モデル・配列設計モデル・構造予測モデルを組み合わせた仮説検証パイプラインの構築
- **科学的根拠に基づくAIエージェント**：機密性の高い研究データを端末内に留めつつ、決定論的な数値計算とLLMによる解釈を分離した研究支援基盤の設計
- **データ品質監査と継続的なソフトウェア開発**：構造整合性の自動検査、再現性メタデータの記録、テスト・CIを組み込んだ開発運用

---

## 技術スタック / Technical Stack

| 領域 | 主な技術・ツール |
| :--- | :--- |
| **データ解析・科学計算** | Python, Jupyter Notebook, Google Colab, NumPy, pandas, SciPy, Matplotlib, PyTorch |
| **構造生物学・分子解析** | MDTraj (DSSP / SASA / 接触解析), 3Dmol.js, py3Dmol |
| **生体分子AIモデル** | AlphaFold 3, Boltz-2, BioEmu-2, RFdiffusion3, ProteinMPNN, LigandMPNN |
| **AIエージェント・Web開発** | TypeScript, React, Express, OpenAI Responses API, Zod, Electron, Supabase, Stripe |
| **モバイル・品質管理・CI** | Swift, SwiftUI, Core Data, Combine, Vitest, GitHub Actions, Fastlane |

---

## 主要プロジェクト / Featured Projects

### 1. Life Science & Drug Discovery AI（主軸）

#### [FoldLens — Evidence-Linked AlphaFold 3 Research Workspace](https://github.com/Shunsuke-max/foldlens-portfolio)
AlphaFold 3 の予測結果を研究者が解釈・比較・検証するための**ローカルファーストなAI研究支援ワークスペース**（OpenAI Build Week 2026 出展作から継続開発）。
- **設計のポイント**：未公開の構造ファイル（CIF / PAE JSON）を外部送信せず端末側で解析し、決定論的な数値計算（信頼度・界面接触・モデル間比較）とツール呼び出し型AIエージェントを分離することで、すべての所見を実データに紐づけて追跡可能にしています。
- **技術**：TypeScript, React, Express, 3Dmol.js, OpenAI Responses API, Zod, Electron, Vitest
- **リンク**：[プロダクト詳細（ポートフォリオ）](https://github.com/Shunsuke-max/foldlens-portfolio) · [初期版ソースコード](https://github.com/Shunsuke-max/foldlens) · [macOS 配布ページ](https://github.com/Shunsuke-max/foldlens-releases/releases)

#### [AI-driven Protein Design — Computational Research Portfolio](https://github.com/Shunsuke-max/protein-design-portfolio)
Anthropic × Adaptyv Protein Design Competition 2026（Open Track）に向けた、**オンコロジー・デリバリー関連標的（EGFR / TfR1 / KRAS G12D pMHC）の計算タンパク質設計と評価ワークフロー**の記録。
- **取り組みのポイント**：文献・公開構造に基づく科学的な課題設定から、複数モデル（RFdiffusion3 / LigandMPNN / ProteinMPNN / Boltz-2 / AlphaFold 3 等）を用いた計算フロー構築、失敗ログや計算限界の整理までを体系化しています。
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

## 研究・開発で大切にしていること / Core Principles

1. **予測と実験的根拠の厳密な区別**：高い予測信頼度（pLDDT / ipTM）や計算上の接触一致を、そのまま結合親和性や生物学的機能の証明と混同せず、反証条件と不確実性を明示する。
2. **再現性とデータ品質**：使用環境・パラメータ・バージョン・失敗ログを記録し、構造的な整合性は自動検査で担保する。
3. **研究現場で信頼されるAI設計**：研究データの機密性を守りながら、数値計算と自然言語による推論を適切に役割分担させ、専門家が検証できる形で価値を届ける。

---

## 目指す方向性 / Vision

薬学・生命科学のドメイン理解とデータサイエンス・AI実装力の双方を活かし、疾患メカニズムの解明や新薬創出の意思決定を加速する研究・基盤開発に貢献したいと考えています。
