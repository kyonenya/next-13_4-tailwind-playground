# Next 13.4 playground

## 許されたライブラリたち

- [n3r4zzurr0/svg-spinners: A collection of 24 x 24 dp SVG spinners! (CSS & SMIL)](https://github.com/n3r4zzurr0/svg-spinners)
  - ゴミ：[davidhu2000/react-spinners: A collection of loading spinner components for react](https://github.com/davidhu2000/react-spinners)

## Zero-runtime CSS

- Chakra UI の Icon すらも emotion が入り込んでて使えないのでリプレースする必要あり
  - [React Icons](https://react-icons.github.io/react-icons/) あたりでいいかね
- tailwind には勝てなかったよ……
- [poteboy/kuma-ui: 🐻‍❄️ zero-runtime CSS-in-JS with type-safe utility props](https://github.com/poteboy/kuma-ui)
  - SWC では動かない、Babel ベースで AST 解析してる：[Twitter](https://twitter.com/_poteboy_/status/1665736293429690369)
- UI ライブラリは全滅だな……低レベルの UI ライブラリですら RSC 下では動作しない
- [The future of Chakra UI - Segun Adebayo](https://www.adebayosegun.com/blog/the-future-of-chakra-ui)
  - [Zag.js](https://zagjs.com/overview/installation) とかいう最低限のステートマシンなら動作するか？
  - しなかった。`useMachine` が内部的に `useRef` を参照しててエラーになった
    - Error: useRef only works in Client Components. Add the "use client" directive at the top of the file to use it. Read more: https://nextjs.org/docs/messages/react-client-hook-in-server-component
- [Support react server components · radix-ui/primitives · Discussion #2104](https://github.com/radix-ui/primitives/discussions/2104)
  Radix UI でも "use client" 必須らしいしヘッドレス UI ＋ RSC は諦めたほうがよさそう
- [Getting Started | Ark UI](https://ark-ui.com/docs/react/overview/getting-started)
  - うそだろ……Ark、RSC に対応してないんだが？

## RSC (React Server Component)

- [Next.js 13 app directory で記事投稿サイトを作ってみよう](https://zenn.dev/azukiazusa/articles/next-js-app-dir-tutorial)
  - Chakra UI ガッツリ使ってて草なんだけどそれだけに分かりやすい
- [Next.js で React Server Components を試してみた](https://zenn.dev/forcia_tech/articles/202305_next_js_rsc)
  - PostList を page.tsx で Suspense で囲ってるから layout.tsx は要らない
    - 囲わないと page.tsx から漏れ出てくるから loading.tsx でキャッチする
- [Next.js 13 の React Server Components(RSC) とデータフェッチ](https://zenn.dev/tfutada/articles/36ad71ab598019)
- [Next.js 13 の app ディレクトリの基礎(Layout, Suspense, Data Fetching...)](https://reffect.co.jp/react/next-js-13-app)
- [Turbopack](https://nextjs.org/docs/architecture/turbopack): 現状では開発環境でのみ使用できます(next dev --turbo)が、将来の Next.js のバージョンでは本番環境でも使用できるようになる(next build --turbo)予定のようです。
  [Next.js 13.4 まとめ](<https://zenn.dev/a_da_chi/articles/758f77406cda60#turbopack(%E3%83%99%E3%83%BC%E3%82%BF%E7%89%88)>)
- [Blog - Next.js 13.4 | Next.js](https://nextjs.org/blog/next-13-4)
- [fnm（Fast Node Manager）の導入方法](https://zenn.dev/kazuma_r5/articles/cd5eaf3d8b5b9f)
  - `.node-version` ファイル
