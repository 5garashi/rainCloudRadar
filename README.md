# 雨雲レーダー 自動更新 / Rain Radar — Auto-refresh

気象庁の雨雲・雷・衛星画像などを地図に重ね、指定した間隔で自動更新して表示するブラウザ用ツールです。HTMLファイル1つで動作し、サーバー側の処理やビルド作業は不要です。

A browser tool that overlays JMA rain, lightning, satellite and distribution-forecast tiles on a map and refreshes them at a chosen interval. It is a single HTML file: no server-side code and no build step.

- 公開ページ / Published page: https://5garashi.github.io/rainCloudRadar/
- 版 / Version: 1.4（2026-09-30）

## 1. できること / Features

1. 雨雲の動きを過去1時間から1時間先まで5分間隔で再生できます。
   Plays the rain nowcast from one hour back to one hour ahead in 5-minute steps.
2. 表示するデータを18種類から選べます（雨雲、雷活動度、竜巻発生確度、ひまわり、今後の雨、天気予報分布、雪、危険度分布）。
   Selects one of 18 data sets, from the nowcast group through Himawari imagery, rainfall and distribution forecasts, snow and the Kikikuru risk maps.
3. 1分・3分・5分・10分の間隔で自動更新します。「現在」を押した状態では、更新のたびに最新時刻へ切り替わります。
   Refreshes every 1, 3, 5 or 10 minutes; while "現在 / Now" is active, each refresh moves to the latest time step.
4. 等圧線を4hPaごとに重ね、高気圧・低気圧の中心を気圧の値とともに表示します（既定で表示）。
   Overlays isobars every 4 hPa with high and low centres and their values (on by default).
5. 気象庁の天気図（実況・24時間予想・48時間予想）を、移動と大きさ変更ができる窓で表示します。
   Shows the JMA weather charts in a floating window that can be moved and resized.
6. 現在位置を丸印と誤差の範囲で表示します。位置情報はブラウザの許可を得たときだけ取得し、地図の表示にのみ使い、外部には送信しません。
   Shows your position with an accuracy circle. Location is requested only with permission, used only to draw the map, and never transmitted.
7. 日本語と英語を切り替えられます。
   Switches between Japanese and English.

## 2. データの出典 / Data sources

1. 気象データ・天気図：気象庁 https://www.jma.go.jp/bosai/
   Weather data and charts: Japan Meteorological Agency.
2. 背景地図：国土地理院 https://maps.gsi.go.jp/development/ichiran.html
   Base map: Geospatial Information Authority of Japan.
3. 海面気圧（等圧線の計算に使用）：Open-Meteo（CC BY 4.0） https://open-meteo.com/
   Sea-level pressure for the isobars: Open-Meteo, CC BY 4.0.

凡例の色は、気象庁「ホームページにおける気象情報の配色に関する設定指針」（2012年5月）に基づきます。一部の凡例には色の対応を推定した部分があり、画面上で「（目安）/ (approximate)」と表示します。

Legend colours follow the JMA colour guideline of May 2012. Where part of the mapping is estimated, the legend is labelled "（目安）/ (approximate)".

## 3. 制限事項 / Limitations

1. 等圧線は2度間隔の数値予報データから計算した推定値で、気象庁の天気図とは形が異なることがあります。前線は描きません。前線は「天気図」で確認してください。
   The isobars are computed from model data on a 2-degree grid and can differ from the JMA charts. Fronts are not drawn; use the chart window for them.
2. 気象庁の画像は偶数のズーム段階にのみ内容が入っています。奇数のズームでは1段細かい画像を縮小して表示します。
   JMA supplies image content only at even zoom levels; odd levels are drawn by scaling down the next finer level.
3. Open-Meteo の無料枠（非商用、1日10,000回・1時間5,000回）は接続元のIPアドレスごとに数えられます。気圧データは1時間使い回すため、ページを開いたままなら取得は1時間に1回、再読み込みのたびに1回発生します。
   Open-Meteo's free non-commercial limits are counted per client IP. The pressure data is kept for one hour, so a page left open fetches once per hour and a reload fetches again.
4. 防災の判断には、気象庁の発表を直接確認してください。本ツールは表示を補助するものです。
   For decisions about safety, check the JMA announcements directly.

## 4. ライセンス / License

1. ソースコード：MIT License（LICENSE）。
   Source code: MIT License.
2. 気象データ・天気図・背景地図：各配信元の利用規約に従い、出典を明示して利用します。
   Weather data, charts and base map: used under the terms of their providers with the source stated.
3. 5garashi.com設計事務所のシンボルマーク、ロゴタイプ、および Design Office Identity：CC BY-ND 4.0。名称およびロゴに関する権利は留保します。
   The 5garashi.com Design Office symbol mark, logotype and Design Office Identity: CC BY-ND 4.0.
4. 画面デザインは Design Office Identity 第4.6版に準拠します。 https://5garashi.github.io/5garashi-identity/
   The interface follows Design Office Identity v4.6.

---

**作成者 / Author**: 5garashi.com設計事務所 / 5garashi.com Design Office
**最終更新 / Last updated**: 2026-09-30 JST
