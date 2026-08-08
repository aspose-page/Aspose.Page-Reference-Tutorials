---
date: 2026-05-05
description: Aspose.Page for Java を使用して、PostScript ドキュメントにテクスチャ タイル パターンを追加する方法を学びましょう。このガイドでは、テクスチャを効率的に追加し、クリエイティブな可能性を探ります。
keywords:
- how to add texture
- fill shape with texture
- fill rectangle with texture
linktitle: Java PostScriptでテクスチャタイルパターンを追加する
second_title: Aspose.Page Java API
title: Java PostScriptでテクスチャタイルパターンを追加する方法
url: /ja/java/postscript-texture-patterns/add-texture-tiling-pattern/
weight: 10
---

{{< blocks/products/pf/main-wrap-class >}}
{{< blocks/products/pf/main-container >}}
{{< blocks/products/pf/tutorial-page-section >}}

# Java PostScript でテクスチャ タイリング パターンを追加する方法

## はじめに
Java 開発の領域では、PostScript ドキュメントに **テクスチャを追加する方法** を学ぶことは一般的な要件です。Aspose.Page for Java を使用すれば、この作業はシンプルになり、低レベルの PostScript 構文ではなくデザインに集中できます。このチュートリアルでは、テクスチャ タイリング パターンの追加、シェイプの塗りつぶし、さらにはテキストへのテクスチャ適用まで、Java の PostScript ドキュメントで必要な手順をすべて解説します。

## クイック回答
- **必要なライブラリは？** Aspose.Page for Java  
- **このガイドが対象とする主要キーワードは？** *how to add texture*  
- **テストにライセンスは必要ですか？** 無料トライアルがあります。製品版ではライセンスが必要です。  
- **サポートされている Java バージョンは？** Java 8 以上。  
- **テクスチャ ブラシを複数のシェイプで再利用できますか？** はい – `TexturePaint` を一度作成すれば、任意のシェイプに適用できます。  
- **矩形をテクスチャで塗りつぶすには？** `TexturePaint` を現在のペイントとして設定した後、`document.fill(shape)` を使用します。

## テクスチャ タイリング パターンとは？
テクスチャ タイリング パターンは、小さな画像（タイル）を大きな領域全体に繰り返し配置し、**シェイプをテクスチャで塗りつぶす** ことを可能にします。各タイルを手動で描画する必要がなく、背景や塗りつぶし、装飾的なテキスト効果に最適です。

## Aspose.Page for Java を使用する理由
- **ゼロ依存のレンダリング** – 外部の PostScript インタプリタは不要です。  
- **グラフィックスのフルコントロール** – ベクターシェイプ、テキスト、ビットマップテクスチャを組み合わせられます。  
- **クロスプラットフォーム** – Java が動作するすべての OS で利用可能です。  

