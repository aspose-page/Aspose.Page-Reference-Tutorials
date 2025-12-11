---
date: 2025-12-11
description: Aspose.Page を使用して Java で PostScript の楕円を作成する方法を学びます。このステップバイステップガイドでは、楕円を色で塗りつぶす方法と、Java
  を使用して楕円を描く方法を示します。
linktitle: Add Ellipse in Java PostScript
second_title: Aspose.Page Java API
title: Aspose.Page を使用して Java で PostScript の楕円を作成する方法
url: /ja/java/postscript-shapes/add-ellipse/
weight: 10
---

{{< blocks/products/pf/main-wrap-class >}}
{{< blocks/products/pf/main-container >}}
{{< blocks/products/pf/tutorial-page-section >}}

# Java と Aspose.Page で PostScript 楕円を作成する方法

## Introduction
プログラムで **PostScript 楕円** を作成すると、レポート、請求書、または任意の印刷可能ドキュメントにおけるベクターグラフィックスを細かく制御できます。このチュートリアルでは、Aspose.Page for Java ライブラリを使用して **PostScript 楕円** シェイプを作成し、楕円を色で塗りつぶし、楕円の輪郭を描く方法を学びます。最後まで読めば、カスタムグラフィックを直接 PostScript 出力に埋め込む準備が整います。

## Quick Answers
- **Java で PostScript グラフィックスを描画するのに最適なライブラリは何ですか？** Aspose.Page for Java。  
- **楕円を単色で塗りつぶすことはできますか？** はい – `fill` の前に `document.setPaint(Color.YOUR_COLOR)` を使用します。  
- **楕円の輪郭だけを描くにはどうすればよいですか？** ペイントとストロークを設定し、`document.draw(...)` を呼び出します。  
- **本番環境で使用するにはライセンスが必要ですか？** 商用ライセンスが必要です；テスト用の一時ライセンスも利用可能です。  
- **サポートされている Java バージョンは何ですか？** 現行の Aspose.Page リリースは Java 8 以上のランタイムで動作します。

## What is a PostScript ellipse?
PostScript 楕円は、バウンディング矩形で定義されるベクタ形状です。ラスタ画像とは異なり、品質を損なうことなく拡大縮小できるため、高解像度印刷や PDF 変換に最適です。

## Why use Aspose.Page to create a PostScript ellipse?
- **描画プリミティブ（線、曲線、楕円）に対する完全な制御**。  
- **クロスプラットフォーム** – Windows、Linux、macOS で動作。  
- **外部依存なし** – 純粋な Java API、ネイティブコード不要。  
- **既存の Java アプリケーションやビルドツールとの統合が容易**。

## Prerequisites
開始する前に、以下を確認してください。

1. 機能する Java 開発環境（JDK 8 以上）。  
2. プロジェクトに Aspose.Page for Java ライブラリを追加します。**[here](https://releases.aspose.com/page/java/)** からダウンロードできます。  

## Import Packages
Java ソースファイルで、PostScript コンテンツの描画と保存に必要なクラスをインポートします。

```java
import java.awt.BasicStroke;
import java.awt.Color;
import java.awt.geom.Ellipse2D;
import java.io.FileOutputStream;
import com.aspose.eps.PsDocument;
import com.aspose.eps.device.PsSaveOptions;
```

## Step‑by‑step guide

### Step 1: Set up the PostScript document
出力ストリームを作成し、ページサイズを設定し、`PsDocument` をインスタンス化します。

```java
// The path to the documents directory.
String dataDir = "Your Document Directory";
// Create output stream for PostScript document
FileOutputStream outPsStream = new FileOutputStream(dataDir + "AddEllipse_outPS.ps");
// Create save options with A4 size
PsSaveOptions options = new PsSaveOptions();
// Create new PS Document with the page opened
PsDocument document = new PsDocument(outPsStream, options, false);
```

### Step 2: Fill ellipse with color
希望する塗りつぶし色にペイントを設定し、`Ellipse2D` インスタンスで `fill` を呼び出します。

```java
// Set paint for filling ellipse
document.setPaint(Color.ORANGE);
// Fill the first ellipse
document.fill(new Ellipse2D.Float(250, 100, 150, 100));
```

### Step 3: Outline ellipse with stroke
ペイントをストローク色に切り替え、線の太さを表す `BasicStroke` を定義し、楕円の輪郭を描画します。

```java
// Set paint for stroking ellipse
document.setPaint(Color.RED);
// Set stroke
document.setStroke(new BasicStroke(3));
// Stroke (outline) the second ellipse
document.draw(new Ellipse2D.Float(250, 300, 150, 100));
```

### Step 4: Close and save the document
ページを確定し、PostScript ファイルをディスクに書き込みます。

```java
// Close current page
document.closePage();
// Save the document
document.save();
```

これで、オレンジで塗りつぶされた楕円と赤で輪郭が描かれた楕円の 2 つを含む PostScript ファイルが作成されました。座標、サイズ、色を自由に変更して、デザイン要件に合わせて実験してください。

## Common pitfalls and troubleshooting
- **ファイルパスが正しくない** – `dataDir` が OS に適した区切り文字（`/` または `\\`）で終わっていることを確認してください。  
- **ライセンスがない** – 有効なライセンスがない場合、ライブラリは評価モードで動作し、透かしが追加されることがあります。  
- **色が適用されない** – 各 `fill` または `draw` 呼び出しの *前に* `document.setPaint(...)` を設定することを忘れないでください。ペイント設定は別々の操作間で自動的に保持されません。  

## Frequently Asked Questions

**Q: Aspose.Page for Java を他の Java ライブラリと併用できますか？**  
A: はい、Aspose.Page for Java は他の Java ライブラリとシームレスに統合できるよう設計されています。

**Q: Aspose.Page for Java の一時ライセンスはどこで取得できますか？**  
A: テスト目的で使用できる一時ライセンスは **[here](https://purchase.aspose.com/temporary-license/)** から取得してください。

**Q: Aspose.Page は商用プロジェクトに適していますか？**  
A: もちろんです！商用利用向けのライセンスオプションは **[here](https://purchase.aspose.com/buy)** でご確認ください。

**Q: Aspose.Page に関する質問や議論はどこでできますか？**  
A: 議論やサポートは **[Aspose.Page Forum](https://forum.aspose.com/c/page/39)** で行えます。

**Q: Aspose.Page for Java を学ぶための無料リソースはありますか？**  
A: **[free trial](https://releases.aspose.com/)** を利用し、ドキュメント内のサンプルを確認してください。

## Conclusion
Aspose.Page for Java は、シンプルな塗りつぶし形状から複雑なストローク輪郭まで、**PostScript 楕円** グラフィックスを簡単に作成できるようにします。上記の手順を使えば、任意の印刷可能ドキュメントにプロフェッショナル品質のベクターグラフィックスをすぐに追加できます。複数形状の組み合わせ、グラデーションの適用、PDF への変換など、さらに深く探求したい場合は公式 **[documentation](https://reference.aspose.com/page/java/)** を参照してください。

{{< /blocks/products/pf/tutorial-page-section >}}

{{< /blocks/products/pf/main-container >}}
{{< /blocks/products/pf/main-wrap-class >}}

{{< blocks/products/products-backtop-button >}}

---

**最終更新日:** 2025-12-11  
**テスト環境:** Aspose.Page for Java 24.11  
**作者:** Aspose