---
date: 2026-02-15
description: Aspose.Page Java を使用して、Java の PostScript ファイルにハッチパターンを追加する方法を学びましょう。このステップバイステップガイドでは、完全なコードとヒントを示します。
linktitle: Add Hatch Pattern in Java PostScript
second_title: Aspose.Page Java API
title: Aspose.Page を使用した Java PostScript でハッチパターンを追加する方法
url: /ja/java/postscript-hatch-patterns/add-hatch-pattern/
weight: 10
---

 markdown formatting exactly.

Let's craft translation.

{{< blocks/products/pf/main-wrap-class >}}
{{< blocks/products/pf/main-container >}}
{{< blocks/products/pf/tutorial-page-section >}}

# Java PostScriptでハッチパターンを追加する方法

## はじめに
**Aspose.Page Java** を使用していて、PostScript 出力に **ハッチパターンを追加する方法** を知りたい場合、ハッチパターンは高速かつ柔軟なソリューションです。このチュートリアルでは、PostScript ドキュメントに **ハッチ** デザインを追加する手順を解説し、なぜそれが有用かを説明し、実行可能な完全なコード例を提供します。最後まで読めば、数行の Java コードで視覚的に魅力的なハッチ塗りの図形やテキストを作成できるようになります。

## クイック回答
- **必要なライブラリは何ですか？** Aspose.Page for Java（「aspose page java」SDK）。  
- **追加するビジュアルエフェクトは何ですか？** ハッチパターン（例：対角線、クロスハッチ）。  
- **サンプルを実行するのにライセンスは必要ですか？** 開発には無料トライアルで動作しますが、本番環境ではライセンスが必要です。  
- **コード行数はどれくらいですか？** 約70行で、明確なステップに分かれています。  
- **PDFでも同じアプローチを使用できますか？** はい—Aspose.PageはPDFを含む複数の出力フォーマットをサポートしています。

## ハッチパターンの追加 – 概要
ハッチパターンはベクターベースのテクスチャで、任意の解像度で鮮明に描画でき、モノクロプリンターでもうまく機能します。Aspose.Page Java を使用すれば、低レベルの PostScript コマンドに触れることなく、図形、パス、テキストにこれらのパターンを適用できます。

## 前提条件
開始する前に、以下を用意してください。

