---
date: 2025-12-07
description: Aspose.Page を使用して Java で矩形の拡大縮小、形状の平行移動、アフィン変換を行い、PostScript ドキュメントを作成する方法を学びます。
linktitle: Transformations in Java Page Manipulation
second_title: Aspose.Page Java API
title: Aspose.Pageで矩形を拡大縮小し、変換を適用する方法
url: /ja/java/page-manipulation/transformations/
weight: 11
---

{{< blocks/products/pf/main-wrap-class >}}
{{< blocks/products/pf/main-container >}}
{{< blocks/products/pf/tutorial-page-section >}}

# Aspose.Pageで矩形を拡大縮小し、変換を適用する方法

## Introduction
**Aspose.Page for Java** の強力な機能を活用して、さまざまなページ変換を実行するための包括的なガイドへようこそ。このチュートリアルでは、**矩形の拡大縮小方法**、シェイプの平行移動、オブジェクトの回転、そして **アフィン変換** のテクニックを **PostScript ドキュメント** の作成時に適用する方法を学びます。これらの機能により、低レベルのレンダリングコードに悩むことなく、グラフィック集中的な Java アプリケーションを構築できます。

## Quick Answers
- **Aspose.Page を使用して Java で矩形を拡大縮小するには？** シェイプを描画する前に `document.scale()` メソッドを使用します。  
- **他のグラフィックに影響を与えずにシェイプを移動（平行移動）できますか？** はい。グラフィック状態を保存し、`document.translate(x, y)` を呼び出して描画し、最後に状態を復元します。  
- **PostScript ファイルを作成するクラスは？** `PsDocument` と `PsSaveOptions` を組み合わせて使用します。  
- **本番環境で使用する際にライセンスは必要ですか？** 商用デプロイには有効な Aspose.Page ライセンスが必要です。  
- **対応している Java バージョンは？** Aspose.Page は Java 8 以降で動作します。

## Prerequisites
ステップバイステップのガイドに入る前に、以下の前提条件が整っていることを確認してください。

- Java プログラミングの基本知識。  
- Aspose.Page for Java ライブラリがインストール済み。ダウンロードは [Aspose.Page for Java documentation](https://reference.aspose.com/page/java/) から行えます。  
- マシンに Java 用統合開発環境（IDE）が設定済み。

## Import Packages
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

## What is “how to scale rectangle” in Aspose.Page?
矩形の拡大縮小とは、形状を保ったまま X 軸と Y 軸方向のサイズを変更することです。Aspose.Page は `scale(float sx, float sy)` メソッドを提供しており、現在のグラフィック状態に **アフィン変換** を適用します。これが **矩形の拡大縮小方法** キーワードの核心です。

## How to Translate Shape with Aspose.Page
平行移動は、シェイプの位置を変更しつつサイズは変えない操作です。これが **シェイプの平行移動方法** の本質です。グラフィック状態を保存し、`translate(dx, dy)` を適用して描画し、最後に状態を復元することで、他のオブジェクトに影響を与えません。

## Example 1: No Transformations
最初の例は、変換を一切適用せずにシンプルな矩形を描画します。これは後続の例と比較するためのベースラインとなります。

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

## Example 2: Translation
ここでは **シェイプの平行移動方法** を示すため、2 番目の矩形を描画する前にグラフィックコンテキストを右方向へ 250 ユニット移動します。

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

## Example 3: Scaling
この例は主要な質問 **矩形の拡大縮小方法** に答えます。矩形の幅を元の 50 %、高さを 75 % に縮小します。

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

## How to Rotate Shape Java (rotate shape java)
回転はもう一つの一般的なアフィン操作です。回転用のコードスニペットは簡潔さのため省略していますが、パターンは同じです：グラフィック状態を保存し、`document.rotate(angle)` を呼び出してシェイプを描画し、最後に状態を復元します。これにより **rotate shape java** と **how to rotate rectangle** を実践できます。

## Why Use Aspose.Page for These Transformations?
- **デバイス非依存**：一度書くだけで、プラットフォーム固有のコードなしに PostScript や XPS を生成できます。  
- **細かな制御**：グラフィック状態への直接アクセスにより、平行移動、拡大縮小、せん断、回転を組み合わせられます。  
- **パフォーマンス**：大規模ドキュメントのバッチ処理に適した低オーバーヘッド API です。  

## Common Use Cases
- 動的なバーコードやロゴを含む印刷可能な請求書の生成。  
- 正確な拡大縮小と位置決めが必要な技術図面の作成。  
- PostScript 形式のマルチページレポートの自動生成。

## Conclusion
このチュートリアルでは、Aspose.Page for Java を使用した Java ページ操作におけるさまざまな変換を取り上げ、**矩形の拡大縮小方法**、**シェイプの平行移動方法**、その他のアフィン操作に焦点を当てました。これらの例に従うことで、Java アプリケーションに高度なページ操作機能を追加し、**PostScript ドキュメント** をプロフェッショナルな出版基準に合わせて作成できます。

## FAQ's
### Aspose.Page for Java を他のドキュメント形式で使用できますか？
Aspose.Page は主に PostScript と XPS 形式のページ操作に特化しています。

### Aspose.Page for Java のサンプルやドキュメントはどこで入手できますか？
包括的な情報は [Aspose.Page for Java documentation](https://reference.aspose.com/page/java/) をご覧ください。

### Aspose.Page for Java の無料トライアルはありますか？
はい、無料トライアルは [here](https://releases.aspose.com/) から利用できます。

### Aspose.Page for Java の一時ライセンスはどこで取得できますか？
一時ライセンスは [here](https://purchase.aspose.com/temporary-license/) から取得できます。

### Aspose.Page for Java に関するコミュニティサポートや質問はどこでできますか？
コミュニティディスカッションは [Aspose.Page for Java forum](https://forum.aspose.com/c/page/39) をご利用ください。

## Frequently Asked Questions

**Q: `translate` と `scale` の違いは何ですか？**  
A: `translate` は座標系の原点を移動させ、`scale` は描画オブジェクトのサイズを X 軸または Y 軸方向に変更します。

**Q: 複数の変換を単一のグラフィック状態で組み合わせられますか？**  
A: はい。`translate`、`scale`、`rotate`、`shear` を順に呼び出すことで、合成アフィン変換を作成できます。

**Q: シェイプ描画後に変換をリセットするには？**  
A: `document.writeGraphicsRestore()` を使用して、以前に保存したグラフィック状態に戻します。

**Q: 矩形を中心を基点に回転させることは可能ですか？**  
A: 可能です。矩形を原点に平行移動し、`rotate(angle)` を適用してから元の位置に戻して描画します。

**Q: Aspose.Page は滑らかなグラフィックのためにアンチエイリアスをサポートしていますか？**  
A: はい。`PsSaveOptions` の適切なレンダリングオプションを設定することでアンチエイリアスを有効にできます。

---

**Last Updated:** 2025-12-07  
**Tested With:** Aspose.Page for Java 24.12  
**Author:** Aspose  

{{< /blocks/products/pf/tutorial-page-section >}}

{{< /blocks/products/pf/main-container >}}
{{< /blocks/products/pf/main-wrap-class >}}

{{< blocks/products/products-backtop-button >}}