## 前提条件
チュートリアルに入る前に、以下の前提条件が整っていることを確認してください。
- Java プログラミング言語の基本的な理解。  
- PostScript ドキュメント構造に関する知識。  
- Aspose.Page for Java ライブラリがインストール済み。ダウンロードは [こちら](https://releases.aspose.com/page/java/) から。

## パッケージのインポート
Java プロジェクトで必要なパッケージをインポートします。

```java
import java.awt.BasicStroke;
import java.awt.Color;
import java.awt.Font;
import java.awt.TexturePaint;
import java.awt.geom.Rectangle2D;
import java.awt.image.BufferedImage;
import java.io.File;
import java.io.FileOutputStream;
import javax.imageio.ImageIO;
import com.aspose.eps.PsDocument;
import com.aspose.eps.device.PsSaveOptions;
```

## Java PostScript でテクスチャ タイリング パターンを追加する方法
以下はステップバイステップのガイドです。各ステップには簡単な説明と、コピーして使用できる正確なコードが含まれています。

### 手順 1: PostScript ドキュメントの作成
出力ストリームと保存オプションを指定して、新しい PostScript ドキュメントを作成します。必要なパスが設定されていることを確認してください。

```java
// The path to the documents directory.
String dataDir = "Your Document Directory";
// Create output stream for PostScript document
FileOutputStream outPsStream = new FileOutputStream(dataDir + "AddTextureTilingPattern_outPS.ps");
// Create save options with A4 size
PsSaveOptions options = new PsSaveOptions();
// Create new PS Document with the page opened
PsDocument document = new PsDocument(outPsStream, options, false);
// Create new PS Document with the page opened
PsDocument document = new PsDocument(outPsStream, options, false);
```

### 手順 2: グラフィック環境の設定
原点を便利な位置に平行移動し、テクスチャ タイルとして使用するビットマップを読み込みます。

```java
document.writeGraphicsSave();
document.translate(200, 100);
// Create a BufferedImage object from image file
BufferedImage image = ImageIO.read(new File(dataDir + "TestTexture.bmp"));
```

### 手順 3: テクスチャ ブラシの作成
ビットマップをシェイプ領域全体に繰り返す `TexturePaint` を定義します。タイルを大きくしたり小さくしたりしたい場合は、矩形サイズを調整してください。

```java
// Create image area doubled in width
Rectangle2D.Float imageArea = new Rectangle2D.Float(0, 0, image.getWidth() * 2, image.getHeight());
// Create texture brush from the image
TexturePaint paint = new TexturePaint(image, imageArea);
```

### 手順 4: シェイプの描画と塗りつぶし
矩形を作成し、ブラシを使用して **テクスチャで矩形を塗りつぶす** ことができます。その後、シェイプの輪郭を描画して視覚的に区別しやすくします。

```java
// Create rectangle
Rectangle2D.Float shape = new Rectangle2D.Float(0, 0, 200, 100);
// Set this texture brush as current paint
document.setPaint(paint);
// Fill rectangle
document.fill(shape);
document.setPaint(Color.RED);
document.setStroke(new BasicStroke(2));
document.draw(shape);
```

### 手順 5: テクスチャ パターンを使用したテキストの追加
同じテクスチャをテキストのグリフにも適用できます。これにより、文字に **テクスチャを塗りつぶす** と同時にストロークを付けることが可能です。

```java
// Fill the text with the texture pattern
Font font = new Font("Arial", Font.BOLD, 96);
document.fillAndStrokeText("ABC", font, 200, 300, paint, Color.BLACK, new BasicStroke(2));
// Outline the text with the texture pattern
document.outlineText("ABC", font, 200, 400, paint, new BasicStroke(5));
```

### 手順 6: 保存とクローズ
最後にページを閉じ、ドキュメントを保存し、リソースを解放します。

```java
// Close current page
document.closePage();
// Save the document
document.save();
```

## よくある問題とヒント
- **テクスチャ ファイルが見つからない** – `TestTexture.bmp` へのパスが正しく、ファイルにアクセス可能か確認してください。  
- **画像サイズが不正** – テクスチャが伸びて見える場合は、`imageArea` を元画像のサイズに合わせて調整します。  
- **パフォーマンス** – 複数のシェイプで同じ `TexturePaint` インスタンスを再利用し、不要なオブジェクト生成を避けます。  
- **プロのコツ:** タイル用ビットマップは高解像度のものを使用し、拡大縮小時にもテクスチャが鮮明に保たれるようにします。

## よくある質問

**Q: Aspose.Page for Java は初心者に適していますか？**  
A: もちろんです！Aspose.Page for Java は包括的なドキュメントを提供しており、あらゆるスキルレベルの開発者が利用できます。

**Q: 既存の Java プロジェクトに Aspose.Page for Java を統合できますか？**  
A: はい、提供されているドキュメントに従って簡単に統合できます。詳細は [こちら](https://reference.aspose.com/page/java/) をご覧ください。

**Q: Aspose.Page に関するサポートやディスカッションはどこで行えますか？**  
A: コミュニティとやり取りしたり支援を受けたりするには、[Aspose.Page フォーラム](https://forum.aspose.com/c/page/39) をご利用ください。

**Q: Aspose.Page for Java の無料トライアルはありますか？**  
A: はい、[こちら](https://releases.aspose.com/) から無料トライアルをご利用いただけます。

**Q: Aspose.Page for Java の一時ライセンスはどのように取得できますか？**  
A: [このリンク](https://purchase.aspose.com/temporary-license/) から一時ライセンスを取得してください。

## 結論
おめでとうございます！Aspose.Page for Java を使用して、Java の PostScript ドキュメントに **テクスチャを追加する方法** をマスターしました。さまざまなビットマップタイル、スケール係数、合成操作を試して、テクスチャ塗りつぶしの創造的な可能性を最大限に引き出してください。

---

**最終更新日:** 2026-05-05  
**テスト環境:** Aspose.Page for Java 24.12 (最新)  
**作者:** Aspose  

---

{{< /blocks/products/pf/tutorial-page-section >}}

{{< /blocks/products/pf/main-container >}}
{{< /blocks/products/pf/main-wrap-class >}}

{{< blocks/products/products-backtop-button >}}