- **Java 開発環境** – JDK 8 以上とお好みの IDE。  
- **Aspose.Page for Java ライブラリ** – 公式サイトから最新の JAR をダウンロードしてください [here](https://releases.aspose.com/page/java/)。  
- **書き込み権限** – 生成された PostScript ファイルを保存するフォルダーへの書き込み権限。

## パッケージのインポート
まず、必要なクラスをプロジェクトに取り込みます。これらのインポートにより、描画プリミティブ、カラー処理、Aspose.Page API へのアクセスが可能になります。

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

## ステップ 1: 初期パラメータの設定
出力ストリームを作成し、ページサイズ（A4）を設定し、各ハッチ塗り正方形を描画する際に再利用するレイアウト変数をいくつか定義します。

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

## ステップ 2: グラフィックス状態の保存と平行移動
グラフィックス状態を保存すると、後で元の座標系に戻すことができ、`translate` で原点を便利な開始位置に移動します。

```java
document.writeGraphicsSave();
document.translate(x0, y0);
```

## ステップ 3: 各パターン用の正方形を作成
各ハッチ塗りセルを表す再利用可能な矩形を定義します。

```java
Rectangle2D.Float square = new Rectangle2D.Float(0, 0, squareSide, squareSide);
```

## ステップ 4: パターン正方形のアウトライン用ペンの設定
2 ポイントの `BasicStroke` が、すべての正方形に鮮明なアウトラインを提供します。

```java
BasicStroke stroke = new BasicStroke(2);
```

## ステップ 5: ハッチパターンを反復処理
`HatchStyle` 列挙型のすべての値をループし、対応するテクスチャで各正方形を塗りつぶし、アウトラインを描画します。これが **ハッチパターンを追加する** 機能の核心です。

```java
HatchStyle[] hatchStyles = HatchStyle.values();
for (int i = 0; i < hatchStyles.length; i++) {
    // ... (continue with the provided code)
}
```

## ステップ 6: グラフィックス状態の復元
正方形グリッドの描画が完了したら、元の座標系に戻ります。

```java
document.writeGraphicsRestore();
```

## ステップ 7: ハッチパターンでテキストを塗りつぶす
ここでは、ハッチテクスチャを使用してテキストを描画する方法を示します。例では、単語 “ABC” を対角クロスパターンで塗りつぶします。

```java
TexturePaint paint = HatchPaintLibrary.getHatchTexturePaint(HatchStyle.DiagonalCross, Color.RED, Color.YELLOW);
Font font = new Font("Arial", Font.BOLD, 96);
document.fillAndStrokeText("ABC", font, 200, 320, paint, Color.BLACK, stroke);
```

## ステップ 8: ハッチパターンでテキストのアウトラインを描く
同じテキストをアウトライン化しますが、今回は 70 % のハッチスタイルと太めのストロークを使用します。

```java
paint = HatchPaintLibrary.getHatchTexturePaint(HatchStyle.Percent70, Color.BLUE, Color.WHITE);
document.outlineText("ABC", font, 200, 420, paint, new BasicStroke(5));
```

## ステップ 9: ドキュメントを閉じて保存
ページを確定し、ファイルをディスクに書き込み、リソースを解放します。

```java
document.closePage();
document.save();
```

これらの手順に従えば、形状とテキストの両方にハッチパターンのフルセットを適用した PostScript ファイルが作成できます—すべて **aspose page java** によって実現されています。

## Aspose.Page Javaでハッチパターンを使用する理由
- **視覚的な区別** – プリンタがモノクロ出力に限定されていてもハッチ塗りが機能します。  
- **パフォーマンス** – テクスチャはオンザフライで生成されるため、大きな画像ファイルを回避できます。  
- **クロスフォーマットサポート** – 同じコードで最小限の変更で PDF、EPS、SVG などに対応できます。

## よくある落とし穴とヒント
- **ファイルパスエラー** – `dataDir` が適切なファイル区切り文字（`/` または `\`）で終わっていることを確認してください。  
- **未対応のカラー** – 古い PostScript インタプリタは特定のカラースペースに対応していない場合があります。最大の互換性のために基本的な RGB を使用してください。  
- **ライセンス警告** – 有効なライセンスなしでサンプルを実行すると、出力に透かしが埋め込まれます。

## 結論
ハッチパターンを組み込むことで、技術図面、地図、または Java で生成されるあらゆるグラフィックの可読性と美観が大幅に向上します。**Aspose.Page Java** を使用すれば、低レベルの PostScript コマンドを抽象化した簡潔な API が提供され、ファイル形式の細部に煩わされることなくデザインに集中できます。これで **PostScript ドキュメントにハッチパターンを追加する方法** が分かりましたので、必要な外観を実現するためにさまざまな `HatchStyle` 値を試してみてください。

## よくある質問

**Q: Aspose.Page Java を他の Java フレームワークと併用できますか？**  
A: はい、ライブラリはフレームワーク非依存で、Spring、Jakarta EE、Android（制限あり）、および純粋な Java SE で動作します。

**Q: Aspose.Page Java のトライアル版は利用可能ですか？**  
A: もちろんです。無料の 30 日間トライアルを [here](https://releases.aspose.com/) からダウンロードしてください。

**Q: 開発用の一時ライセンスはどう取得しますか？**  
A: 一時ライセンスを [here](https://purchase.aspose.com/temporary-license/) からリクエストしてください。評価用の透かしが除去されます。

**Q: もっと多くのチュートリアルやコミュニティサポートはどこで見つけられますか？**  
A: 公式フォーラム [Aspose.Page for Java forum](https://forum.aspose.com/c/page/39) で追加のサンプルや Q&A をご覧ください。

**Q: すべてのクラスとメソッドの包括的なドキュメントはありますか？**  
A: はい、完全な API リファレンスが [here](https://reference.aspose.com/page/java/) で利用可能です。

**Q: 同じハッチパターンを PostScript ではなく PDF にレンダリングできますか？**  
A: もちろんです。`PsSaveOptions` を `PdfSaveOptions`（または同等）に変更すれば、残りのコードはそのままです。

**Q: 生成されたファイルが空の場合はどうすればよいですか？**  
A: 出力ストリームが書き込み可能なディレクトリを指しているか、すべての描画操作の後に `document.save()` が呼び出されているかを確認してください。

---

**最終更新日:** 2026-02-15  
**テスト環境:** Aspose.Page for Java 24.12（執筆時点での最新）  
**作者:** Aspose

{{< /blocks/products/pf/tutorial-page-section >}}

{{< /blocks/products/pf/main-container >}}
{{< /blocks/products/pf/main-wrap-class >}}

{{< blocks/products/products-backtop-button >}}