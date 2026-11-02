# golden-angle-drift

**Phyllotaxis Chaos — 秩序ある葉の生成**

黄金角(golden angle, ≈137.5°)による葉序(phyllotaxis)配置と、ロジスティック写像(logistic map)によるカオスを組み合わせた生成アート。植物が見せる秩序だった螺旋パターンに、決定論的カオスの揺らぎを差し込むとどうなるかを visualize しています。

## 見る

`index.html` をブラウザで直接開くだけで動作します(ビルド不要・依存ライブラリなし、Canvas 2D のみ)。

GitHub Pages を有効にすれば、そのままオンラインで公開・共有できます。

## 仕組み

- **配置**: 各「葉」は `n * GOLDEN_ANGLE` の角度と `sqrt(n)` の半径で螺旋状に配置される、古典的な phyllotaxis モデル。
- **カオス**: ロジスティック写像 `x → r·x·(1-x)` を用いて、
  - 葉ごとの角度に揺らぎ(golden angle drift)を与え、
  - 葉ごとの大きさ・色・明滅を、各葉が持つ独立したロジスティック軌道で駆動し、
  - 全体の出現タイミングにも不規則性を与えています。
- 成長率 `r` を上げていくと、系は 収束 → 周期倍分岐 → カオス的レジーム へと遷移します(ロジスティック写像のカオスへの道)。

## 操作パネル

| パラメータ | 内容 |
|---|---|
| growth rate `r` | ロジスティック写像の成長率。低いほど秩序的、`r > 3.57` あたりでカオス的になる |
| golden angle drift | カオスが黄金角にどれだけ揺らぎを与えるか |
| density | 画面上に同時に存在する葉の最大数 |
| spawn speed | 葉が生成される速さ |
| trail / fade | 軌跡の残り方(値が小さいほど長く尾を引く) |

画面をクリックすると、螺旋の中心をその位置へなめらかに移動できます。右下のボタンでパネルの表示/非表示を切り替えられます。

## 技術

- 素の HTML / CSS / JavaScript(フレームワーク・ビルドツールなし)
- 描画は Canvas 2D API
- 外部依存なし

## ライセンス / License

### コード / Code
このリポジトリのコードは [PolyForm Noncommercial License 1.0.0](https://polyformproject.org/licenses/noncommercial/1.0.0) で公開しています。
個人の学習・研究・趣味などの**非商用の利用・改変・再配布は自由**です。**商用利用はできません。**

The code in this repository is licensed under the PolyForm Noncommercial License 1.0.0.
Noncommercial use, modification and redistribution are permitted. **Commercial use is not permitted.**

### Symbea の作品 / Symbea artworks
Symbea として公開・販売している作品（壁紙パック、SNS の投稿、グッズのデザインなど）の著作権は Symbealab に帰属します（All rights reserved）。

### 商用利用のご相談 / Commercial licensing
商用でのご利用を希望される場合は、Instagram [@symbealab](https://www.instagram.com/symbealab/) の DM でご相談ください。
For commercial licensing, please contact [@symbealab](https://www.instagram.com/symbealab/) on Instagram.
