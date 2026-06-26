---
date: 2026-02-07
description: Aspose.Page for Java を使用して矩形を拡大縮小する方法、シェイプを平行移動する方法、そしてアフィン変換を適用して PostScript
  ドキュメントを作成する方法を学びましょう。
linktitle: Transformations in Java Page Manipulation
second_title: Aspose.Page Java API
title: Aspose.Page for Javaで矩形を拡大縮小する方法
url: /ja/java/page-manipulation/transformations/
weight: 11
---

{{< blocks/products/pf/main-wrap-class >}}
{{< blocks/products/pf/main-container >}}
{{< blocks/products/pf/tutorial-page-section >}}

# Aspose.Page for Javaで矩形をスケーリングする方法

## はじめに
**Aspose.Page for Java** の強力な機能を活用し、さまざまなページ変換を実行するための包括的なガイドへようこそ。このチュートリアルでは、**矩形のスケーリング** 方法、形状の平行移動、オブジェクトの回転、そして **アフィン変換** のテクニックを **PostScript ドキュメント** の作成時に適用する方法を学びます。これらの機能により、低レベルのレンダリングコードに悩まされることなく、リッチでグラフィック集中的な Java アプリケーションを構築できます。

## クイック回答
- **JavaでAspose.Pageを使用して矩形をスケーリングするには？** `document.scale()` メソッドを図形を描画する前に使用します。  
- **他のグラフィックに影響を与えずに形状を移動（平行移動）できますか？** はい—グラフィック状態を保存し、`document.translate(x, y)` を呼び出し、描画し、最後に状態を復元します。  
- **PostScriptファイルを作成するクラスは何ですか？** `PsDocument` と `PsSaveOptions` を組み合わせます。  
- **本番環境で使用するにはライセンスが必要ですか？** 商用展開には有効な Aspose.Page ライセンスが必要です。  
- **サポートされているJavaバージョンは？** Aspose.Page は Java 8 以降で動作します。

