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

Metaの大規模プロダクトを支える、自立分散的アーキテクチャの歴史

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

Reactチームから見たReact Server Componentsを、歴史から紐解く

1. Reactの誕生
1. ReactとGraphQL
1. RSCの誕生

---
layout: section
---

# Reactの誕生

ViewライブラリとしてのReact

---

# 2012年のWeb開発

見てきたわけではないが、僕のレガシーアプリケーションの保守・エンハンス経験も踏まえて

- アーキテクチャとしてはWeb MVC+jQueryなどがよく採用された
  - MVCはスケールと共に複雑化しやすかった
  - jQueryはブラウザ差異を解決したが、設計は開発者に委ねられてた
- モバイルアプリの台頭もあり、API層とView層の分離ニーズが高まっていた

結果、<span v-mark.underline.red class="font-bold">フロントエンドフレームワーク需要が拡大</span>していた

---

# 2012年のフロントエンド事情とMeta

Metaは既存のOSSフレームワークではなく、内省開発を試みていた

1. Meta（当時はFacebook）では複雑なUI開発に苦労しており、これを解決するためにBolt.jsを開発していた
1. 複雑なUI開発で最も複雑な問題は、**更新**である仮説が建てられた
1. 「更新が発生したら再レンダリングする」というアイディアを取り込んだFBolt.jsが誕生
1. FBolt.jsにさらにJSXなどのアイディアが取り込まれて、名前もReactに変更された

<span v-mark="{ at: 1, color: '#f87171', type: 'underline' }">Reactは以下**3つの大きなアイディア**を持って生まれた</span>

<div v-click="1">

- 関数型思考
- 更新に伴う再レンダリング
- JSX

</div>

<!--
参考: https://dionarodrigues.dev/blog/reactjs-behind-the-scenes
-->

---

# 2013年、ReactはOSS化するも...

React公開直後は、批判的意見が多かった

- ReactはInstagramのWeb UIで最初に採用された
  - Reactはまだ未完成で、何度も議論と決断があったらしい
- Instagramでの成功を経て、2013年ReactはOSS化
  - US JSConfで発表も否定的意見が多かった
  - 多くの改善を重ねUE JSConfで再度発表、徐々にコミュニティが拡大し採用事例も増える

Reactが人気を得るまでには多くの逆風があったが、それだけ<span v-mark.underline.red class="font-bold">革命的なアイディア</span>を持ち合わせていた

---

# Reactの誕生 まとめ

Reactチームから見ると...

- Metaはシンプルでスケールできるフレームワークを求めていた
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

# ReactとGraphQL

Metaを支える技術基盤

---

# Reactの誕生〜2020年頃、React拡大期

Reactは急速にMeta内外での実績を獲得していく

- Meta以外にもNetflixやAirbnbなど、多くの企業がReactを採用
- 関連ライブラリやプラクティスも急速に拡大
- hooksや並行レンダリングなど登場するが、破壊的変更は最小限に留められた
- <span v-mark.underline.red class="font-bold">最も人気なフレームワークとしての地位を確立</span>

---

# GraphQLの拡大

同時期に開発されていたGraphQLも急速に拡大し始める

- 2012年: MetaではREST APIの課題（以下）を解決すべくGraphQLの開発が開始
  - 複数エンドポイントからデータ取得するとネットワーク効率が悪い
  - Over-fetching: 取得するデータが過剰になる場合がある
  - Under-fetching: 取得するデータが不足する場合がある
- 2013年: ReactとGraphQLを統合すべくRelayの開発が開始
- 2015年: GraphQLとRelayがOSS化
- その後、Meta社内でReact&Relay(GraphQL)の採用が進む

---
transition: fade
---

# React, GraphQL, Meta

Metaは我々が想像もできない規模の開発を行なっている

- 世界中に独自のデータセンターを配置
- フレームワークや言語開発も厭わない開発予算
- Meta社内には数万のコンポーネントが存在
  - 10万以上という噂も
  - 多くの修正を自動化しているらしい（Code mod？）

<!--
参考: https://medium.com/@syedmahmad/react-relay-modern-simplified-956f33739f0
-->

---

# React, GraphQL, Meta

Metaの大規模プロダクトたちを支えるアーキテクチャ

- MetaではReactとGraphQLによる**自律分散的アーキテクチャ**を採用してる
  - 自律分散的アーキテクチャの対義語は中央集権アーキテクチャ（Web MVCなど）
- GraphQLのFragment Colocationを用いて、コンポーネント付近で必要なデータフェッチも定義

<img src="https://miro.medium.com/v2/resize:fit:1400/format:webp/1*OXYaanlsu9RszaGrstHP2A.png" alt="https://quramy.github.io/graph-api-note/#/21" width="300" class="pt-5">

https://quramy.github.io/graph-api-note/#/21

---

# ReactとGraphQL まとめ

Reactチームから見ると...

- React+GraphQLによる自立分散的アーキテクチャは、最も重要なアーキテクチャパターン
  - 自立分散的アーキテクチャ=コンポーネントが必要なデータを自分で宣言する世界
  - バックエンドはこれに合わせて、細粒度に設計される必要がある
  - 実際にMetaは社内でこれを採用し、現在も多くのプロダクトを支えている

---
layout: section
---

# RSCの誕生

新たな自立分散的アーキテクチャ

---

# 2020年頃、Reactが抱えていた課題

Reactアプリケーションが肥大化するにつれ、さまざまな問題が浮き彫りになってきた

- バックエンドアクセス
  - 冗長な実装
  - セキュリティ
  - パフォーマンス
- バンドルサイズ
  - 不要なバンドル、冗長なバンドル
  - 最適化コスト
  - 抽象化コスト
- etc...

---

# React Server Components

前述の課題を1つの統合されたアプローチで解決

- バックエンドフルアクセス
- 0バンドルサイズ（ただし、バンドルサイズは[必ずしも減るわけではない](https://tonyalicea.dev/blog/understanding-react-server-components/)）
- 自動コードスプリッティング
- 0コスト抽象化
- etc...

https://github.com/reactjs/rfcs/blob/main/text/0188-server-components.md#motivation

---

# React Server Componentsの自立分散性

前述のReact+GraphQLによる自立分散的アーキテクチャとの関係性

- React Server Componentsも**自立分散的アーキテクチャ**である
  - [_React Server Components と GraphQL のアナロジー_ by Quramyさん](https://quramy.medium.com/react-server-components-%E3%81%A8-graphql-%E3%81%AE%E3%82%A2%E3%83%8A%E3%83%AD%E3%82%B8%E3%83%BC-89b3f5f41a01)
- MetaではReact+GraphQLで解決していた課題を、React単体で解決できるようにしたとも取れる

---

# 余談: 2022年以降のReactチームとMeta

ReactはMeta専属な雰囲気ではなくなってきた

- 主要なReactチームのメンバーが転職し始める
  - Dan Abramov: Blue Sky
  - Andrew Clark: Vercel
  - Sebastian Markbåge: Vercel
  - ...etc
- 2022,2023年には大規模レイオフもあった影響もありそう
  - （実際Recoilチームは解散させられた...）

---

# まとめ

Metaの大規模プロダクトを支える、自立分散的アーキテクチャの歴史

- MetaはReact+GraphQLで自立分散的アーキテクチャを採用し、成功を収めた
- React Server Componentsもまた、自立分散的アーキテクチャである
- Reactは大規模開発まで通用する、シンプルでスケールするフレームワークを目指し続けている

---
layout: section
---

# End
