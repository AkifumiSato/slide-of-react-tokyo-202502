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
  - 執筆: e.g. [Next.jsの考え方](https://zenn.dev/akfm/books/nextjs-basic-principle)
  - OSS: [`location-state`](https://github.com/recruit-tech/location-state)

::right::

<div class="pt-10 flex justify-center">
  <img src="https://avatars.githubusercontent.com/u/25711332?v=4" width="200" height="200">
</div>

---

# 今日のテーマ: Reactチームが見てる世界

Reactの歴史から彼らの視点を知る

- Reactの誕生: Facebookが抱えていた課題
- Reactの活躍: Facebookを支えるReactとGraphQL
- RSCの誕生: FacebookからVercelへ

---
layout: section
---

# Reactの誕生

Facebookが抱えていた課題

---

# 2012年のWeb開発

僕が見てきたわけではないが、レガシーアプリケーションの保守・エンハンス経験も踏まえて

- アーキテクチャとしてはWeb MVC+jQueryなどがよく採用された
  - MVCはスケールと共に複雑化しやすかった
  - jQueryはブラウザ差異を解決したが、設計は開発者に委ねられてた
- モバイルアプリの台頭もあり、API層とView層の分離ニーズが高まっていた

結果、<span v-mark.underline.red class="font-bold">フロントエンドフレームワーク需要が拡大</span>していた（らしい）

---

# 2012年のフロントエンド事情とFacebook

Facebookは既存のOSSフレームワークではなく、内省開発を試みていた

1. Facebookでは複雑なUI開発に苦労しており、これを解決するためにBolt.jsを開発していた
1. 複雑なUI開発で最も複雑な問題は、**更新**である仮説が建てられた
1. 「更新が発生したら再レンダリングする」というアイディアを取り込んだFBolt.jsが誕生
1. FBolt.jsにさらにJSXなどのアイディアが取り込まれて、名前もReactに変更された

Reactは以下**3つの大きなアイディア**を持って生まれた

- <span v-mark="{ at: 1, color: '#f87171', type: 'underline' }">関数型思考</span>
- <span v-mark="{ at: 1, color: '#f87171', type: 'underline' }">更新に伴う再レンダリング</span>
- <span v-mark="{ at: 1, color: '#f87171', type: 'underline' }">JSX</span>

<!--
参考https://dionarodrigues.dev/blog/reactjs-behind-the-scenes
-->

---

# 2013年、ReactはOSS化するも...

React公開直後は、批判的意見が多かった

- ReactはInstagramのWeb UIで最初に採用された
  - Reactはまだ未完成で、何度も議論と決断があったらしい
- Facebook社内での成功もあり、2013年ReactはOSS化
  - US JSConfで発表も否定的意見が多かった
  - 多くの改善を重ねUE JSConfで再度発表、徐々にコミュニティが拡大し採用事例も増える

Reactが人気を得るまでには多くの逆風があった=それだけ<span v-mark.underline.red class="font-bold">革命的なアイディア</span>を持ち合わせていた

---

# Reactの誕生初期まとめ

Reactチームから見ると...

- Facebookはシンプルでスケールできるフレームワークを求めていた
  - 既存のフレームワークでは、複雑なUI開発に苦労した
  - 覚えやすさやパフォーマンスはおそらく2番目
- Reactは以下3つの大きなアイディアを持って生まれた
  - 関数型思考
  - 更新に伴う再レンダリング
  - JSX
- React初期は特に多くの逆風があった

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
