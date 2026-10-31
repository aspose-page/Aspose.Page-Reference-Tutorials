---
date: 2026-10-31
description: Aspose.Pageを使用してJava PostScriptでpaint colorを設定し、ellipseを塗りつぶす方法を学びます。このガイドでは、ellipseの塗りつぶし、輪郭の描画、stroke
  thicknessの設定を明確なコード手順で示します。
keywords:
- how to fill ellipse
- how to set paint color
- Aspose.Page Java ellipse
- PostScript drawing Java
lastmod: 2026-10-31
linktitle: Java PostScriptにellipseを追加
og_description: Aspose.Pageを使用してJava PostScriptでellipseを塗りつぶし、paint colorを設定する方法を学びます。数秒で塗りつぶしと輪郭付きellipseを描くステップバイステップのコードをご覧ください。
og_image_alt: Developer guide showing how to fill ellipse and set paint color in Java
  PostScript with Aspose.Page
og_title: Java PostScriptでellipseを塗りつぶし、paint colorを設定する方法
schemas:
- author: Aspose
  dateModified: '2026-10-31'
  description: Learn how to set paint color and fill ellipse in Java PostScript using
    Aspose.Page. This guide shows how to fill ellipse, draw ellipse outline, and set
    stroke thickness with clear code steps.
  headline: How to fill ellipse and set paint color in Java PostScript
  type: TechArticle
- description: Learn how to set paint color and fill ellipse in Java PostScript using
    Aspose.Page. This guide shows how to fill ellipse, draw ellipse outline, and set
    stroke thickness with clear code steps.
  name: How to fill ellipse and set paint color in Java PostScript
  steps:
  - name: Set up the PostScript document
    text: Create an output stream, configure page size, and instantiate a `PsDocument`.
      `PsDocument` is the core class that represents a PostScript file in memory.
      All drawing commands are routed through this object, and it handles page layout,
      resource management, and final file generation.
  - name: Fill ellipse – use set paint color
    text: To **fill ellipse**, you must first call `setPaint` with the desired fill
      color, then invoke `fill` with an `Ellipse2D` instance. `setPaint` sets the
      current drawing color used for subsequent fill or stroke operations. `Ellipse2D`
      defines the geometric bounds of the ellipse; its constructor takes th
  - name: Draw ellipse outline and set stroke thickness
    text: After filling, you can change the paint to a different color, define a `BasicStroke`
      to control line width, and draw the ellipse outline. `BasicStroke` specifies
      line width, dash pattern, and end‑cap style for drawing outlines. By adjusting
      its `width` property you control how bold the ellipse borde
  - name: Close and save the document
    text: Finalize the page and write the PostScript file to disk. Calling `document.close()`
      flushes all pending drawing commands and releases resources. The resulting `.ps`
      file can be opened with any PostScript viewer or converted to PDF. You now have
      a PostScript file that contains two ellipses—one filled
  type: HowTo
