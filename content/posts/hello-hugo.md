---
title: "Hugo に移行しました"
date: 2026-08-22T02:47:23+09:00
draft: false
tags: ["hugo", "test"]
summary: "Jekyll から Hugo + PaperMod への移行が完了したので、投稿の動作確認をする。"
ShowToc: true
---

このサイトのビルドを Jekyll から Hugo + PaperMod に切り替えた。
この記事は投稿から公開までの経路が動いているかを確認するためのテストである。

## 確認したいこと

- 記事が `/posts/` の一覧とトップページに出るか
- 目次、タグ、reading time が表示されるか
- コードブロックのコピーボタンが動くか
- 検索インデックス（`/index.json`）に本文が入るか

## コードブロック

```python
import networkx as nx

G = nx.karate_club_graph()
print(nx.average_clustering(G))
```

## 投稿の手順

記事の追加は次の 3 手で済む。

```bash
hugo new content posts/2026-08-22-something.md
```

本文を書いて front matter の `draft: true` を消し、コミットして push すれば GitHub Actions が数分でビルドと公開まで進める。

確認が済んだらこの記事は削除して構わない。
