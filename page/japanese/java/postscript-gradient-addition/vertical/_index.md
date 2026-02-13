---
date: 2026-02-13
description: Aspose.Page を使用して Java で PostScript グラデーションを作成する方法を学びましょう。このステップバイステップガイドでは、PostScript
  ドキュメントに垂直グラデーションを簡単に追加する方法を示します。
linktitle: Add Vertical Gradient in Java PostScript
second_title: Aspose.Page Java API
title: JavaでPostScriptのグラデーションを作成 – 垂直グラデーションを追加
url: /ja/java/postscript-gradient-addition/vertical/
weight: 14
---

 "Create PostScript Gradient in Java – Add Vertical Gradient" to Japanese.

Let's translate each section.

We'll keep the shortcodes.

Let's craft Japanese translation.

Make sure not to translate URLs.

Also keep the markdown links.

Let's produce final output.{{< blocks/products/pf/main-wrap-class >}}
{{< blocks/products/pf/main-container >}}
{{< blocks/products/pf/tutorial-page-section >}}

# Java で PostScript グラデーションを作成 – 縦方向グラデーションの追加

## はじめに
この包括的なチュートリアルでは、**Java で PostScript グラデーションを作成**する方法を Aspose.Page for Java を使って学びます。縦方向のグラデーションを追加することで、ドキュメントがより鮮やかでプロフェッショナルに見えるようになり、数行のコードで驚くべきビジュアル効果を実現できます。各ステップを順に解説し、なぜその処理が重要なのかを説明し、一般的な落とし穴を回避する実用的なヒントも提供します。このガイドを終える頃には、滑らかで目を引く縦方向の色変化を持つ PostScript ファイルを生成できるようになります。

## クイック回答
- **必要なライブラリは？** Aspose.Page for Java  
- **色はカスタマイズできますか？** はい、任意の `java.awt.Color` が使用可能です  
- **回転はサポートされていますか？** はい、`AffineTransform` でグラデーションを回転できます  
- **生成される出力形式は？** 標準的な PostScript (.ps) ファイル  
- **本番環境でライセンスは必要ですか？** はい、商用ライセンスが必要です  

## なぜ PostScript ドキュメントに縦方向グラデーションを追加するのか？
縦方向グラデーションは、ファイルサイズを増やさずにページに奥行きを与えます。次のようなシーンに最適です：

* 微妙な背景カラーが必要なレポートのヘッダーやフッター  
* 技術マニュアルやホワイトペーパーのセクションを強調表示  
* チャート、図、プロモーションフライヤーにモダンな外観を提供  

グラデーションはベクタ形式で定義されるため、どの解像度でも鮮明さが保たれます。

