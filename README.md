# 横浜ビジネスゲーム分析コード  

`横浜ビジネスゲーム`は 横浜国立大学が提供するラウンド型 ビジネスシミュレーションゲームです。   
このゲームは`レストランゲーム`と`ベーカリーゲーム`の2種類があり、どちらも販売価格,製造個数などの数値を毎ラウンド入力し`表(csv)`と`メッセージ`のみが毎ラウンドのゲーム結果として出ます。
  
しかし、経営状態の可視化を行いレポートをまとめるには毎回のcsvのみでは困難を極めます。  
そこで今回、複数のLLMを使用し毎ラウンドのデータのグラフ化をメインとした分析コードの作成を行いました。  
主にjupyter notebookによる分析コードです。
またjupyter notebookアンチ勢のため、現在streamlitによるwebアプリ化を進行中です。

---

## ゲームと本リポジトリのコードの説明
横浜ビジネスゲームは毎ラウンド`csv(表)`などのデータが取得できます。
以下のようなファイル構成で保存してください
<pre>
任意のフォルダ名
├── 1
│   ├── 20xxBaxx_accounting.csv
│   ├── 20xxBaxx_sales.csv
│   └── 20xxBaxx_teamstatus.csv
├── 2
│   ├── 20xxBaxx_accounting.csv
│   ├── 20xxBaxx_sales.csv
│   └── 20xxBaxx_teamstatus.csv
├── 3
│   ├── 20xxBaxx_accounting.csv
│   ├── 20xxBaxx_sales.csv
│   └── 20xxBaxx_teamstatus.csv
.
.
.
</pre>
  

### ベーカリーゲーム
`ベーカリーゲーム` では  
プレイヤーが毎ラウンドで取得できるデータは  
自社の `現金収支` と公開情報として全チームの`販売価格`と`来店者数`のみ  
という制限があり、ここのコードは全てその制限下で分析を行います。  
webアプリ化はこのベーカリーゲームをメインに進行中

分析コードは jupyter notebookで [`anlz_bakerygame03.ipynb`](./anlz_bakerygame03.ipynb)  
ガイドに従い フォルダのパス、csvファイル名、Team番号 を変更してご使用ください

このリポジトリにおいて実際のプレイデータとして [`ba_t7_0521`](./ba_t7_0521)、 [`ba_t7_0528`](./ba_t7_0528) 二つのデータがあります。  
ベーカリーゲーム Team7 におけるプレイデータです。

### レストランゲーム
`レストランゲーム` ではプレイヤーの情報制限はありません。  

分析コードは jupyter notebook で [`anlz_restaurantgame02.ipynb`](./anlz_restaurantgame02.ipynb)  
ガイドに従い フォルダのパス、csvファイル名、Team番号 を変更してご使用ください

このリポジトリにおいて実際のプレイデータとして [`re_t7_0604`](./re_t7_0604) があります。  
レストランゲーム Team7 におけるプレイデータです。
