---
date: 2026-08-23
description: aspose.page の image manipulation java を使用して、PostScript ファイルに画像を埋め込み、回転させる方法を、わかりやすい
  Java のサンプルで学びましょう。
keywords:
- aspose.page image manipulation java
- add image postscript java
- java postscript image rotation
- aspose.page java tutorial
- image embedding java
lastmod: 2026-08-23
linktitle: Java PostScript で画像を追加
og_description: aspose.page の image manipulation java を使用して、PostScript ファイルに画像を埋め込み、回転させる方法を、ステップバイステップの
  Java コード例で学べます。
og_image_alt: Guide showing Java code to add and rotate images in PostScript using
  Aspose.Page
og_title: aspose.page の image manipulation java を使用して画像を追加する方法
schemas:
- author: Aspose
  dateModified: '2026-08-23'
  description: Learn how to use aspose.page image manipulation java to embed and rotate
    images in PostScript files with clear Java examples.
  headline: How to use aspose.page image manipulation java to add image
  type: TechArticle
- description: Learn how to use aspose.page image manipulation java to embed and rotate
    images in PostScript files with clear Java examples.
  name: How to use aspose.page image manipulation java to add image
  steps:
  - name: write graphics save
    text: Saving the graphics state isolates your transformations so you can revert
      later. This is equivalent to the `gsave` operator in raw PostScript.
  - name: translate and transform (translate and rotate image)
    text: First, create a `BufferedImage` from the source file, then build an `AffineTransform`
      that translates the image to the desired coordinates and rotates it around its
      centre. `AffineTransform.rotate` expects an angle in radians, so convert degrees
      with `Math.toRadians(degrees)`. **AffineTransform** is
  - name: add image to document
    text: After configuring the transform, draw the image onto the current page. The
      library automatically converts the `BufferedImage` into an appropriate PostScript
      image stream.
  - name: write graphics restore
    text: Calling restore (`grestore`) returns the graphics state to what it was before
      the save, ensuring subsequent drawing commands are not affected by the previous
      transformation.
  - name: close current page and save
    text: Finish the page, close the document, and write the output file to disk.
      You can repeat the above sequence to embed additional images, adjusting the
      translation coordinates and rotation angle each time.
  type: HowTo
