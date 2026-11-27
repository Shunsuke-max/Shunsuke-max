# Shunsuke

日本語 | [English](README.en.md)

**薬学・生命科学 × データサイエンス・AIエンジニアリング**  
*Building reproducible computational pipelines and evidence-linked scientific AI software for drug discovery.*

生命現象の理解と創薬研究の加速に向けて、**構造バイオインフォマティクス・計算タンパク質設計・AI研究支援ツール**の領域で解析パイプラインとソフトウェアを開発しています。予測モデルを「動かすだけ」で終わらせず、**モデルの弱点や見落としを数値で確かめる独立検証、再現性の確保、実験による裏付けとの線引き**を大切にしています。

> **30秒で見る・関心領域別ガイド**
> - **データサイエンス／構造解析にご関心のある方** → [VAMP721–PICALM1a 構造アンサンブル解析（Python / pytest / CI）](https://github.com/Shunsuke-max/vamp721-structural-ensemble) ・ [FoldLens 実データ検証ケーススタディ](https://github.com/Shunsuke-max/foldlens-portfolio)
> - **AIエンジニアリング／ソフトウェア設計にご関心のある方** → [FoldLens ライブデモ（ブラウザ内完結・実AF3データ搭載）](https://shunsuke-max.github.io/foldlens-portfolio/) ・ [Part5 Pro データ品質監査 & iOS 開発運用](https://github.com/Shunsuke-max/part5-pro-portfolio)

---

## 独自に検知・解決したデータ品質と検証の課題（Verified Findings）

| プロジェクト | 発見した課題・見落とし | 設計・実装による解決 |
| :--- | :--- | :--- |
| **[VAMP721–PICALM1a](https://github.com/Shunsuke-max/vamp721-structural-ensemble)** | 構造生成モデル BioEmu-2 の標準チェック（`check_physicality`）で **8/8 合格**となった構造の中に、原子どうしの衝突が残っていた | 独自の `SciPy cKDTree` 距離検査を実装し、**2 フレーム（1.62 Å / 2.02 Å）の立体衝突**を特定。再利用可能な Python モジュール化し、`pytest` と GitHub Actions CI で自動検証 |
| **[FoldLens](https://github.com/Shunsuke-max/foldlens-portfolio)** | AlphaFold 3 の予測は、総合スコア（例：`ipTM 0.79`）だけを見ると、界面の誤差予測（PAE）の高さや一部領域の低信頼、モデル間の配置のばらつきを見落としやすい | ブラウザ内のルールベース計算（Web Worker）で、**形状は 5/5 一致するが界面 PAE が 11.0 Å と高めな食い違い**、**3鎖複合体での配置の大きなばらつき（全体 RMSD 60.3 Å）**、および重複ファイルを自動検知（[ライブデモ](https://shunsuke-max.github.io/foldlens-portfolio/)） |
| **[Part5 Pro](https://github.com/Shunsuke-max/part5-pro-portfolio)** | 継続運用中の iOS 学習アプリにおいて、教材データの構造不整合や復習アルゴリズム（SM-2）の仕様ずれが発生していた | **3,966問（59ファイル）の自動構造監査**と SM-2 仕様の修正・回帰テストを整備し、データ品質を自動チェックできる運用へ改善 |

---

## ビジュアル一覧 / Visual Showcase

<table>
  <tr>
    <td width="50%" valign="top">
      <a href="https://shunsuke-max.github.io/foldlens-portfolio/">
        <img src="https://raw.githubusercontent.com/Shunsuke-max/foldlens-portfolio/main/assets/real-af3-case1-overview.png" alt="FoldLens 実際のAlphaFold 3予測データを解析するライブデモ画面" />
      </a>
      <br />
      <strong><a href="https://shunsuke-max.github.io/foldlens-portfolio/">▶ FoldLens ライブデモ（実際の AF3 データ 2 件を搭載）</a></strong><br />
      <sub>ブラウザ内の Web Worker で実際の AlphaFold 3 出力を解析。3D 分子表示・PAE・モデル間比較を 5 秒で試せます。</sub>
    </td>
    <td width="50%" valign="top">
      <a href="https://github.com/Shunsuke-max/vamp721-structural-ensemble">
        <img src="https://raw.githubusercontent.com/Shunsuke-max/vamp721-structural-ensemble/main/assets/interface_contact_map.png" alt="VAMP721–PICALM1a BioEmu-2 界面コンタクトマップ" />
      </a>
      <br />
      <strong><a href="https://github.com/Shunsuke-max/vamp721-structural-ensemble">VAMP721–PICALM1a 構造アンサンブル解析</a></strong><br />
      <sub>BioEmu-2 で生成した構造に対し、二次構造定量・距離閾値の感度分析・独自の立体衝突チェック・pytest CI を実装。</sub>
    </td>
  </tr>
</table>

---

## 主要プロジェクト / Featured Projects

### 1. 生命科学・AI 創薬（主軸）

#### [FoldLens — 根拠をたどれる AlphaFold 3 検証ワークスペース](https://github.com/Shunsuke-max/foldlens-portfolio) · [▶ ライブデモ](https://shunsuke-max.github.io/foldlens-portfolio/)
AlphaFold 3 の構造予測結果を、研究者が比較・検証するための**ローカル完結型の AI 研究支援ワークスペース**です（OpenAI Build Week 2026 出展作から継続開発）。
- **実データケーススタディ & ライブデモ**：公開されている野生型配列 2 件（① `Arabidopsis PICALM1a–VAMP721`：形状は 5/5 一致するが界面 PAE が高めの例、② `Human PICALM–HRB–VAMP7`：3鎖複合体でモデル間の配置が大きく割れる例）を [GitHub Pages](https://shunsuke-max.github.io/foldlens-portfolio/) 上でブラウザ完結デモとして公開しています。
- **設計のポイント**：未公開の立体構造ファイル（CIF / PAE JSON）を外部送信せず端末内の Web Worker で解析し、厳密な数値計算（重複ファイル検査・接触一致率・RMSD・両方向 PAE）と、6 種類の解析ツールを使い分ける AI エージェントを明確に分離しています。
- **技術**：TypeScript, React, Express, 3Dmol.js, Web Workers, OpenAI Responses API, Zod, Electron, Vitest
- **リンク**：[**▶ ライブデモ（ブラウザで試す）**](https://shunsuke-max.github.io/foldlens-portfolio/) · [プロダクト詳細・実データケーススタディ](https://github.com/Shunsuke-max/foldlens-portfolio) · [初期版ソースコード](https://github.com/Shunsuke-max/foldlens) · [macOS 配布ページ](https://github.com/Shunsuke-max/foldlens-releases/releases)

#### [VAMP721–PICALM1a 構造アンサンブル解析（Python / BioEmu-2）](https://github.com/Shunsuke-max/vamp721-structural-ensemble)
拡散モデル **BioEmu-2** を使ってタンパク質複合体がとり得る複数の立体構造（配座アンサンブル）を探索し、独自の物理チェック・感度分析・自動テスト済み Python モジュールまで一貫して組んだ解析リポジトリです。
- **解析のポイント**：事前拘束なしの `equilibrium` サンプリング（NVIDIA A100）に対し、モデル標準チェック（`check_physicality`: 8/8 合格）を通過した後で独自の原子間距離チェックを走らせ、2 フレーム（1.62 Å / 2.02 Å）の立体衝突を発見しました。MDTraj による二次構造・界面面積（BSA）評価、`SciPy cKDTree` による 6/8/10 Å の感度分析、`pytest` + GitHub Actions CI まで実装しています。
- **技術**：Python, Jupyter Notebook, Google Colab, BioEmu-2, PyTorch, MDTraj, SciPy, NumPy, pandas, Matplotlib, pytest
- **リンク**：[解析リポジトリ・実行済み Notebook](https://github.com/Shunsuke-max/vamp721-structural-ensemble)

#### [AI-driven Protein Design — 計算タンパク質設計ポートフォリオ](https://github.com/Shunsuke-max/protein-design-portfolio)
Anthropic × Adaptyv Protein Design Competition 2026（Open Track）に向けた、**がん治療・ドラッグデリバリーに関わる標的タンパク質（EGFR / TfR1 / KRAS G12D pMHC）の計算設計と評価フロー**の記録です。
- **取り組みのポイント**：文献と公開立体構造から設計条件を整理し、骨格生成・配列設計・構造予測の各モデル（RFdiffusion3 / LigandMPNN / ProteinMPNN / Boltz-2 / AlphaFold 3 等）を組み合わせた検証フローを構築。失敗ログや計算上の限界も体系的に整理しています。
- **技術**：Python, Jupyter Notebook, Google Colab, 各種生体分子設計・構造予測モデル
- **リンク**：[計算研究ポートフォリオ](https://github.com/Shunsuke-max/protein-design-portfolio)

---

### 2. ソフトウェア開発・データ品質管理

#### [Part5 Pro — iOS 学習アプリ & 教材データ品質監査](https://github.com/Shunsuke-max/part5-pro-portfolio)
App Store で公開・継続運用している TOEIC Part 5 学習用 iOS アプリです。企画・実装・配信だけでなく、**復習間隔アルゴリズム（SM-2）の仕様整合性改善**や、**3,966問（59ファイル）の教材データに対する自動構造監査と回帰テスト整備**を通じて、実運用でのデータ品質管理を実践しています。
- **技術**：Swift, SwiftUI, Core Data, Combine, GitHub Actions, Fastlane
- **リンク**：[開発ポートフォリオ](https://github.com/Shunsuke-max/part5-pro-portfolio) · [App Store](https://apps.apple.com/jp/app/part5-pro/id6748593708)

#### その他の制作物
- **[EIKEN Grade 1 Speaking](https://github.com/Shunsuke-max/eiken-grade1-speaking)**：外部ライブラリを使わない軽量な Web 学習教材（300表現・900例文の検索・絞り込み・ランダム出題）
- **Hitokoto English（ひとこと英語）**：日常表現の英作文に対して AI がフィードバックを返す個人開発 iOS アプリ

---

## 技術スタック / Technical Stack

| 領域 | 主な技術・ツール |
| :--- | :--- |
| **データ分析・科学計算** | Python, Jupyter Notebook, Google Colab, NumPy, pandas, SciPy, Matplotlib, PyTorch, pytest |
| **構造生物学・分子解析** | MDTraj (DSSP / SASA / 接触解析), 3Dmol.js, py3Dmol |
| **生体分子AIモデル** | AlphaFold 3, Boltz-2, BioEmu-2, RFdiffusion3, ProteinMPNN, LigandMPNN |
| **AIエージェント・Web開発** | TypeScript, React, Express, Web Workers, OpenAI Responses API, Zod, Electron, Supabase, Stripe |
| **モバイル・品質管理・CI** | Swift, SwiftUI, Core Data, Combine, Vitest, GitHub Actions, Fastlane |

---

## 設計ノート / Technical Writing

- **[AI 時代の科学ソフトウェア開発における UX ライティング](https://github.com/Shunsuke-max/foldlens-portfolio/blob/main/docs/ux-writing-in-scientific-ai.md)**：文章を「単なる説明」ではなくインターフェースの品質特性として扱う設計思想、FoldLens での改善実例、および開発工程に組み込む [8 項目の文章品質チェックリスト](https://github.com/Shunsuke-max/foldlens-portfolio/blob/main/docs/ux-writing-checklist.md)。

---

## 研究・開発で大切にしていること / Core Principles

1. **予測スコアと実験的証明を混同しない**：高い予測信頼度（pLDDT / ipTM）や構造の一致を、そのまま結合親和性や生物学的機能の証明とみなさず、予測が覆り得る条件（反証条件）と不確実性を明示する。
2. **再現性とデータ品質を仕組みで守る**：実行環境・パラメータ・バージョン・失敗ログを残し、モデル標準の品質チェックを鵜呑みにせず独自の自動検査で妥当性を確かめる。
3. **研究現場で信頼される AI 設計**：研究データの機密性を守りながら、厳密な数値計算はプログラムに任せ、AI はその観測結果をもとに説明する役割分担を徹底する。
4. **文章と UI をインターフェースの品質特性として設計・監査する**：文章の自然さ・意味の正確さ・用語の一貫性・情報量の適切さを、コードの可読性やテストと同じ品質基準としてレビューする。
