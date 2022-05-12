# navi-ß を支える技術

## [Next.js](https://nextjs.org/)

- React のメジャーフレームワーク
- フロントエンドのみ使用
- 基本的に SSG

## [TypeScript](https://www.typescriptlang.org/)

- 静的型が無いとやってられないので
- tsconfig にはという厳し目のルールを採用

## [microCMS](https://microcms.io/)

- 国産 CMS
- 団体詳細と Breeze のコンテンツを管理
- 無料プランでは API キーが 1 つしか発行できない制約がありセキュリティ面が怪しいが、SSG でごまかしている

## [Cloudfrare Pages](https://pages.cloudflare.com/)

- 強力な CDN を持った静的ホスティングツール
- Organization からの利用も無料で OK。他の選択肢との比較は[こちら](https://zenn.dev/catnose99/scraps/6780379210136f)が詳しい。

## [Tailwind CSS](https://tailwindcss.com/)

- CSS ファイルを書くより断然早い
- サイジングなどがそこそこ限定されており、スタイリングの統一にも一役買っている
- [VSCode の拡張機能](https://zenn.dev/ikenohi/articles/df2bf0c990d99a#%E2%91%A0tailwind-css-intellisense%E3%82%92%E5%85%A5%E3%82%8C%E3%81%A6%E3%80%81%E7%B4%A0%E6%97%A9%E3%81%84%E8%A3%9C%E5%AE%8C%E3%82%92%E6%89%8B%E3%81%AB%E5%85%A5%E3%82%8C%E3%82%8B)を入れておくと便利

## [daisyUI](https://daisyui.com/)

- Tailwind の Bootstrap みたいなやつ
- 最初は楽しくてガンガン使ってたけど、独特のスタイリングがなんかやっかいになってきたので脱依存したい気持ちが大きい

## [clsx](https://github.com/lukeed/clsx)

- className を動的に変更するのを書きやすくしてくれる軽量なライブラリ
- `const style = clsx(...)`で切り出したときにも補完が効くのが嬉しい（普通の文字列として切り出すと効かない）

## [React Hook Form](https://react-hook-form.com/)

- バリデーションなどの Form 操作をシンプルにしてくれるやつ
- 定番なので練習がてら使っているところはある
- 後述の getform.io と組ませてもなんら邪魔をしない

## [Jest](https://jestjs.io/)

- 有名テストツール
- フロントエンドにテストは要らねえ派だが、さくいんなどちょっと複雑なロジックを書くところがあるのでそこだけテストしている

## [Storybook](https://storybook.js.org/)

- コンポーネントライブラリみたいなのを作るやつ
- デザイナー不在の組織でデザイン資産は管理されないがちなので積極採用
- mock データを使いつつ見た目の調整だけをしたいときに超便利
- 現状は webpack でビルドしているが、vite でビルドするようにすると hot reload が速くなるらしい（現状は結構遅い。起動は悪くないけど。）
- 後述の scaffdog にファイルを生成させているので管理も楽ちん

## [ESLint](https://eslint.org/)

- コーディングのお作法みたいなのを取り締まってくれるやつ
- 主要なやつだと import order,tailwind className sorting あたり
- VSCode の設定を施して、Format on Save させるようにしてください

## [Prettier](https://prettier.io/)

- コード整形ツール
- わりとデフォルトのルールを採用している
- VSCode の設定を施して、Format on Save させるようにしてください

## [commitlint](https://commitlint.js.org/#/)

- commit メッセージを限定してくれるやつ
- たまに余計だなと思うけど、当たり前水準はとりあえず上げたいので採用

## [husky](https://github.com/typicode/husky) & [lint-staged](https://github.com/okonet/lint-staged)

- commit 前に TS ルールと ESLint ルールのチェックを行ってくれるやつ
- コード品質を保てる＆レビュー時の負担を減らせる
- エディタの Format on Save 設定しとけば引っかかることはそうそうない

## [scaffdog](https://github.com/cats-oss/scaffdog)

- markdown の設定ファイルを書いて、ファイルやフォルダの自動生成が行えるツール（scaffolding 系のツールという）
- コンポーネントの管理をわりと厳密にし、あらゆるコンポーネントのファイルを自動生成できるようにしている
- Storybook 用のファイルとかも一緒に吐いてくれるので新規コンポーネント作成時には必ず使ってください

## [Google analytics 4](https://developers.google.com/analytics/devguides/collection/ga4)

- サイトの流入とかの数値を取ってくれるやつ
- 最近機構が新しくなった
- ここから API とかも作れるので、カスタマイズの余地あり

## [Sentry](https://sentry.io/)

- フロントエンドのエラートラッキングツール
- 静的配信しているのでエラーがでることはあんまり無い気がするが、無料なのでとりあえず入れとけって感じ

## [getform.io](https://getform.io/)

- お問い合わせやメンバー募集で使っているフォームツール
- 無料プランだと受付可能件数が 50 件なのだが、それでも大丈夫な気がしているので採用
- Google Form も悪くはないが、UI をすごく圧迫するので好まない
- これを使う他に、microCMS のクライアントを増やしてそこから API を生やすことも考えられる
- ちなみに Notion 上で Form を作るときは NortionForm を使えばリクエスト無制限なので、フォーム付きの LP とかは Notion ベースで作ると良い
