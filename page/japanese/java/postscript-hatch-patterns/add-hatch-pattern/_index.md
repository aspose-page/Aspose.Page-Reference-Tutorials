---
date: 2025-12-08
description: Aspose.Page Java を使用して、Java の PostScript ドキュメントにハッチパターンを追加する方法を学びましょう。このステップバイステップガイドでは、ハッチパターンのグラフィックを効率的に追加する方法を示します。
linktitle: Add Hatch Pattern in Java PostScript
second_title: Aspose.Page Java API
title: 'Aspose.Page Java: JavaのPostScriptにハッチパターンを追加'
url: /ja/java/postscript-hatch-patterns/add-hatch-pattern/
weight: 10
---

{{< blocks/products/pf/main-wrap-class >}}
{{< blocks/products/pf/main-container >}}
{{< blocks/products/pf/tutorial-page-section >}}

# Java PostScript にハッチパターンを追加する

## はじめに
**Aspose.Page Java** を使用していて、テクスチャ付きグラフィックで PostScript 出力を充実させたい場合、ハッチパターンは高速かつ柔軟なソリューションです。このチュートリアルでは、PostScript ドキュメントに **ハッチを追加する方法** を順を追って説明し、その有用性を解説し、完全な実行可能コード例を提供します。最後まで読むと、数行の Java コードだけで視覚的に魅力的なハッチ塗りの形状やテキストを作成できるようになります。

## クイック回答
- **必要なライブラリは何ですか？** Aspose.Page for Java（“aspose page java” SDK）。  
- **追加するビジュアル効果は何ですか？** ハッチパターン（例：対角線、クロスハッチ）。  
- **サンプルを実行するのにライセンスは必要ですか？** 開発には無料トライアルで動作しますが、製品版ではライセンスが必要です。  
- **コード行数はどれくらいですか？** 約 70 行で、明確なステップに分かれています。  
- **PDF にも同じアプローチを使用できますか？** はい—Aspose.Page は PDF を含む複数の出力フォーマットをサポートしています。

## 前提条件
開始する前に、以下が揃っていることを確認してください：