## 前提条件
- Javaプログラミングの基本知識。  
- Aspose.Page for Java ライブラリがインストールされていること。[Aspose.Page for Java ドキュメント](https://reference.aspose.com/page/java/) からダウンロードできます。  
- マシンに Java 統合開発環境（IDE）が設定されていること。

## パッケージのインポート
Java プロジェクトで Aspose.Page for Java を利用するために必要なパッケージをインポートします。

```java
import java.awt.Color;
import java.awt.Shape;
import java.awt.geom.AffineTransform;
import java.awt.geom.Rectangle2D;
import java.io.FileOutputStream;
import com.aspose.eps.PsDocument;
import com.aspose.eps.device.PsSaveOptions;
```

## Aspose.Pageにおける「矩形のスケーリング」とは何ですか？
矩形のスケーリングは、形状を保持しながら X 軸と Y 軸に沿ってサイズを変更することです。Aspose.Page は `scale(float sx, float sy)` メソッドを提供しており、現在のグラフィック状態に **アフィン変換** を適用します。これが **矩形のスケーリング** キーワードの核心技術です。

## Aspose.Pageで形状を平行移動する方法
平行移動は、形状の寸法を変えずに新しい位置へ移動させます。これが **形状の平行移動** の本質です。グラフィック状態を保存し、`translate(dx, dy)` を適用し、描画し、最後に状態を復元することで、他のオブジェクトへの影響を防げます。

## 例 1: 変換なし
最初の例では、変換を適用せずにシンプルな矩形を描画します。これは後続の例との比較基準となります。

```java
// The path to the documents directory.
String dataDir = "Your Document Directory";
// Create output stream for PostScript document
FileOutputStream outPsStream = new FileOutputStream(dataDir + "Tranformations_outPS.ps");
// Create save options with A4 size
PsSaveOptions options = new PsSaveOptions();
// Create new PS Document with the page opened
PsDocument document = new PsDocument(outPsStream, options, false);
// Create a rectangle
Shape shape = new Rectangle2D.Float(0, 0, 150, 100);
// Set paint in graphics state on the upper level
document.setPaint(Color.ORANGE);
// Fill the first rectangle without any transformations.
document.fill(shape);
// Close current page
document.closePage();
// Save the document
document.save();
```

## 例 2: 平行移動
ここでは **形状の平行移動** をデモンストレーションします。2 番目の矩形を描画する前に、グラフィック コンテキストを右方向へ 250 ユニット移動します。

```java
// Save graphics state to return back after transformation
document.writeGraphicsSave();
// Displace current graphics state 250 to the right
document.translate(250, 0);
// Set paint in the current graphics state
document.setPaint(Color.BLUE);
// Fill the second rectangle with translation transformation
document.fill(shape);
// Restore graphics state to the previous (upper) level
document.writeGraphicsRestore();
```

## 例 3: スケーリング
この例は主要な質問 **矩形のスケーリング** に答えます。矩形の幅を元の 50 %、高さを 75 % に縮小します。

```java
// Save graphics state to return back after transformation
document.writeGraphicsSave();
// Scale current graphics state on 0.5 in X axis and 0.75f in Y axis
document.scale(0.5f, 0.75f);
// Set paint in the current graphics state
document.setPaint(Color.RED);
// Fill the third rectangle with scale transformation
document.fill(shape);
// Restore graphics state to the previous (upper) level
document.writeGraphicsRestore();
```

## Javaで形状を回転させる方法 (rotate shape java)
回転は別の一般的なアフィン操作です。回転用のコードスニペットは簡潔さのため省略していますが、パターンは同一です：グラフィック状態を保存し、`document.rotate(angle)` を呼び出し、形状を描画し、最後に復元します。これにより **rotate shape java** と **矩形の回転** が実践で示されます。

## なぜ重要か – 実務上のメリット
- **デバイス非依存の出力** – 一度書くだけで、プラットフォーム固有の調整なしに PostScript や XPS を生成できます。  
- **細かな制御** – 平行移動、スケーリング、せん断、回転を組み合わせて、正確なレイアウト要件を満たします。  
- **パフォーマンス重視** – 大規模ドキュメントのバッチ処理に最適な低オーバーヘッド API。

## 一般的な使用例
- 印刷可能な請求書の生成 – 例えば、ロゴやバーコードを正確に配置する **printable invoice java** ソリューション。  
- 正確なスケーリングと位置決めが必要な技術図の作成。  
- PostScript 形式のマルチページレポートの自動生成。

## 一般的な問題と解決策
- **変換がリセットされない** – `document.writeGraphicsSave()` と `document.writeGraphicsRestore()` を必ず対にして、不要な引き継ぎ効果を防ぎます。  
- **予期しない色** – 各変換後にペイントを設定してください。復元後はグラフィック状態が以前の色設定を保持しません。  
- **ファイルサイズが大きすぎる** – ラスタ画像を埋め込む際は `PsSaveOptions` で圧縮を有効にするか、画像解像度を下げてください。

## FAQ

### Aspose.Page for Java を他のドキュメント形式で使用できますか？
Aspose.Page は主に PostScript と XPS 形式のページ操作に焦点を当てています。

### Aspose.Page for Java のさらなるサンプルやドキュメントはどこで見つかりますか？
包括的な情報は [Aspose.Page for Java ドキュメント](https://reference.aspose.com/page/java/) をご覧ください。

### Aspose.Page for Java の無料トライアルはありますか？
はい、無料トライアルは [こちら](https://releases.aspose.com/) から利用できます。

### Aspose.Page for Java の一時ライセンスはどう取得できますか？
一時ライセンスは [こちら](https://purchase.aspose.com/temporary-license/) から取得してください。

### Aspose.Page for Java に関するコミュニティサポートや質問はどこでできますか？
コミュニティの議論は [Aspose.Page for Java フォーラム](https://forum.aspose.com/c/page/39) をご利用ください。

## よくある質問

**Q: `translate` と `scale` の違いは何ですか？**  
**A:** `translate` は座標系の原点を移動させ、`scale` は描画オブジェクトのサイズを X 軸および/または Y 軸に沿って変更します。

**Q: 単一のグラフィック状態で複数の変換を組み合わせられますか？**  
**A:** はい—描画前に `translate`、`scale`、`rotate`、`shear` を順に呼び出すことで、合成アフィン変換を作成できます。

**Q: 図形描画後に変換をリセットするには？**  
**A:** `document.writeGraphicsRestore()` を使用して、以前に保存したグラフィック状態に戻します。

**Q: 矩形を中心周りに回転させることは可能ですか？**  
**A:** もちろん可能です。矩形を原点に平行移動し、`rotate(angle)` を適用し、描画前に元の位置に戻します。

**Q: Aspose.Page は滑らかなグラフィックのためにアンチエイリアスをサポートしていますか？**  
**A:** はい—`PsSaveOptions` で適切なレンダリングオプションを設定してアンチエイリアスを有効にします。

---

**Last Updated:** 2026-02-07  
**Tested With:** Aspose.Page for Java 24.12  
**Author:** Aspose  

{{< /blocks/products/pf/tutorial-page-section >}}

{{< /blocks/products/pf/main-container >}}
{{< /blocks/products/pf/main-wrap-class >}}

{{< blocks/products/products-backtop-button >}}