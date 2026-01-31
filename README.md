# 2025gsc-AkiraMotoyoshi

# 登下校ルート分析（淵野辺駅北口 → 青山学院大学相模原キャンパス）
## School Commuting Route Analysis  
### (Fuchinobe Station North Exit → Aoyama Gakuin Univ. Sagamihara Campus)

---

## 📂 **Power Point（発表スライド）**

[こちらのリンクから閲覧できます](https://aoyamajp-my.sharepoint.com/:p:/g/personal/aa123191_aoyama_jp/ESa7l4GgSRtOpCJfYLqhQcQBFu6b1HZE5cE1NhNoImUE-A?e=4aRIaA)

---

## 1. 研究概要 / Research Overview

### 🇯🇵 日本語
本研究は、実際の学生が通学で使用する「淵野辺駅北口 → 青山学院大学相模原キャンパス」のルートを対象に、  
**最短距離・歩きやすさ・夜の安全性（街灯密度）** の3点から比較・分析を行う。  
必要に応じて **Google Earth / QGIS / OpenStreetMap / Strava** を使用し、データ取得・可視化・分析を行う。

### 🌐 English
This study analyzes the commuting route from *Fuchinobe Station (North Exit)* to *Aoyama Gakuin University Sagamihara Campus*.  
The evaluation focuses on **distance, walkability (obstacles), and nighttime safety (streetlight density)**.  
Data collection and visualization are performed using **Google Earth, QGIS, OpenStreetMap, and Strava**.

---

## 2. 研究目的 / Objectives

### 🇯🇵 日本語
- 通学ルートの **距離・安全性・歩きやすさ** を定量的に比較  
- 学生がルートを選ぶ理由を把握する  
- QGIS で地図として可視化し、レポートとしてまとめる  

### 🌐 English
- Quantitatively compare **distance, safety, and walkability** of commuting routes  
- Understand why students choose specific routes  
- Visualize maps in QGIS and summarize findings in a final report  

---

## 🛠 3. 使用ツール / Tools

### 🇯🇵 日本語
- **QGIS**：距離計測、街灯密度分析、地図作成  
- **OpenStreetMap (OSM)**：道路・信号・横断歩道・街灯データ  
- **Google Earth**：景観確認、歩道状況のチェック  
- **Strava（無料版）**：歩行ログ（GPX）取得、移動速度・停止時間の分析  
- **ChatGPT**：研究設計、手順の作成、分析補助、コーディング補助  

### 🌐 English
- **QGIS:** distance measurement, streetlight density analysis, map creation  
- **OpenStreetMap:** road network, signals, crosswalks, streetlight data  
- **Google Earth:** visual confirmation of sidewalks and surroundings  
- **Strava (Free):** walking logs (GPX), speed, and stopping time analysis  
- **ChatGPT:** research planning support, analytical assistance, workflow design, coding support  

---

## 4. 研究フロー / Research Workflow

---

### ① 対象区間の設定 / Defining the Study Area  

- **淵野辺駅北口 → 青山学院大学相模原キャンパス正門**  
- 全ツールの準備（QGIS / OSM / Google Earth / Strava）



---

### ②基本ルートの決定 / Defining the Representative Route  

- 実際に学生が最も多く使う **代表ルートを1本設定**  
- QGIS で LineString として作成  
- 全ての分析はこのルートを対象に行う  

---

### ④ 最短距離の測定（QGIS） / Distance Measurement
- QGIS の計測ツール or ネットワーク解析を使用  
- ルートの総距離（m）を算出  
- 結果はレポートへ反映  

---

#### 2. QGIS に GPX をインポート  
- 速度低下区間・停止ポイントを可視化  

#### 3. OSM データとの重ね合わせ  
- 信号・横断歩道・歩道情報を追加  
- ルートと比較し、障害物の位置を定量化  

---
---

### ⑤ 信号待ち時間の算定 / Signal Waiting Time Estimation

#### 🇯🇵 日本語
本研究では、交差点における信号待ち時間を  
**信号ローテーション構造に基づく期待値モデル**を用いて算定する。

**前提**
- 信号は一定の周期（ローテーション）で繰り返される
- 歩行者の到着時刻は、1ローテーション内で一様分布すると仮定する
- 平均待ち時間は以下で評価する  

\[
\text{平均待ち時間} = \frac{\text{最大待ち時間}}{2}
\]

**対象交差点と採用値**
- **Point B（淵野辺駅入口交差点）**  
  縦断のみ／横断＋縦断の2パターンが存在するため、  
  両者が同確率で発生すると仮定し、平均信号遅延を **58秒** とした。

- **Point C（青山学院大学入口交差点）**  
  歩行者縦フェーズのみ通行可能な交差点について、  
  ストップウォッチによる実測ローテーション（75.74秒）を基に算定し、  
  平均信号遅延を **26.6秒** とした。

これらの値を、登下校ルート全体の所要時間評価に加算する。

#### 🌐 English
Signal waiting time is estimated using an **expected value model** based on signal cycles.

**Assumptions**
- Signals operate in fixed cycles
- Pedestrian arrival time is uniformly distributed within a cycle
- Average waiting time is calculated as half of the maximum waiting time

**Adopted values**
- **Point B (Fuchinobe Station Intersection):** 58 seconds  
- **Point C (AGU Main Gate Intersection):** 26.6 seconds  

These values are incorporated into the total commuting time analysis.
----

### ⑥ 夜の安全性（街灯密度）分析

#### 🇯🇵 日本語
- OSM の `highway=street_lamp` を QGIS に取り込み  
- 夜に実際のルートを歩いて明るさを5段階評価  
- 暗い区間・死角をチェック  
- 街灯密度マップを QGIS で作成  

#### 🌐 English
- Import streetlight data from OSM  
- Walk the route at night and evaluate brightness (1–5 scale)  
- Identify dark zones and blind spots  
- Generate a streetlight density map in QGIS  

---


### ⑧ 分析・考察 / Analysis & Discussion

QGIS で以下の可視化を作成：  
- **距離マップ**  
- **Strava ログ重ね合わせマップ**  
- **信号・横断歩道マップ**  
- **街灯密度マップ**

考察観点：  
- 距離差  
- 障害物の多さ  
- 夜の安全性  
---

### ⑨ 最終成果物 / Final Deliverables

#### 1. QGIS 可視化マップ  
- 距離マップ  
- Strava 重ね合わせ  
- 信号・横断歩道マップ  
- 街灯密度マップ  


---

## 📚 先行研究まとめ

### 1. 大友秀一（2008）
**タイトル**：小学校におけるGISの学校安全への応用に関する研究  
**概要（3文）**：  
GIS を用いて小学校の通学路における危険箇所を可視化した先駆的研究。危険地点の多くが細い路地や見通しの悪い場所に集中することを示した。通学路安全評価に GIS を取り入れる手法の基礎を築いた。  
**リンク**：https://hyogo-u.repo.nii.ac.jp/record/2494/files/geo1303.pdf

---

### 2. 王尾和寿（2014）
**タイトル**：通学路における不安箇所のマッピングとその空間的特徴  
**概要（3文）**：  
児童・保護者の感じた「不安地点」を GIS にマッピングし、ヒートマップを用いて空間分布を分析した研究。不安箇所は交差点や交通量の多い道路、見通しの悪い地点に集中する傾向が明らかになった。主観的不安と道路環境の関連を示した点が特徴である。  
**リンク**：https://cir.nii.ac.jp/crid/1390282680673368704

---

### 3. 吉城秀治（2017）
**タイトル**：通学路における小学生のアクティビティの発生傾向とその要因の検討  
**概要（3文）**：  
通学中の児童行動（立ち止まり・集団形成など）を現地観察し、GIS で道路環境との関連を分析した研究。交差点・信号待ち・歩道の狭い場所で行動が変化しやすいことが示された。道路構造が児童の安全行動に影響を与えることを明確にした。  
**リンク**：https://www.jstage.jst.go.jp/article/journalcpij/52/3/52_879/_article/-char/ja/

---

## 📁 ディレクトリ構成 / Directory Structure


