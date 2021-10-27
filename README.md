# docker-vivliostyle
vivliostyle

[公式チュートリアル](https://docs.vivliostyle.org/#/ja/create-book)

## instal
```
npm ci
```

## 作成
* 本を作成
```
npm create book <directory>
```

`scripts` に `--no-sandbox` を付ける。
※Chromium の root ユーザ起動対策

```js:pakage.json
{
  "name": "sample",
  "description": "sample",
  "version": "0.0.0",
  "author": "こぴぺたん <@c_a_p_engineer>",
  "scripts": {
    "build": "vivliostyle build --no-sandbox",
    "preview": "vivliostyle preview --no-sandbox"
  },
  "dependencies": {
    "@vivliostyle/cli": "latest",
    "@vivliostyle/theme-techbook": "^0.3.1"
  },
  "license": "MIT",
  "private": true
}

```

* pdf 作成
```
npm run build
```

* プレビュー
```
npm run preview
```
※プレビュー時は http://localhost:6080/ に接続して実行してください。

## フォルダ分け

```
└ book
  ├ index.md
  ├ 01.md
  ├ 02.md
  ├ 03.md
  └ colophon.md
```

```javascript:vivliostyle.config.js
entry: [
  'book/index.md',
  'book/01.md',
  'book/02.md',
  'book/03.md',
  'book/colophon.md',
],
```

## 参考
* [Vivliostyle — 楽しく CSS 組版！](https://vivliostyle.org/ja/)
* [Vivliostyle ドキュメント | docs.vivliostyle.org](https://docs.vivliostyle.org/ja/)
* [Vivliostyle：とにかくCreate Bookのサンプルをビルドしてみる（中編その1）](https://zenn.dev/sky_y/articles/markdown-advent-2020-vivliostyle2)
* [Vivliostyle: 技術同人誌をつくって入稿用PDFをビルドする（後編）](https://zenn.dev/sky_y/articles/markdown-advent-2020-vivliostyle4)
