---
theme: default
# https://unsplash.com/ja/%E5%86%99%E7%9C%9F/%E6%97%A5%E9%A3%9F%E3%81%AE%E3%83%87%E3%82%B8%E3%82%BF%E3%83%AB%E5%A3%81%E7%B4%99-_ok8uVzL2gI
background: /background.png
class: text-center
highlighter: shiki
lineNumbers: false
colorSchema: "dark"
drawings:
  persist: false
transition: slide-left
title: Next.js入門
mdc: true
---

# Scalable & React

Metaの大規模開発を支える基盤としてのReact

---

# Profile

- 名前: 佐藤 昭文（[akfm_sato](https://x.com/akfm_sato)、あっきー）
- 活動
  - Next.jsの布教
    - [Next.jsの考え方](https://zenn.dev/akfm/books/nextjs-basic-principle)
    - イベント登壇
  - others
    - テスト設計の研究: [フロントエンドにおける「単体テストの考え方/使い方」](https://zenn.dev/akfm/articles/frontend-unit-testing)
    - 稀にRustの布教: [Rust入門本](https://www.amazon.co.jp/dp/4798067318)
    - OSS `location-state`: 履歴位置単位の状態管理ライブラリ
      - https://github.com/recruit-tech/location-state

---

# 今日の主題とアジェンダ

Reactの開発者達の視点を知って欲しい

- React登場以前の技術的課題
- ReactはFacebook(Meta)の何を解決したのか
- ReactはRSCで何を解決したのか
- Reactの開発者はどこにいるのか

---
layout: section
---

# React登場以前の技術的課題

---

# React登場以前(1): MVCフレームワーク全盛

見てきたわけではないので多少誤りはあるかもしれません

- プログラミング言語も様々
- HTMLはテンプレートエンジンで出力
- インタラクションはjQueryなど
- マイクロサービスが過激的に盛り上がっていた
- （厳密にはWebのMVCと出自のMVCは違うらしい）

---

# React登場以前(2): Ruby on Railsの衝撃

見てきたわけではないので多少誤りはあるかもしれません

- ブログを10数分で作れてしまうことが当時は相当な衝撃だったらしい
- Railに沿ってれば非常に効率的な開発
  - Rail = 作者が想定する「よくあるアプリケーション」
  - Railから逸れると一気に難易度が高くなる

<span v-mark.underline.red class="font-bold">Webアプリ開発の0 -> 1が高速になった</span>

---

# React登場以前(3): JavaScriptフレームワーク

見てきたわけではないので多少誤りはあるかもしれません

- EmberやBackboneなど、JavaScriptのフレームワークも様々で始める
- JavaScriptのSSRを担うRendrなども

---

# React登場以前の技術課題

レガシーアプリケーションの保守・エンハンス経験も踏まえて

- 前提
  - コードは常に追加され、設計の見直しや削除はほとんどされない
  - ブラウザの進化もあいまって、日に日により高度なJavaScript処理が求められた
- 結果
  - 認知負荷が急激に上昇し、開発効率が悪化する
    - e.g. 最初は数十行だった`Controller`が数百行、数千行に
    - e.g. 1つだったDOM操作が気づいたらあらゆるJSファイルから操作しており、影響把握が困難
  - 増え続けるHTML,JavaScript,サーバー側処理によってパフォーマンスは劣化の一途

<span v-mark.underline.red class="font-bold">Webアプリ開発のスケールが非常に困難</span>

---
layout: section
---

# ReactはFacebook(Meta)の何を解決したのか

---

# Facebookのスケール

Facebookは企業として成長し続けており、アプリ開発のスケールが急務だった

TBW

---
layout: section
---

# ReactはRSCで何を解決したのか

---

TBW

---
layout: section
---

# Reactの開発者はどこにいるのか

---

TBW

---