- **Java 開発環境** – JDK 8 以上とお好みの IDE。  
- **Aspose.Page for Java ライブラリ** – 公式サイトから最新の JAR をダウンロードしてください [here](https://releases.aspose.com/page/java/)。  
- **書き込み権限** – 生成された PostScript ファイルを保存するフォルダーへの書き込み権限。

## パッケージのインポート
まず、必要なクラスをプロジェクトにインポートします。これらのインポートにより、描画プリミティブ、カラー処理、そして Aspose.Page API にアクセスできます。

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
出力ストリームを作成し、ページサイズ（A4）を設定し、各ハッチ塗りの正方形を描画する際に再利用されるレイアウト変数をいくつか定義します。

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
グラフィックス状態を保存することで、後で元の座標系に戻すことができ、`translate` は原点を便利な開始点へ移動させます。

```java
document.writeGraphicsSave();
document.translate(x0, y0);
```

## ステップ 3: 各パターン用の正方形作成
各ハッチ塗りセルを表す再利用可能な矩形を定義します。

```java
Rectangle2D.Float square = new Rectangle2D.Float(0, 0, squareSide, squareSide);
```

## ステップ 4: パターン正方形のアウトライン用ペン設定
`BasicStroke` を 2 ポイントに設定すると、すべての正方形に鮮明なアウトラインが付与されます。

```java
BasicStroke stroke = new BasicStroke(2);
```

## ステップ 5: ハッチパターンの反復処理
`HatchStyle` 列挙型のすべての値をループし、各正方形を対応するテクスチャで塗り、そしてアウトラインを描画します。これが **ハッチパターン追加** 機能の核心です。

```java
HatchStyle[] hatchStyles = HatchStyle.values();
for (int i = 0; i < hatchStyles.length; i++) {
    // ... (continue with the provided code)
}
```

## ステップ 6: グラフィックス状態の復元
正方形のグリッド描画が完了したら、元の座標系に戻ります。

```java
document.writeGraphicsRestore();
```

## ステップ 7: テキストをハッチパターンで塗りつぶす
ここでは、ハッチテクスチャを使用してテキストを塗りつぶす方法を示します。例では、単語 “ABC” を対角クロスパターンで塗りつぶします。

```java
TexturePaint paint = HatchPaintLibrary.getHatchTexturePaint(HatchStyle.DiagonalCross, Color.RED, Color.YELLOW);
Font font = new Font("Arial", Font.BOLD, 96);
document.fillAndStrokeText("ABC", font, 200, 320, paint, Color.BLACK, stroke);
```

## ステップ 8: テキストをハッチパターンでアウトライン
同じテキストにアウトラインを付けますが、今回は 70 % のハッチスタイルと太めのストロークを使用します。

```java
paint = HatchPaintLibrary.getHatchTexturePaint(HatchStyle.Percent70, Color.BLUE, Color.WHITE);
document.outlineText("ABC", font, 200, 420, paint, new BasicStroke(5));
```

## ステップ 9: ドキュメントのクローズと保存
ページを最終化し、ファイルをディスクに書き込み、リソースを解放します。

```java
document.closePage();
document.save();
```

これらの手順に従うと、形状とテキストの両方にハッチパターンの全セットが適用された PostScript ファイルが作成できます—すべて **aspose page java** によって実現されています。

## Aspose.Page Java でハッチパターンを使用する理由
- **視覚的な区別** – ハッチ塗りは、プリンターがモノクロ出力に限定されている場合でも機能します。  
- **パフォーマンス** – テクスチャはリアルタイムで生成されるため、大きな画像ファイルを回避できます。  
- **クロスフォーマットサポート** – 同じコードで最小限の変更で PDF、EPS、SVG などを対象にできます。

## よくある落とし穴とヒント
- **ファイルパスエラー** – `dataDir` が適切なファイル区切り文字（`/` または `\`）で終わっていることを確認してください。  
- **未対応の色** – 古い PostScript インタプリタは特定のカラースペースに対応していない場合があります。最大の互換性のために基本的な RGB を使用してください。  
- **ライセンス警告** – 有効なライセンスなしでサンプルを実行すると、出力に透かしが埋め込まれます。

## 結論
ハッチパターンを組み込むことで、技術図面、地図、または Java で生成されたあらゆるグラフィックの可読性と美観を劇的に向上させることができます。**Aspose.Page Java** を使用すれば、低レベルの PostScript コマンドを抽象化した簡潔な API が提供され、ファイル形式の細かな違いに悩むことなくデザインに集中できます。

## よくある質問

**Q: Aspose.Page Java を他の Java フレームワークと併用できますか？**  
A: はい、ライブラリはフレームワーク非依存で、Spring、Jakarta EE、Android（制限あり）、および純粋な Java SE で動作します。

**Q: Aspose.Page Java のトライアル版は利用できますか？**  
A: もちろんです。無料の 30 日間トライアルを [here](https://releases.aspose.com/) からダウンロードしてください。

**Q: 開発用の一時ライセンスはどう取得しますか？**  
A: 一時ライセンスを [here](https://purchase.aspose.com/temporary-license/) でリクエストしてください。評価用の透かしが除去されます。

**Q: さらにチュートリアルやコミュニティサポートはどこで見つけられますか？**  
A: 公式フォーラム [Aspose.Page for Java forum](https://forum.aspose.com/c/page/39) を訪れて、追加の例や Q&A をご覧ください。

**Q: すべてのクラスとメソッドの包括的なドキュメントはありますか？**  
A: はい、完全な API リファレンスは [here](https://reference.aspose.com/page/java/) で入手可能です。

---

**最終更新日:** 2025-12-08  
**テスト環境:** Aspose.Page for Java 24.12 (執筆時点での最新)  
**作者:** Aspose

{{< /blocks/products/pf/tutorial-page-section >}}

{{< /blocks/products/pf/main-container >}}
{{< /blocks/products/pf/main-wrap-class >}}

{{< blocks/products/products-backtop-button >}}