## 前提条件
チュートリアルに入る前に、以下の前提条件が整っていることを確認してください：
- マシンに Java Development Kit (JDK) がインストールされていること。  
- Aspose.Page for Java ライブラリ。ダウンロードは [here](https://releases.aspose.com/page/java/) から。

## パッケージのインポート
Java プロジェクトで必要なパッケージをインポートします：
```java
import java.awt.Color;
import java.awt.LinearGradientPaint;
import java.awt.MultipleGradientPaint;
import java.awt.geom.AffineTransform;
import java.awt.geom.Point2D;
import java.awt.geom.Rectangle2D;
import java.io.FileOutputStream;
import com.aspose.eps.PsDocument;
import com.aspose.eps.device.PsSaveOptions;
```

それでは、縦方向グラデーションを追加する手順をステップバイステップで見ていきましょう。

## Java で PostScript グラデーションを作成する方法
以下は、Aspose.Page API を使用して **Java で PostScript グラデーションを作成**する手順を示したガイドです。

### 手順 1: ドキュメントディレクトリを設定
```java
// The path to the documents directory.
String dataDir = "Your Document Directory";
```

### 手順 2: PostScript ドキュメント用の出力ストリームを作成
```java
// Create output stream for PostScript document
FileOutputStream outPsStream = new FileOutputStream(dataDir + "VerticalGradient_outPS.ps");
```

### 手順 3: A4 サイズの保存オプションを作成
```java
// Create save options with A4 size
PsSaveOptions options = new PsSaveOptions();
```

### 手順 4: 新しい PS ドキュメントを作成
```java
// Create new PS Document with the page opened
PsDocument document = new PsDocument(outPsStream, options, false);
```

### 手順 5: 長方形を作成
```java
// Create a rectangle
Rectangle2D.Float rectangle = new Rectangle2D.Float(200, 100, 200, 100);
```

### 手順 6: グラデーション用のカラーとフラクションを設定
```java
// Create arrays of colors and fractions for the gradient.
Color[] colors = { Color.RED, Color.GREEN, Color.BLUE, Color.ORANGE, new Color(85, 107, 47) };
float[] fractions = { 0.0f, 0.1873f, 0.492f, 0.734f, 1.0f };
```

### 手順 7: グラデーション変換を作成
```java
// Create the gradient transform. Scale components in the transform must be equal to width and height of the rectangle.
// Translation components are offsets of the rectangle.
AffineTransform transform = new AffineTransform(200, 0, 0, 100, 200, 100);
// Rotate the gradient on 90 degrees around an origin
transform.rotate(90 * (Math.PI / 180));
```

### 手順 8: 縦方向リニアグラデーションペイントを作成
```java
// Create vertical linear gradient paint.
LinearGradientPaint paint = new LinearGradientPaint(new Point2D.Float(0, 0), new Point2D.Float(200, 100),
        fractions, colors, MultipleGradientPaint.CycleMethod.NO_CYCLE, MultipleGradientPaint.ColorSpaceType.SRGB,
        transform);
```

### 手順 9: ペイントを設定し、長方形を塗りつぶす
```java
// Set paint
document.setPaint(paint);
// Fill the rectangle
document.fill(rectangle);
```

### 手順 10: 現在のページを閉じてドキュメントを保存
```java
// Close current page
document.closePage();
// Save the document
document.save();
```

おめでとうございます！Aspose.Page for Java を使用して、Java の PostScript ドキュメントに縦方向グラデーションを正常に追加できました。

## よくある問題と解決策
- **グラデーションが平坦に見える**：`AffineTransform` のスケーリングが長方形の寸法と一致しているか確認してください。  
- **色がくすんで見える**：正しい `ColorSpaceType`（SRGB）を使用し、フラクション配列が 0.0 から 1.0 の順序になっているか確認してください。  
- **ファイルが生成されない**：出力ディレクトリ（`dataDir`）が存在し、アプリケーションに書き込み権限があるか確認してください。  

## FAQ（よくある質問）
### Aspose.Page for Java を他の Java ライブラリと併用できますか？
はい、Aspose.Page for Java は他の Java ライブラリとシームレスに連携できるよう設計されています。

### Aspose.Page for Java の無料トライアルはありますか？
はい、無料トライアルは [here](https://releases.aspose.com/) から取得できます。

### 追加のドキュメントはどこで見つけられますか？
詳細なドキュメントは [here](https://reference.aspose.com/page/java/) にあります。

### Aspose.Page for Java の購入方法は？
購入は [here](https://purchase.aspose.com/buy) から行えます。

### Aspose.Page に関するフォーラムはありますか？
はい、コミュニティフォーラムは [here](https://forum.aspose.com/c/page/39) で参加できます。

## 追加の FAQ

**Q: 他のグラデーション方向（水平、対角線）も作成できますか？**  
A: もちろんです。`LinearGradientPaint` の開始点と終了点を調整し、`AffineTransform` の回転角度を変更すれば実現できます。

**Q: PDF 出力でも同じことはできますか？**  
A: 同じグラデーションロジックを使用し、`PsSaveOptions` の代わりに `PdfSaveOptions` を指定すれば PDF にも適用できます。

**Q: グラデーションのサイズを動的に変更するには？**  
A: 実行時に長方形の寸法を計算し、その値を `Rectangle2D` と `AffineTransform` のコンストラクタに渡してください。

---

**最終更新日:** 2026-02-13  
**テスト環境:** Aspose.Page for Java 24.11（最新）  
**作者:** Aspose  

{{< /blocks/products/pf/tutorial-page-section >}}

{{< /blocks/products/pf/main-container >}}
{{< /blocks/products/pf/main-wrap-class >}}

{{< blocks/products/products-backtop-button >}}