- questions:
  - answer: The core library is Java‑only, but Aspose provides equivalent APIs for
      .NET, C++, and Python, each tailored to its platform.
    question: Can I use Aspose.Page for Java with other programming languages?
  - answer: Yes, you can access the free trial **[Aspose.Page free trial page](https://releases.aspose.com/)**.
    question: Is there a free trial available for Aspose.Page for Java?
  - answer: You can get a temporary license **[temporary license request page](https://purchase.aspose.com/temporary-license/)**.
    question: How can I obtain a temporary license for Aspose.Page for Java?
  - answer: Visit the **[Aspose.Page Forum](https://forum.aspose.com/c/page/39)**
      for community assistance.
    question: Where can I find community support and discussions related to Aspose.Page
      for Java?
  - answer: You can buy the library **[Aspose.Page purchase page](https://purchase.aspose.com/buy)**.
    question: Are there any additional resources for purchasing Aspose.Page for Java?
  type: FAQPage
second_title: Aspose.Page Java API
tags:
- aspose.page
- java image manipulation
- postscript
- image rotation
- java tutorial
title: aspose.page の image manipulation java を使用して画像を追加する方法
url: /ja/java/postscript-image-manipulation/add-image/
weight: 10
---

{{< blocks/products/pf/main-wrap-class >}}
{{< blocks/products/pf/main-container >}}
{{< blocks/products/pf/tutorial-page-section >}}

# aspose.page 画像操作 Java を使用して画像を追加する方法

## はじめに
このチュートリアルでは、**aspose.page 画像操作 Java** を使用して PostScript ファイルを作成し、ラスター画像を埋め込み、平行移動と回転の変換を適用する方法を学びます。ガイドの最後までに、Java からピクセル単位で正確な PostScript 出力を生成できるようになり、レポートの自動化、印刷パイプライン、または PostScript ドキュメント内で画像を正確に配置する必要があるあらゆるワークフローに最適です。

## クイック回答
- **必要なライブラリは何ですか？** Aspose.Page for Java  
- **複数の画像を追加できますか？** はい – 各画像に対して変換と描画の手順を繰り返します  
- **開発にライセンスは必要ですか？** テストには無料トライアルで動作しますが、本番環境ではライセンスが必要です  
- **サポートされている Java バージョンは？** Java 8 以降  
- **画像の回転はサポートされていますか？** もちろんです – `AffineTransform.rotate()` を使用します  

## aspose.page 画像操作 Java とは？
`aspose.page image manipulation java` は、Java コードからプログラム的に PostScript ドキュメントを構築、編集、レンダリングできる Aspose.Page API で、画像の配置、スケーリング、回転を完全に制御できます。この API を使用すると、低レベルの PostScript 構文を回避し、ライブラリが内部でフォーマット変換と埋め込みを処理します。

## なぜ画像操作に aspose.page を使用するのか？
Aspose.Page は **50 以上の画像フォーマット**（JPEG、PNG、BMP、TIFF など）を提供し、ドキュメント全体をメモリに読み込むことなく PostScript に埋め込むことができ、数百ページのファイルを処理しながら、一般的なサーバーでメモリ使用量を 100 MB 未満に抑えます。高レベルの API は複雑な PostScript コマンドを抽象化するため、生の PS 演算子ではなく簡潔な Java コードを書くだけで済みます。

## 前提条件
- Java Development Kit (JDK) 8 以上がインストールされていること。  
- Aspose.Page for Java ライブラリ – **[Aspose.Page for Java ダウンロードページ](https://releases.aspose.com/page/java/)** からダウンロードしてください。  
- Java の構文とオブジェクト指向プログラミングの基本的な知識。

## create postscript java とは？
Java から PostScript ファイルを作成することは、PostScript 言語を使用してページレイアウト、ベクターグラフィック、ラスター画像を記述する `.ps` ドキュメントをプログラム的に生成することを意味します。Aspose.Page は Java の呼び出しを有効な PostScript 命令に変換し、別途 PostScript インタプリタを使用せずに印刷可能なファイルを作成できます。

## 画像を平行移動と回転で追加する手順

画像を読み込み、`AffineTransform` を適用し、ページに描画します。以下の手順で正確なシーケンスを示します。

### 手順 1: グラフィックスの保存
グラフィックス状態を保存すると、変換を分離でき、後で元に戻すことができます。これは生の PostScript の `gsave` 演算子に相当します。

```java
import java.awt.geom.AffineTransform;
import java.awt.image.BufferedImage;
import java.io.File;
import java.io.FileOutputStream;
import javax.imageio.ImageIO;
import com.aspose.eps.PsDocument;
import com.aspose.eps.device.PsSaveOptions;
```

### 手順 2: 平行移動と変換（画像の平行移動と回転）
まず、ソースファイルから `BufferedImage` を作成し、次に画像を目的の座標に平行移動し、中心を軸に回転させる `AffineTransform` を構築します。`AffineTransform.rotate` はラジアン単位の角度を期待するため、`Math.toRadians(degrees)` で度数を変換します。

**AffineTransform** は、平行移動、回転、スケーリング、せん断などの 2 次元アフィン変換を表す Java クラスです。  
**BufferedImage** は、画像をピクセルのラスタとしてメモリに格納する Java クラスです。

```java
// The path to the documents directory.
String dataDir = "Your Document Directory";
// Create output stream for PostScript document
FileOutputStream outPsStream = new FileOutputStream(dataDir + "AddImage_outPS.ps");
// Create save options with A4 size
PsSaveOptions options = new PsSaveOptions();
// Create new PS Document with the page opened
PsDocument document = new PsDocument(outPsStream, options, false);
document.writeGraphicsSave();
```

### 手順 3: 画像をドキュメントに追加
変換を設定した後、画像を現在のページに描画します。ライブラリは `BufferedImage` を自動的に適切な PostScript 画像ストリームに変換します。

```java
document.translate(100, 100);
// Create a BufferedImage object from the image file
BufferedImage image = ImageIO.read(new File(dataDir + "TestImage Format24bppRgb.jpg"));
// Create image transform
AffineTransform transform = new AffineTransform();
transform.translate(35, 300);
transform.scale(3, 3);
transform.rotate(-45);
```

### 手順 4: グラフィックスの復元
復元 (`grestore`) を呼び出すと、保存前のグラフィックス状態に戻り、以降の描画コマンドが前の変換の影響を受けないようにします。

```java
document.drawImage(image, transform, null);
```

### 手順 5: 現在のページを閉じて保存
ページを終了し、ドキュメントを閉じ、出力ファイルをディスクに書き込みます。

```java
document.writeGraphicsRestore();
```

上記のシーケンスを繰り返すことで、追加の画像を埋め込むことができ、その都度平行移動座標と回転角度を調整します。

## よくある問題と解決策
- **FileNotFoundException:** `dataDir` がファイル区切り文字（`/` または `\\`）で終わっていること、画像ファイル名が正確に一致していることを確認してください。  
- **ImageIO.read が null を返す:** 画像フォーマットがサポートリスト（JPEG、PNG、BMP、GIF、TIFF）に含まれていることを確認してください。  
- **回転角度が正しくない:** `AffineTransform.rotate` はラジアンで動作するため、度数から変換する際は `Math.toRadians(degrees)` を使用してください。  
- **大きなページでメモリが急増:** `Document.save` 時に `saveOptions.setCompress(true)` を使用してメモリ使用量を削減してください。

## よくある質問

**Q: Aspose.Page for Java を他のプログラミング言語と併用できますか？**  
A: コアライブラリは Java のみですが、Aspose は .NET、C++、Python 用の同等 API を提供しており、各プラットフォームに合わせて最適化されています。

**Q: Aspose.Page for Java の無料トライアルはありますか？**  
A: はい、無料トライアルは **[Aspose.Page 無料トライアルページ](https://releases.aspose.com/)** から利用できます。

**Q: Aspose.Page for Java の一時ライセンスはどのように取得できますか？**  
A: 一時ライセンスは **[一時ライセンス申請ページ](https://purchase.aspose.com/temporary-license/)** から取得できます。

**Q: Aspose.Page for Java に関するコミュニティサポートやディスカッションはどこで見つけられますか？**  
A: コミュニティ支援は **[Aspose.Page フォーラム](https://forum.aspose.com/c/page/39)** をご覧ください。

**Q: Aspose.Page for Java の購入に関する追加リソースはありますか？**  
A: ライブラリは **[Aspose.Page 購入ページ](https://purchase.aspose.com/buy)** から購入できます。

## 結論
これで、PostScript ファイルを作成し、画像を平行移動・回転させ、結果を保存する **aspose.page 画像操作 Java** の完全なエンドツーエンド例が手に入りました。ベクターグラフィック、カスタムページサイズ、テキストレンダリングなどの高度な機能については、完全な **[ドキュメント](https://reference.aspose.com/page/java/)** をご覧ください。

---

**Last Updated:** 2026-08-23  
**Tested With:** Aspose.Page for Java 23.11  
**Author:** Aspose  








```java
document.closePage();
document.save();
```

## 関連チュートリアル

- [Aspose.Page Java API を使用して PostScript を PDF に変換する方法](/page/java/postscript-conversion/to-pdf/)
- [グラデーションの追加: Aspose.Page Java を使用した Java PostScript の対角グラデーション](/page/java/postscript-gradient-addition/diagonal/)
- [Aspose.Page を使用した Java PostScript にハッチパターンを追加する方法](/page/java/postscript-hatch-patterns/add-hatch-pattern/)


{{< /blocks/products/pf/tutorial-page-section >}}

{{< /blocks/products/pf/main-container >}}
{{< /blocks/products/pf/main-wrap-class >}}

{{< blocks/products/products-backtop-button >}}