- questions:
  - answer: Yes, Aspose.Page for Java is designed to seamlessly integrate with other
      Java libraries.
    question: Can I use Aspose.Page for Java with other Java libraries?
  - answer: Obtain a temporary license **[from the Aspose temporary‑license page](https://purchase.aspose.com/temporary-license/)**
      for testing purposes.
    question: How can I get a temporary license for Aspose.Page for Java?
  - answer: Absolutely! Visit **[the Aspose purchase page](https://purchase.aspose.com/buy)**
      to explore licensing options for commercial use.
    question: Is Aspose.Page suitable for commercial projects?
  - answer: Join the community at the **[Aspose.Page Forum](https://forum.aspose.com/c/page/39)**
      for discussions and assistance.
    question: Where can I seek help or discuss Aspose.Page‑related queries?
  - answer: Utilize the **[Aspose free trial page](https://releases.aspose.com/)**
      and explore examples in the documentation.
    question: Are there any free resources to learn more about Aspose.Page for Java?
  type: FAQPage
second_title: Aspose.Page Java API
tags:
- Aspose.Page
- Java graphics
- PostScript ellipse
- vector drawing
title: Java PostScriptでellipseを塗りつぶし、paint colorを設定する方法
url: /ja/java/postscript-shapes/add-ellipse/
weight: 10
---

{{< blocks/products/pf/main-wrap-class >}}
{{< blocks/products/pf/main-container >}}
{{< blocks/products/pf/tutorial-page-section >}}

# Java PostScriptで楕円を塗りつぶし、ペイントカラーを設定する方法

## はじめに
ベクターグラフィックを描画する際に**ペイントカラーを設定**する必要がある場合、Aspose.Page for Java ライブラリはストロークや塗りつぶしを完全にコントロールできます。このチュートリアルでは、**ペイントカラーの設定**、**楕円の塗りつぶし**、**楕円の輪郭描画**をシンプルなステップバイステップで学びます。最後まで実施すれば、請求書やレポート、その他印刷可能な文書に高品質な PostScript 楕円を追加できるようになります。

## クイック回答
- **JavaでPostScriptグラフィックを描画するのに最適なライブラリは何ですか？** Aspose.Page for Java。  
- **楕円を単色で塗りつぶすことはできますか？** はい – `fill` の前に `document.setPaint(Color.YOUR_COLOR)` を使用します。  
- **楕円の輪郭だけを描くには？** ペイントとストロークを設定し、`document.draw(...)` を呼び出します。  
- **本番環境で使用するにはライセンスが必要ですか？** 商用ライセンスが必要です。テスト用の一時ライセンスも利用可能です。  
- **対応しているJavaバージョンは？** 現行の Aspose.Page リリースは Java 8 以降のランタイムで動作します。

## PostScript楕円とは？
PostScript 楕円は、外接矩形で定義されたベクタ形状です。ラスタ画像とは異なり、品質を損なうことなく拡大縮小できるため、高解像度印刷や PDF 変換に最適です。形状は数式で記述されているため、任意のサイズや解像度で描画しても、エッジは鮮明で曲線は滑らかに保たれます。

## なぜAspose.Pageを使ってPostScript楕円を作成するのか？
Aspose.Page は、すべての描画プリミティブを決定的に制御できます。**Windows、Linux、macOS の 3 つの主要 OS** をサポートし、**ネイティブ依存性は 0**、典型的なサーバー上で **1 秒あたり 50 以上のベクタプリミティブ** をレンダリングできます。このライブラリは純粋な Java で構成されているため、追加のネイティブライブラリなしで Java 8 以降の任意のアプリケーションに組み込めます。

## 前提条件
開始する前に、以下が揃っていることを確認してください：

1. 動作する Java 開発環境 (JDK 8 以上)。  
2. プロジェクトに Aspose.Page for Java ライブラリを追加します。**[Aspose.Page for Java のリリースページからダウンロード](https://releases.aspose.com/page/java/)** できます。  

## パッケージのインポート
Java のソースファイルで、PostScript コンテンツの描画と保存に必要なクラスをインポートします。

`java.awt` パッケージは `Color`、`Ellipse2D`、`BasicStroke` などの基本的なグラフィック型を提供します。`com.aspose.page` パッケージは PostScript 出力を書き込む `PsDocument` クラスを提供します。

- **`Color`** – 描画に使用される sRGB カラーを表します。  
- **`Ellipse2D`** – 外接矩形で定義された楕円形状を記述します。  
- **`BasicStroke`** – 輪郭描画の線幅、破線パターン、端点スタイルを指定します。  
- **`PsDocument`** – PostScript ドキュメントを表し、グラフィック描画やページ管理のメソッドを提供します。

```java
import java.awt.BasicStroke;
import java.awt.Color;
import java.awt.geom.Ellipse2D;
import java.io.FileOutputStream;
import com.aspose.eps.PsDocument;
import com.aspose.eps.device.PsSaveOptions;
```

## 楕円のペイントカラーを設定する方法
最初のステップは、次の描画操作で使用する色をドキュメントに指示することです。`setPaint` メソッドは、後続の呼び出しに応じて塗りつぶしまたはストロークに適用される単色を設定します。

### 手順 1: PostScriptドキュメントの設定
出力ストリームを作成し、ページサイズを設定し、`PsDocument` のインスタンスを生成します。

`PsDocument` はメモリ上の PostScript ファイルを表すコアクラスです。すべての描画コマンドはこのオブジェクトを通じて実行され、ページレイアウト、リソース管理、最終的なファイル生成を処理します。

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

### 手順 2: 楕円を塗りつぶす – ペイントカラーを設定
**楕円を塗りつぶす**には、まず目的の塗りつぶし色で `setPaint` を呼び出し、次に `Ellipse2D` インスタンスを使って `fill` を実行する必要があります。

`setPaint` は、以降の塗りつぶしまたはストローク操作で使用される現在の描画色を設定します。  
`Ellipse2D` は楕円の幾何学的境界を定義します。コンストラクタは左上隅の X‑Y 座標と幅・高さを受け取ります。

```java
// Set paint for filling ellipse
document.setPaint(Color.ORANGE);
// Fill the first ellipse
document.fill(new Ellipse2D.Float(250, 100, 150, 100));
```

### 手順 3: 楕円の輪郭を描画し、ストロークの太さを設定
塗りつぶし後、ペイントを別の色に変更し、`BasicStroke` を定義して線幅を制御し、楕円の輪郭を描画できます。

`BasicStroke` は輪郭描画の線幅、破線パターン、端点スタイルを指定します。`width` プロパティを調整することで、楕円の枠線の太さを制御できます。

```java
// Set paint for stroking ellipse
document.setPaint(Color.RED);
// Set stroke
document.setStroke(new BasicStroke(3));
// Stroke (outline) the second ellipse
document.draw(new Ellipse2D.Float(250, 300, 150, 100));
```

### 手順 4: ドキュメントを閉じて保存
ページを確定し、PostScript ファイルをディスクに書き出します。

`document.close()` を呼び出すと、保留中のすべての描画コマンドがフラッシュされ、リソースが解放されます。生成された `.ps` ファイルは任意の PostScript ビューアで開くか、PDF に変換できます。

```java
// Close current page
document.closePage();
// Save the document
document.save();
```

これで、オレンジで塗りつぶされた楕円と赤で輪郭が描かれた楕円の 2 つを含む PostScript ファイルが作成されました。座標、サイズ、色を自由に変更して、デザイン要件に合わせて試してみてください。

## よくある落とし穴とトラブルシューティング
- **ファイルパスが不正** – `dataDir` が OS に適した区切り文字 (`/` または `\\`) で終わっていることを確認してください。  
- **ライセンスが欠如** – 有効なライセンスがない場合、ライブラリは評価モードで動作し、透かしが付く可能性があります。  
- **色が適用されない** – 各 `fill` または `draw` 呼び出しの *前に* `document.setPaint(...)` を設定することを忘れないでください。ペイント設定は別々の操作間で自動的に保持されません。

## よくある質問

**Q: Aspose.Page for Java を他の Java ライブラリと併用できますか？**  
A: はい、Aspose.Page for Java は他の Java ライブラリとシームレスに統合できるよう設計されています。

**Q: Aspose.Page for Java の一時ライセンスはどう取得できますか？**  
A: テスト目的で **[Aspose の一時ライセンスページから取得](https://purchase.aspose.com/temporary-license/)** できます。

**Q: Aspose.Page は商用プロジェクトに適していますか？**  
A: もちろんです！商用利用向けのライセンスオプションは **[Aspose の購入ページ](https://purchase.aspose.com/buy)** でご確認ください。

**Q: Aspose.Page に関する質問やサポートはどこで受けられますか？**  
A: **[Aspose.Page フォーラム](https://forum.aspose.com/c/page/39)** に参加して議論や支援を受けられます。

**Q: Aspose.Page for Java を学ぶための無料リソースはありますか？**  
A: **[Aspose の無料トライアルページ](https://releases.aspose.com/)** を利用し、ドキュメント内のサンプルを確認してください。

## 結論
Aspose.Page for Java を使用すれば、**ペイントカラーの設定**、**楕円の塗りつぶし**、**楕円の輪郭描画**が簡単に行えます。シンプルな塗りつぶし形状でも複雑なストロークグラフィックでも、上記の手順で印刷可能な文書にプロフェッショナル品質のベクタ画像をすぐに追加できます。複数形状の組み合わせやグラデーションの適用、PDF への変換など、さらに深く学びたい場合は公式の **[Aspose.Page Java ドキュメント](https://reference.aspose.com/page/java/)** を参照してください。

---

**Last Updated:** 2026-10-31  
**Tested With:** Aspose.Page for Java 24.11  
**Author:** Aspose

## 関連チュートリアル

- [Java PostScriptで矩形を描く方法 (Aspose.Page)](/page/java/postscript-shapes/add-rectangle/)
- [Java PostScriptでUnicodeテキストを追加する方法 (Aspose.Page)](/page/java/postscript-text-manipulation/add-text-unicode/)
- [Java用Aspose.PageでPostScriptの放射状グラデーションを作成する方法](/page/java/postscript-gradient-addition/)


{{< /blocks/products/pf/tutorial-page-section >}}

{{< /blocks/products/pf/main-container >}}
{{< /blocks/products/pf/main-wrap-class >}}

{{< blocks/products/products-backtop-button >}}