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
title: Reactチームが見てる世界
mdc: true
---

# Reactチームが見てる世界

in React Tokyo

Metaの大規模開発を支える基盤としてのReact

---
layout: two-cols
---

# Profile

- 名前: 佐藤 昭文（あっきー）
- ID: [akfm_sato](https://x.com/akfm_sato)
- 仕事: フロントエンドエキスパート
- 活動
  - 技術記事: e.g. [Next.jsの考え方](https://zenn.dev/akfm/books/nextjs-basic-principle)
  - OSS: [`location-state`](https://github.com/recruit-tech/location-state)

::right::

<div class="pt-10 flex justify-center">
  <img src="https://avatars.githubusercontent.com/u/25711332?v=4" width="200" height="200">
</div>

---

# 今日のテーマ: Reactチームが見てる世界

Reactチームの歴史から彼らの視点を知る

- React誕生: Facebookが抱えていた課題
- Reactの活躍: Facebookを支えるReactとGraphQL
- RSCの誕生: FacebookからVercelへ

---
layout: section
---

# React誕生

Facebookが抱えていた課題

---

# React登場以前(2012年前後)の風潮と課題

個人的な、レガシーアプリケーションの保守・エンハンス経験も踏まえて

- Web開発としてはMVC+jQueryなどがよく採用された
  - 中規模以上の開発でMVC+jQueryは複雑化しやすかった
- モバイルアプリの台頭もあり、API層とView層の分離ニーズが高まっていた

<span v-mark.underline.red class="font-bold">フロントエンドフレームワーク需要が拡大</span>

---

# JavaScriptフレームワークとFacebook

[React.js: The Documentary](https://www.youtube.com/watch?v=8pDqJVdNa44)より

- OSSで言うとEmberやBackbone.jsなど
- FacebookではBackbone.jsに影響を受けた、Bolt.jsというフレームワークを内省開発していた

Bolt.jsに関数型のアイディアで改善を試みたのが、<span v-mark.underline.red class="font-bold">後のReactのベース</span>となってる

<!--
参考https://dionarodrigues.dev/blog/reactjs-behind-the-scenes
-->

---

# Reactの誕生とInstagram

[React.js: The Documentary](https://www.youtube.com/watch?v=8pDqJVdNa44)より

- Bolt.jsにレンダリングやJSXなどのアイディアが取り込まれ、Reactが誕生した
- ReactはInstagramのWeb UIで最初に採用された
- ReactのOSS化の発表
  - これに興味を持ったSophie Alpert氏が2000行のコントリビュートし、多くの課題を解決
  - その後コミュニティが拡大、様々な企業が採用

---
layout: section
---

# Reactの活躍

Facebookを支えるReact（&GraphQL）

---

TBW

---
layout: section
---

# RSCの誕生

FacebookからVercelへ

---

TBW
