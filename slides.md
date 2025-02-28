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

Reactが見据える大規模開発とアーキテクチャ

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

# 前提: Metaの大規模開発

Metaは我々が想像もできない規模の開発を行なっている

- 世界中に独自のデータセンターを配置
- フレームワークや言語開発も厭わない開発予算
- 現在では、Meta社内には数万のコンポーネントが存在
  - 10万以上という噂も
  - 多くの修正を自動化しているらしい（Code mod？）

<!--
参考: https://medium.com/@syedmahmad/react-relay-modern-simplified-956f33739f0
-->

---

# 今日のテーマ: Reactチームが見てる世界

大規模開発を支えるReactチームが見てる世界を、歴史から紐解く

1. Reactの誕生
1. ReactとGraphQL
1. React Server Components

---
layout: section
---

# Reactの誕生

Reactは何を解決すべく生まれたのか

---

# 2012年のWeb開発

見てきたわけではないが、僕のレガシーアプリケーションの保守・エンハンス経験も踏まえて

- サーバーサイドWeb MVC+jQueryがよく採用されていた
  - Web MVCはスケールと共に複雑化しやすかった
  - jQueryはブラウザ差異を解決したが、設計は開発者に委ねられてた
- モバイルアプリの台頭もあり、API層とView層の分離ニーズが高まっていた

結果、<span v-mark.underline.red class="font-bold">フロントエンドフレームワーク需要が拡大</span>していた

---

# 2012年のMetaとフレームワーク開発

Meta（当時はFacebook）はフロントエンドフレームワークを内製開発していた

1. Metaは複雑なUI実装に苦労していた
1. これを解決すべく、クライアントサイドMVCフレームワークであるBolt.jsを開発していた
1. UI開発の最も複雑な問題は<span v-mark.underline.red class="font-bold">UIの更新</span>である、という仮説が生まれた
1. MVCを削除し、更新に応じてUIを再レンダリングするアイディアを取り込んだFBolt.jsが誕生
1. さらにJSXなどのアイディアが取り込まれ、**React**が誕生

---

# Reactの誕生

Reactは以下のアイディアやコンセプトを持って生まれた

- 関数型思考
- 更新に伴う再レンダリング
- コンポーネント指向
- JSX

<!--
参考: https://dionarodrigues.dev/blog/reactjs-behind-the-scenes
-->

---

# ReactのOSS化

OSSとして公開した直後は、批判的意見が多かった

- Meta社内でReactが採用されはじめ、2013年ReactはOSS化
  - JSConf USで発表するも、否定的意見が多かった
  - 多くの改善を重ねJSConf EUで再度発表、徐々にコミュニティが拡大し採用事例も増える

当初は強い逆風だったが、それだけ<span v-mark.underline.red class="font-bold">革命的なアイディア</span>だったとも言える

---

# Reactの誕生 まとめ

Reactは何を解決すべく生まれたのか

- Metaは複雑なUI開発に耐えうる<span v-mark.underline.red class="font-bold">シンプル</span>なフレームワークを求めていた
  - 覚えやすさやパフォーマンスは1番ではない
  - Reactは革新的だったが故に、初期は多くの人が否定的だった

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

- ~2012年: Metaはクライアントサイド・API Gateway（BFF）・バックエンドの3層構成を基本としていた
- 2012年: API GatewayをREST APIにした時に発生する以下の課題を解決すべく、GraphQLの開発が開始
  - 複数エンドポイントからデータ取得するとネットワーク効率が悪い
  - Over-fetching: 取得するデータが過剰になる場合がある
  - Under-fetching: 取得するデータが不足する場合がある
- 2013年: ReactとGraphQLを統合すべくRelayの開発が開始
- 2015年: GraphQLとRelayがOSS化
- その後、Meta社内でReact&Relay(GraphQL)の採用が進む

---

# MetaにとってのGraphQL

GraphQLはプロトコルなのか

- MetaにとってのGraphQLはBFFに対する通信、つまり**フロントエンドの問題**を解決する技術
  - BFF〜バックエンドの通信では、**Thrift**というRPCが採用されている
- Meta以外では**バックエンド通信のプロトコル**として採用されることが多い

開発元のMetaと世間では、<span v-mark.underline.red class="font-bold">GraphQL採用のモチベーションが異なる</span>ことが多い

---

# Metaの考えるGraphQLが担う層

<div class="flex justify-center mt-10">
  <img src="/graphql.png" alt="GraphQL" width="80%">
</div>

<!--
https://excalidraw.com/#json=J6xbE-rC2K5hIMY3EUYwW,HHuYJ-TUkRoT8SBc5xmBbw
-->

---
transition: fade
---

# MetaにとってのGraphQLとReact

Metaの大規模プロダクトたちを支えるアーキテクチャ

- MetaにとってReactとGraphQLは大規模システムを支える<span v-mark.underline.red class="font-bold">自律分散的アーキテクチャ</span>の基盤である
  - Not 中央集権アーキテクチャ（e.g. ReduxやWeb MVCなど）
  - [Thinking in Relay](https://relay.dev/docs/principles-and-architecture/thinking-in-relay/)などからもMetaの思考が読み取れる

---
transition: fade
---

# MetaにとってのGraphQLとReact

<div class="flex justify-center mt-10">
  <img src="/top-level-data-fetching.png" alt="Top Level Data Fetching">
</div>

---

# MetaにとってのGraphQLとReact

<div class="flex justify-center mt-10">
  <img src="/graphql-co-location.png" alt="GraphQL">
</div>

---

# ReactとGraphQL まとめ

Metaを支える技術基盤

- MetaにとってReactとGraphQLは<span v-mark.underline.red class="font-bold">自立分散的アーキテクチャ</span>を構築するための基盤
  - コンポーネントが必要なデータを自分で宣言する世界
  - 現在もMetaで多くのプロダクトを支えている

---
layout: section
---

# React Server Components

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
transition: fade
---

# RSCでのData Fetching

<div class="flex justify-center mt-10">
  <img src="/graphql-co-location.png" alt="GraphQL">
</div>

---

# RSCでのData Fetching

<div class="flex justify-center mt-10">
  <img src="/react-server-components.png" alt="React Server Components">
</div>

---

# まとめ

Reactは大規模開発に通用する

- Reactは大規模開発を支えるシンプルなフレームワークである
- MetaはReact+GraphQLで自立分散的なアーキテクチャを採用している
- React Server Componentsもまた、自立分散的アーキテクチャであり、正常進化である

---
layout: section
---

# End
