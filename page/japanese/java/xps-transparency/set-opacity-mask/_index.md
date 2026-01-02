---
date: 2026-01-02
description: Aspose.Page Java を使用して XPS ドキュメントに不透明度マスクを追加する方法を学びましょう。ステップバイステップのガイドで、不透明度マスクの矩形を作成し、視覚的品質を向上させます。
linktitle: Set Opacity Mask in Java XPS
second_title: Aspose.Page Java API
title: Aspose.Page Java を使用した Java XPS での不透明度マスクの設定
url: /ja/java/xps-transparency/set-opacity-mask/
weight: 11
---

{{< blocks/products/pf/main-wrap-class >}}
{{< blocks/products/pf/main-container >}}
{{< blocks/products/pf/tutorial-page-section >}}

# Aspose.Page Java を使用した Java XPS の不透明度マスクの設定

## はじめに
Welcome to our comprehensive guide on **aspose page java** opacity masks. In this tutorial you’ll learn how to create an XPS document, add a canvas, and apply an opacity mask to a rectangle—all with the powerful Aspose.Page Java API. By the end you’ll be able to add opacity mask rectangles that give your XPS files a polished, semi‑transparent look.

## クイック回答
- **不透明度マスクは何をするものですか？** 形状の透明度レベルを変化させ、下のコンテンツが透けて見えるようにします。  
- **必要なライブラリはどれですか？** Aspose.Page for Java (aspose page java)。  
- **ライセンスは必要ですか？** テスト用には一時ライセンスで動作しますが、本番環境ではフルライセンスが必要です。  
- **コード行数はどれくらいですか？** Javaで約20行に加えて、いくつかのセットアップ文があります。  
- **マスクを複数の形状で再利用できますか？** はい、同じ ImageBrush を複数のパスに割り当てることができます。  

## XPS における不透明度マスクとは？
An opacity mask is a bitmap or vector that controls the alpha (transparency) of each pixel in a shape. When applied to a rectangle, parts of the rectangle become fully opaque, partially transparent, or fully transparent, creating sophisticated visual effects.

## なぜ Aspose.Page Java を不透明度マスクに使用するのか？
- **Full .NET‑style API in Java** – 直感的なオブジェクトモデル。  
- **No external dependencies** – 純粋な Java で動作します。  
- **High‑fidelity rendering** – マスクは XPS 仕様通りに正確にレンダリングされます。  
- **Cross‑platform** – Windows、Linux、macOS で変更なしで実行できます。  

## 前提条件
- Java プログラミングの基本的な理解。  
- Aspose.Page for Java ライブラリがインストールされていること。**[here](https://releases.aspose.com/page/java/)** からダウンロードできます。  
- 有効な Aspose.Page ライセンス。お持ちでない場合は、**[here](https://purchase.aspose.com/temporary-license/)** から一時ライセンスを取得してください。  
- Java アプリケーションをコンパイル・実行できる開発環境（例: IntelliJ IDEA、Eclipse、VS Code）。  

## パッケージのインポート
Start by importing the necessary classes from the Aspose.Page library. This ensures the API is available to your project.

```java
import com.aspose.xps.XpsCanvas;
import com.aspose.xps.XpsDocument;
import com.aspose.xps.XpsImageBrush;
import com.aspose.xps.XpsPath;
import com.aspose.xps.XpsTileMode;
import java.awt.geom.Rectangle2D;
```

## ステップバイステップガイド

### ステップ 1: 新しい XPS ドキュメントを作成する
First, instantiate a fresh XPS document that will hold all of our graphics.

```java
// Create a new XPS document
XpsDocument doc = new XpsDocument();
```

### ステップ 2: キャンバスを追加する
A canvas acts as a drawing surface inside the XPS page.

```java
// New canvas
XpsCanvas canvas = doc.addCanvas();
```

### ステップ 3: 四角形を追加し、単色塗りを適用する
Here we create a rectangle path and give it a solid red fill. This rectangle will later receive the opacity mask.

```java
// Rectangle in the middle left with opacity masked by ImageBrush
XpsPath path = canvas.addPath(doc.createPathGeometry("M 10,180 L 228,180 228,285 10,285"));
path.setFill(doc.createSolidColorBrush(doc.createColor(1.0f, 0.0f, 0.0f)));
```

### ステップ 4: ImageBrush を使用して不透明度マスクを追加する
We load a TIFF image, define source and destination rectangles, and set the brush to tile mode so the mask repeats if needed.

```java
path.setOpacityMask(doc.createImageBrush(dataDir +  "R08SY_NN.tif", 
                    new Rectangle2D.Float(0f, 0f, 128f, 192f), new Rectangle2D.Float(0f, 0f, 64f, 96f)));
((XpsImageBrush)path.getOpacityMask()).setTileMode(XpsTileMode.Tile);
```

### ステップ 5: 結果の XPS ドキュメントを保存する
Finally, persist the document to disk. The output file will contain the rectangle with the applied opacity mask.

```java
// Save resultant XPS document
doc.save(dataDir + "OpacityMask_out.xps"); 
```

Follow these steps carefully to incorporate **add opacity mask** functionality into your Java XPS document using Aspose.Page.

## 一般的な問題とトラブルシューティング
- **Image not found** – `dataDir` が正しいフォルダーを指しているか、`R08SY_NN.tif` が存在するか確認してください。  
- **Mask appears solid** – ソース画像に実際にアルファ値の変化があるか確認してください。完全に不透明な画像では透明度は表示されません。  
- **Tile mode not respected** – タイルが目立つようにするには、デスティネーション矩形がソース矩形より小さい必要があります。  

## よくある質問

**Q: Aspose.Page はすべての Java 開発環境と互換性がありますか？**  
A: Yes, Aspose.Page is designed to work seamlessly with various Java IDEs and build tools.

**Q: Aspose.Page をライセンスなしで使用できますか？**  
A: While you can evaluate the library with a temporary license, a full license is required for production use.

**Q: 試用版に制限はありますか？**  
A: The trial may impose size or feature restrictions; consult the official documentation for details.

**Q: Aspose.Page のサポートはどうすれば受けられますか？**  
A: Visit the **[Aspose.Page forum](https://forum.aspose.com/c/page/39)** for community help or purchase a license for premium assistance.

**Q: Aspose.Page に返金保証はありますか？**  
A: Refer to the **[purchase page](https://purchase.aspose.com/buy)** for information on refund policies.

---

**最終更新日:** 2026-01-02  
**テスト環境:** Aspose.Page Java 24.11 (執筆時点での最新)  
**作者:** Aspose  

{{< /blocks/products/pf/tutorial-page-section >}}

{{< /blocks/products/pf/main-container >}}
{{< /blocks/products/pf/main-wrap-class >}}

{{< blocks/products/products-backtop-button >}}