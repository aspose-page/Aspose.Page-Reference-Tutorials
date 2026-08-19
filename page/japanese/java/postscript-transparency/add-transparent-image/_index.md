---
date: 2026-03-05
description: Aspose.Page for Java を使用して、Java で背景色を設定し、PostScript に透過画像を追加する方法を学びましょう。PNG
  を簡単に PostScript に変換できます。
linktitle: Add Transparent Image in Java PostScript
second_title: Aspose.Page Java API
title: 'Javaで背景色を設定: 透明画像をPSに追加'
url: /ja/java/postscript-transparency/add-transparent-image/
weight: 10
---

{{< blocks/products/pf/main-wrap-class >}}
{{< blocks/products/pf/main-container >}}
{{< blocks/products/pf/tutorial-page-section >}}

# Javaで背景色を設定: 透明画像をPSに追加

## Introduction
Java PostScriptで作業中に **set background color java** が必要な場合、透明画像を追加するとドキュメントが洗練されたプロフェッショナルな外観になります。このチュートリアルでは、カラー背景の設定、PNG を PostScript に変換、そして Aspose.Page for Java ライブラリを使用して不透明画像と透明画像の両方を描画する完全な手順を解説します。最後には **add image to postscript** ファイルに対して不透明度を完全に制御できるようになります。

## Quick Answers
- **Java PostScriptで透明度を扱うライブラリは何ですか？** Aspose.Page for Java.  
- **画像を描画する前に背景色を設定できますか？** はい – `document.setPaint()` と `fill()` を使用します。  
- **PNG を PostScript に変換する方法は？** `ImageIO.read()` で PNG を読み込み、`drawImage` または `drawTransparentImage` で描画します。  
- **画像の不透明度はサポートされていますか？** `drawTransparentImage` を使用して不透明度の値 (0‑255) を指定します。  
- **本番環境で使用するにはライセンスが必要ですか？** 有効な Aspose.Page for Java ライセンスが必要です。無料トライアルも利用可能です。

## Prerequisites
始める前に、以下が揃っていることを確認してください：

1. **Java Development Kit (JDK)** – 最新バージョンがインストールされていること。  
2. **Aspose.Page for Java** – [website](https://releases.aspose.com/page/java/) からダウンロードしてください。  
3. **Document Directory** – PostScript ファイルを書き込むフォルダー。  
4. **Translucent Image File** – 例: `mask1.png`、透明性のデモに使用します。

## Import Packages
Java プロジェクトで必要なクラスをインポートします。このブロックは変更しません：

```java
import java.awt.Color;
import java.awt.geom.AffineTransform;
import java.awt.geom.Rectangle2D;
import java.awt.image.BufferedImage;
import java.io.File;
import java.io.FileOutputStream;
import javax.imageio.ImageIO;
import com.aspose.eps.PsDocument;
import com.aspose.eps.device.PsSaveOptions;
```

## Step 1: Set Background Color Java
ここではドキュメントを作成し、A4 サイズを選択し、背景のコントラストを示すために赤い矩形を塗りつぶします。

```java
// The path to the documents directory.
String dataDir = "Your Document Directory";
// Create output stream for PostScript document
FileOutputStream outPsStream = new FileOutputStream(dataDir + "AddTransparentImage_outPS.ps");
// Create save options with A4 size
PsSaveOptions options = new PsSaveOptions();
// Create new PS Document with the page opened
PsDocument document = new PsDocument(outPsStream, options, false);
// Add a red rectangle under images for visual contrast
document.setPaint(new Color(211, 8, 48));
document.fill(new Rectangle2D.Float(0, 0, (int) options.getPageSize().getWidth(), 300));
```

## Step 2: Translate Coordinates
画像を配置する前に、描画カーソルをページ上の便利な位置に移動します。

```java
// Translate to a specific position on the page
document.writeGraphicsSave();
document.translate(20, 100);
```

## Step 3: Create Image Object
PNG ファイルをロードします（**convert png to postscript** 手順）。

```java
// Create an image from the translucent image file
BufferedImage image = ImageIO.read(new File(dataDir + "mask1.png"));
```

## Step 4: Add Opaque Image
画像を通常通り描画します—これは透明度なしで **add image to postscript** を示します。

```java
// Add the image to the document as an opaque RGB image
document.drawImage(image, new AffineTransform(1, 0, 0, 1, 100, 0), null);
```

## Step 5: Add Transparent Image (draw image with opacity)
ここでは `drawTransparentImage` を使用して、同じ PNG を完全な不透明度 (255) で描画します。値を調整して透明度を制御してください。

```java
// Add the image to the document as a transparent image
document.drawTransparentImage(image, new AffineTransform(1, 0, 0, 1, 350, 0), 255);
```

## Step 6: Save and Close
ドキュメントを確定し、リソースを解放します。

```java
// Save and close the document
document.writeGraphicsRestore();
document.closePage();
document.save();
```

## Why This Matters
Java で背景色を設定すると、重ねたグラフィックを際立たせるキャンバスが得られます。これに **draw image with opacity** を組み合わせることで、外部の編集ツールを使わずに、透かしやロゴ、UI モックアップを直接 PostScript に作成できます。

## Common Issues & Tips
- **画像が透明にならない:** PNG にアルファチャンネルが含まれているか確認してください。  
- **色が正しくない:** 背景矩形は画像の前に描画されます。デザインに合わせて `Color` の値を変更してください。  
- **パフォーマンス:** 大きなドキュメントでは、`AffineTransform` インスタンスを再利用してオブジェクト生成のオーバーヘッドを減らしましょう。

## Frequently Asked Questions

**Q: Aspose.Page for Java を他の Java ライブラリと併用できますか？**  
A: はい、Aspose.Page for Java は他の Java ライブラリとシームレスに統合でき、ドキュメント処理機能を強化します。

**Q: Aspose.Page for Java の無料トライアルは利用できますか？**  
A: はい、[here](https://releases.aspose.com/) から Aspose.Page for Java の無料トライアルにアクセスできます。

**Q: Aspose.Page for Java の一時ライセンスはどのように取得できますか？**  
A: [this link](https://purchase.aspose.com/temporary-license/) から一時ライセンスを取得できます。

**Q: Aspose.Page for Java のサポートフォーラムはありますか？**  
A: はい、コミュニティサポートとディスカッションのために [Aspose.Page for Java forum](https://forum.aspose.com/c/page/39) をご利用ください。

**Q: Aspose.Page for Java のドキュメントはどこで見つけられますか？**  
A: 詳細情報は包括的な [documentation](https://reference.aspose.com/page/java/) を参照してください。

---

**最終更新日:** 2026-03-05  
**テスト環境:** Aspose.Page for Java 24.11 (latest)  
**作者:** Aspose  

{{< /blocks/products/pf/tutorial-page-section >}}

{{< /blocks/products/pf/main-container >}}
{{< /blocks/products/pf/main-wrap-class >}}

{{< blocks/products/products-backtop-button >}}