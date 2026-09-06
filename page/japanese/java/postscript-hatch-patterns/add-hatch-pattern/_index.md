---
date: 2026-08-18
description: Aspose.Page Java を使用して Java PostScript ファイルにハッチパターンを追加する方法を学びます。このステップバイステップガイドでは、完全なコードとヒントを示します。
keywords:
- how to add hatch pattern
- Aspose.Page Java
- PostScript hatch patterns
- Java graphics API
lastmod: 2026-08-18
linktitle: Java PostScript にハッチパターンを追加
og_description: Aspose.Page を使用して Java PostScript でハッチパターンを追加する方法を学びます。このステップバイステップチュートリアルに従って、ハッチで塗りつぶされたグラフィックをすばやく作成できます。
og_image_alt: Screenshot of Java code adding hatch pattern to a PostScript file with
  Aspose.Page
og_title: Java PostScript でハッチパターンを追加する方法 – Aspose.Page ガイド
schemas:
- author: Aspose
  dateModified: '2026-08-18'
  description: Learn how to add hatch pattern to Java PostScript files using Aspose.Page
    Java. This step‑by‑step guide shows the complete code and tips.
  headline: How to add hatch pattern in Java PostScript
  type: TechArticle
- questions:
  - answer: Yes, the library is framework‑agnostic and works with Spring, Jakarta
      EE, Android (limited), and plain Java SE.
    question: Can I use Aspose.Page Java with other Java frameworks?
  - answer: Absolutely. Download a free 30‑day trial [Aspose trial download page](https://releases.aspose.com/).
    question: Is a trial version available for Aspose.Page Java?
  - answer: Request a temporary license [temporary license request page](https://purchase.aspose.com/temporary-license/).
      It removes evaluation watermarks.
    question: How do I obtain a temporary license for development?
  - answer: Visit the official forum [Aspose.Page for Java forum](https://forum.aspose.com/c/page/39)
      for additional examples and Q&A.
    question: Where can I find more tutorials and community support?
  - answer: Yes, the full API reference is available [Aspose.Page Java API reference](https://reference.aspose.com/page/java/).
    question: Is there comprehensive documentation for all classes and methods?
  type: FAQPage
second_title: Aspose.Page Java API
tags:
- Java
- Aspose.Page
- PostScript
- hatch pattern
title: Java PostScript でハッチパターンを追加する方法
url: /ja/java/postscript-hatch-patterns/add-hatch-pattern/
weight: 10
---

{{< blocks/products/pf/main-wrap-class >}}
{{< blocks/products/pf/main-container >}}
{{< blocks/products/pf/tutorial-page-section >}}

# Java PostScript でハッチパターンを追加する方法

## はじめに
**Aspose.Page Java** を使用していて、PostScript 出力に **ハッチパターンを追加する方法** を知りたい場合、ハッチパターンは高速かつ柔軟なソリューションです。このチュートリアルでは、PostScript ドキュメントに **ハッチを追加する** 方法を順を追って説明し、その有用性を解説し、完全な実行可能コード例を提供します。最後まで読めば、数行の Java コードだけで視覚的に魅力的なハッチ塗りの形状やテキストを作成できるようになります。

## クイック回答
- **どのライブラリが必要ですか？** Aspose.Page for Java (the “aspose page java” SDK)。  
- **どの視覚効果を追加しますか？** ハッチパターン（例：対角線、クロスハッチ）。  
- **サンプルを実行するのにライセンスが必要ですか？** 開発には無料トライアルで動作しますが、本番環境ではライセンスが必要です。  
- **コード行数はどれくらいですか？** 約 70 行で、明確なステップに分割されています。  
- **PDF にも同じアプローチを使用できますか？** はい—Aspose.Page は PDF を含む複数の出力フォーマットをサポートしています。

## ハッチパターンとは何ですか？
ハッチパターンは、繰り返しの線や形状で構成されたベクターベースの塗りで、テクスチャ効果を生み出します。数式で定義されているため、品質の低下なくスケーリングでき、高解像度印刷やモノクロ出力に最適です。

## Aspose.Page Java でハッチパターンを使用する理由は？
Aspose.Page は **10 以上の出力フォーマット**（PostScript、PDF、EPS、SVG、XPS など）をサポートし、**500 ページ**までのドキュメントにハッチ塗りをメモリに全体を読み込まずにレンダリングできます。これにより、高速なパフォーマンス、低メモリフットプリント、すべてのサポートフォーマットで一貫したビジュアル結果が得られます。

## ハッチパターンの追加方法 – 概要
ハッチパターンはベクターベースのテクスチャで、あらゆる解像度で鮮明にレンダリングされ、モノクロプリンターでもうまく機能します。Aspose.Page Java を使用すれば、低レベルの PostScript コマンドを扱うことなく、これらのパターンを形状、パス、さらにはテキストに適用できます。

## 前提条件
- **Java 開発環境** – JDK 8 以上とお好みの IDE。  
- **Aspose.Page for Java ライブラリ** – 公式 **Aspose.Page for Java ダウンロードページ** から最新の JAR をダウンロードしてください [こちら](https://releases.aspose.com/page/java/)。  
- 他の Aspose リリースも [こちら](https://releases.aspose.com/) で閲覧できます。  
- **書き込み権限** – 生成された PostScript ファイルを保存するフォルダーへの書き込み権限。

## パッケージのインポート
以下のインポートは、色、ストローク、幾何形状などのグラフィックプリミティブ用の標準 Java AWT クラスと、PostScript ファイル生成に必要なドキュメントモデル、ハッチスタイル定義、保存オプションを提供する Aspose.Page クラスを含んでいます。
```java
import java.awt.BasicStroke;
import java.awt.Color;
import java.awt.Font;
import java.awt.TexturePaint;
import java.awt.geom.Rectangle2D;
import java.io.FileOutputStream;
import com.aspose.eps.HatchPaintLibrary;
import com.aspose.eps.HatchStyle;
import com.aspose.eps.PsDocument;
import com.aspose.eps.device.PsSaveOptions;
```

## `Document` クラスとは何ですか？
`Document` クラスは、メモリ内の単一の PostScript ファイルを表す Aspose.Page の最上位オブジェクトです。すべての描画操作はこのオブジェクトを通じて実行されます。

## 出力ストリームの設定方法は？
出力を書き込むには、目的のファイルパスを指す `FileOutputStream` を作成します。このストリームは低レベルのバイト書き込みを処理します。`PsSaveOptions` はページサイズや圧縮など、ドキュメントの保存方法を設定します。その後、ページサイズ、圧縮、その他の PostScript 固有設定を指定した `PsSaveOptions` オブジェクトで `Document` をインスタンス化します。
```java
// The path to the documents directory.
String dataDir = "Your Document Directory";
// Create output stream for PostScript document
FileOutputStream outPsStream = new FileOutputStream(dataDir + "AddHatchPattern_outPS.ps");
// Create save options with A4 size
PsSaveOptions options = new PsSaveOptions();
// Create new PS Document with the page opened
PsDocument document = new PsDocument(outPsStream, options, false);
int x0 = 20;
int y0 = 100;
int squareSide = 32;
int width = 500;
int sumX = 0;
```

## グラフィックス状態の保存と原点の平行移動方法は？
グラフィックス状態を保存すると、現在の変換行列、クリッピング領域、描画属性が記録され、後で元に戻すことができます。保存後、グラフィックスオブジェクトで `translate(x, y)` を呼び出し、ハッチ正方形のグリッドを描画するための便利な位置に原点をシフトします。
```java
document.writeGraphicsSave();
document.translate(x0, y0);
```

## 各パターン用に再利用可能な正方形を作成する方法は？
`Rectangle2D` は位置とサイズで定義された矩形形状を表します。セルの寸法に合わせた単一のインスタンスを作成することで、各ハッチ塗りの正方形に再利用でき、オブジェクト割り当てを減らし描画ループの効率を保ちます。
```java
Rectangle2D.Float square = new Rectangle2D.Float(0, 0, squareSide, squareSide);
```

## パターン正方形のアウトライン用ペンの設定方法は？
`BasicStroke` はベクトル形状のアウトラインの太さ、破線パターン、端点の形状を定義します。2 ポイントの `BasicStroke` を使用すると、各ハッチ塗りセルの周囲に明確な境界ができ、隣接する正方形と視覚的に分離されます。
```java
BasicStroke stroke = new BasicStroke(2);
```

## ハッチパターンを反復処理する方法は？
`HatchStyle` は、対角線、クロス、点線などの事前定義されたハッチパターンを列挙した列挙型です。`HatchStyle.values()` をループすることで、各パターンを順に適用し、`HatchBrush` で矩形を塗り、そしてアウトラインを描画できます。
```java
HatchStyle[] hatchStyles = HatchStyle.values();
for (int i = 0; i < hatchStyles.length; i++) {
    // ... (continue with the provided code)
}
```

## 描画後にグラフィックス状態を復元する方法は？
グラフィックスオブジェクトで `restore()` を呼び出すと、変換行列と描画設定が以前に保存された状態に戻り、累積的な平行移動やスケーリングが以降の描画操作に影響しないようにします。これにより、後続のコンテンツは元の座標系から開始し、デフォルト属性が使用されます。
```java
document.writeGraphicsRestore();
```

## テキストをハッチパターンで塗りつぶす方法は？
`TextFragment` は、個別に位置指定やスタイル設定ができるテキストの断片を表します。フラグメントの塗りに選択した `HatchStyle` を持つ `HatchBrush` を割り当てることで、文字は単色ではなくハッチテクスチャで描画されます。
```java
TexturePaint paint = HatchPaintLibrary.getHatchTexturePaint(HatchStyle.DiagonalCross, Color.RED, Color.YELLOW);
Font font = new Font("Arial", Font.BOLD, 96);
document.fillAndStrokeText("ABC", font, 200, 320, paint, Color.BLACK, stroke);
```

## 異なるハッチスタイルでテキストにアウトラインを付ける方法は？
`HatchBrush` はストロークにも使用できます。アウトラインを描くには、フラグメントのストロークを別の `HatchStyle`（例：70 % ハッチ）を持つ `HatchBrush` に設定し、`setStrokeWidth` でストローク幅を増やします。これにより、テキストの境界が独自のハッチパターンで描画され、内部の塗りは保持されます。
```java
paint = HatchPaintLibrary.getHatchTexturePaint(HatchStyle.Percent70, Color.BLUE, Color.WHITE);
document.outlineText("ABC", font, 200, 420, paint, new BasicStroke(5));
```

## ドキュメントを閉じて保存する方法は？
`document.save()` は、メモリ内のドキュメントを指定された出力ストリームに書き込みます。すべての描画コマンドが完了したらこのメソッドを呼び出し、続いて `FileOutputStream` を閉じてシステムリソースを解放し、ファイルがディスクに正しくフラッシュされるようにします。
```java
document.closePage();
document.save();
```

これらの手順に従えば、形状とテキストの両方にハッチパターンのフルセットが適用された PostScript ファイルが作成できます—すべて **aspose page java** によって実現されています。

## よくある落とし穴とヒント
- **ファイルパスエラー** – `dataDir` が適切なファイル区切り文字（`/` または `\`）で終わっていることを確認してください。  
- **サポートされていない色** – 古い PostScript インタプリタでは特定のカラースペースが扱えない場合があります。最大の互換性のために基本的な RGB を使用してください。  
- **ライセンス警告** – 有効なライセンスなしでサンプルを実行すると、出力に透かしが埋め込まれます。

## よくある質問

**Q: Aspose.Page Java を他の Java フレームワークと併用できますか？**  
A: はい、このライブラリはフレームワークに依存せず、Spring、Jakarta EE、Android（制限あり）、および純粋な Java SE で動作します。

**Q: Aspose.Page Java のトライアル版は利用可能ですか？**  
A: もちろんです。無料の 30 日間トライアルをダウンロードしてください [Aspose トライアルダウンロードページ](https://releases.aspose.com/)。

**Q: 開発用の一時ライセンスはどう取得できますか？**  
A: 一時ライセンスをリクエストしてください [一時ライセンスリクエストページ](https://purchase.aspose.com/temporary-license/)。評価用の透かしが除去されます。

**Q: さらにチュートリアルやコミュニティサポートはどこで見つけられますか？**  
A: 公式フォーラム [Aspose.Page for Java フォーラム](https://forum.aspose.com/c/page/39) を訪れて、追加の例や Q&A をご覧ください。

**Q: すべてのクラスとメソッドの包括的なドキュメントはありますか？**  
A: はい、完全な API リファレンスは [Aspose.Page Java API リファレンス](https://reference.aspose.com/page/java/) で利用可能です。

**Q: 同じハッチパターンを PostScript ではなく PDF にレンダリングできますか？**  
A: もちろんです。`PsSaveOptions` を `PdfSaveOptions`（または同等のもの）に変更すれば、残りのコードはそのままです。

**Q: 生成されたファイルが空の場合はどうすればよいですか？**  
A: 出力ストリームが書き込み可能なディレクトリを指しているか、すべての描画操作の後に `document.save()` が呼び出されているかを確認してください。

**最終更新日:** 2026-08-18  
**テスト環境:** Aspose.Page for Java 24.12 (執筆時点での最新)  
**作者:** Aspose

## 関連チュートリアル

- [PostScript でテクスチャパターンを作成 – Aspose.Page Java](/page/java/postscript-texture-patterns/)
- [Java PostScript でグラデーションを追加: 対角グラデーション – Aspose.Page Java](/page/java/postscript-gradient-addition/diagonal/)
- [Aspose.Page Java API を使用して PostScript を PDF に変換する方法](/page/java/postscript-conversion/to-pdf/)


{{< /blocks/products/pf/tutorial-page-section >}}

{{< /blocks/products/pf/main-container >}}
{{< /blocks/products/pf/main-wrap-class >}}

{{< blocks/products/products-backtop-button >}}