# PRC Data Challenge 2026

チーム：athletic-yacht

ヨーロッパの10空港を対象に、航空機が駐機場所を出発してから離陸するまでの時間（タクシーアウト時間）をCatBoostで予測する。

## 使用データ

PRC Data Challenge 2026で提供された以下のデータを使用する。

- 2025年のtrainingファイル12個
- final_ranking.parquet
- final_submitting.parquet

データの入手方法：
https://prc-data-challenge-2026.netlify.app/data.html

## 分析方法

空港、滑走路、時刻などを使った基準モデルに、駐機場所、機種、航空会社などの特徴量を追加し、予測精度を比較する。

2025年1〜8月を学習、9月をモデルの選択、10〜12月を評価に使用する。選択した設定で2025年全体を再学習し、2026年1月・2月・6月・7月を予測する。

## 再現方法

Google Colabでの実行を想定する。

1. PRC_DataChallenge_17.ipynbをGoogle Colabで開く。
2. 2025年のtrainingファイル12個、final_ranking.parquet、final_submitting.parquetを/contentに配置する。
3. 「追加分析」の「ライブラリの準備」を実行する。
4. ライブラリを入れ替えた場合は、セッションを再起動する。
5. import pandas as pdで始まるセルから「予測して保存する」の最後のセルまで順に実行する。

「追加分析」は、前半の分析で作成した変数に依存しない。

## ライセンス

GNU General Public License v3.0
