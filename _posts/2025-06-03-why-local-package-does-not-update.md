---
layout: post
title: "npm installでパッケージが更新されないときに確認すること"
---

`package.json` に記載されているパッケージを読み込みたいのに、なぜか古いバージョンがローカルに残ってしまい更新されないことがある。
その際に確認することをまとめる。

## 対処方法
1. `package.lock.json` を削除
2. `node_modules/` を削除
3. `npm cache verify` コマンドを実行しキャッシュをクリア

   ※ Next.js を使用している場合は、`.next/cache/`ディレクトリも削除したほうがよい。
4. `npm install` でパッケージを再インストール


## 参考
- [npm cache](https://docs.npmjs.com/cli/v11/commands/npm-cache)
