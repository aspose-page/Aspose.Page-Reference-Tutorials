---
date: 2026-02-13
description: Aspose.Page for Java を使用して、ラジアル カラーストップ グラデーションを持つ PostScript グラデーションの作成方法を学びましょう。このステップバイステップ
  ガイドでは、ドキュメントにカラーストップ グラデーションを追加する方法を示します。
linktitle: Mastering Radial Gradients in Java
second_title: Aspose.Page Java API
title: PostScript グラデーションの作成 – Java におけるラジアルグラデーション
url: /ja/java/postscript-gradient-addition/radial1/
weight: 12
---

{{< blocks/products/pf/main-wrap-class >}}
{{< blocks/products/pf/main-container >}}
{{< blocks/products/pf/tutorial-page-section >}}

# Java PostScriptでRadial Gradientを追加する方法（Aspose.Page使用）

## はじめに
スムーズで目を引く色の遷移を持つ **PostScript グラデーション** を作成する必要がある場合、放射状グラデーションの追加方法を学ぶことが最適です。このチュートリアルでは、**Aspose.Page for Java** ライブラリを使用して、美しい放射状グラデーションを含む PostScript ファイルを生成するために必要なすべての手順を順に解説します。最後まで読むと、API の概要が把握でき、完全に実行可能なサンプルが見られ、色・位置・半径を任意のデザインに合わせて調整する方法がわかります。

## クイック回答
- **PostScriptで放射状グラデーションを作成するライブラリは何ですか？** Aspose.Page for Java.  
- **実装にどれくらい時間がかかりますか？** 基本的な例で約10〜15分です。  
- **コードを実行するのにライセンスは必要ですか？** 開発目的なら無料トライアルで動作しますが、製品環境では商用ライセンスが必要です。  
- **サポートされている Java バージョンはどれですか？** Java 8 以降。  
- **グラデーションの形状を変更できますか？** はい – `RadialGradientPaint` コンストラクタで半径と中心点を調整します。

## 放射状塗りでPostScriptグラデーションを作成する方法
以下に、放射状塗りを使用して **PostScript グラデーション** コンテンツを作成する手順を簡潔に示します。各ステップには短い説明と、変更なしの元のコードブロックが続きます。

## 放射状グラデーションとは？
放射状グラデーションは、中心点から外側へ放射状に色が広がり、徐々にエッジへブレンドされます。線形グラデーションとは異なり、色の遷移は円形（または楕円形）パターンに従うため、ハイライトやスポットライト、柔らかな背景塗りに最適です。

## なぜAspose.Pageを放射状グラデーションに使用するのか？
- **PostScript 出力をフルコントロール** – 低レベルの PS コマンドを手作業で書く必要がありません。  
- **クロスプラットフォーム** – Java が動作する任意の OS で利用可能です。  
- **リッチなカラー管理** – 複数のカラー ストップ、さまざまなカラースペース、サイクルメソッドをサポート。  
- **統合準備完了** – テキスト、画像、ベクタ形状など、他の Aspose.Page 機能と組み合わせて使用できます。

## 前提条件
コードに入る前に、以下が準備できていることを確認してください。

- **Java Development Kit (JDK) 8+** – `java -version` で確認してください。  
- **Aspose.Page for Java** – 公式の [Aspose.Page ダウンロードページ](https://releases.aspose.com/page/java/) から最新の JAR を取得。  
- **お好みの IDE** – Eclipse、IntelliJ IDEA、または Java 拡張機能付き VS Code。  
- **書き込み可能なフォルダー** – 生成された `.ps` ファイルを保存する場所。

## パッケージのインポート
まず、必要なクラスをインポートします。`java.awt` パッケージはグラデーションペイントオブジェクトを提供し、`com.aspose.eps` には PostScript ドキュメント処理クラスが含まれます。

```java
import java.awt.Color;
import java.awt.MultipleGradientPaint;
import java.awt.RadialGradientPaint;
import java.awt.geom.AffineTransform;
import java.awt.geom.Point2D;
import java.awt.geom.Rectangle2D;
import java.io.FileOutputStream;
import com.aspose.eps.PsDocument;
import com.aspose.eps.device.PsSaveOptions;
```

## ステップバイステップガイド

### 手順 1: 矩形を作成し PS ドキュメントを開く
出力ストリームを作成し、ページサイズ（デフォルトは A4）を設定し、グラデーションを配置する矩形を定義します。

```java
// The path to the documents directory.
String dataDir = "Your Document Directory";
// Create output stream for PostScript document
FileOutputStream outPsStream = new FileOutputStream(dataDir + "RadialGradient1_outPS.ps");
// Create save options with A4 size
PsSaveOptions options = new PsSaveOptions();
// Create new PS Document with the page opened
PsDocument document = new PsDocument(outPsStream, options, false);
// Create a rectangle
Rectangle2D.Float rectangle = new Rectangle2D.Float(200, 100, 200, 200);
```

> **Pro tip:** 矩形の座標 (`200, 100, 200, 200`) を調整して、ページ上の任意の位置にグラデーションを配置できます。

### 手順 2: 色とフラクションを定義する
放射状グラデーションは *カラー ストップ*（色）と *フラクション*（それらの相対位置）から構成されます。ここでは 6 色とそれに対応するフラクションの配列を作成します。

```java
// Create arrays of colors and fractions for the gradient
Color[] colors = { Color.GREEN, Color.BLUE, Color.BLACK, Color.YELLOW, new Color(245, 245, 220), Color.RED };
float[] fractions = { 0.0f, 0.2f, 0.3f, 0.4f, 0.9f, 1.0f };
```

> **Why this matters:** `fractions` を調整することで、色の遷移速度を制御でき、微妙な効果から劇的な効果まで実現できます。

### 放射状塗りにカラー ストップ グラデーションを追加する
**add color stops gradient** が必要な場合は、`colors` と `fractions` 配列が鍵となります。デザインに合わせて順序を入れ替えたり、追加・削除したりしてください。

### 手順 3: Radial Gradient Paint を作成する
次に `RadialGradientPaint` オブジェクトを構築します。コンストラクタは中心点、半径、焦点、フラクション、色、サイクルメソッド、カラースペース、オプションの変換を受け取ります。

```java
// Create radial gradient paint
RadialGradientPaint paint = new RadialGradientPaint(
        new Point2D.Float(300, 200),      // center of the gradient
        100,                              // radius
        new Point2D.Float(300, 200),      // focus point (same as center for a symmetric gradient)
        fractions,
        colors,
        MultipleGradientPaint.CycleMethod.NO_CYCLE,
        MultipleGradientPaint.ColorSpaceType.SRGB,
        transform);
```

> **Note:** 追加のスケーリングや回転が不要な場合、`transform` は `null` にできます。`AffineTransform` を使って傾斜したグラデーションを試してみても構いません。

### 手順 4: Paint を設定し矩形を塗りつぶす
ペイントが準備できたら、`PsDocument` にそれを使用させ、先に定義した矩形を塗りつぶします。

```java
// Set paint
document.setPaint(paint);
// Fill the rectangle
document.fill(rectangle);
```

この時点で、PostScript ページには設定した放射状グラデーションで滑らかに塗りつぶされた矩形が描かれます。

### 手順 5: ドキュメントを閉じて保存する
最後に現在のページを閉じ、ファイルをディスクに書き出します。

```java
// Close current page
document.closePage();
// Save the document
document.save();
```

`RadialGradient1_outPS.ps` を任意の PostScript ビューア（例: Ghostscript）で開くと、定義通りにレンダリングされたグラデーションが確認できます。

## よくある問題と解決策
| 症状 | 考えられる原因 | 対策 |
|------|----------------|------|
| グラデーションが単色で表示される | `fractions` 配列が `0.0f` で始まっていない、または `1.0f` で終わっていない | 最初のフラクションが `0.0f`、最後が `1.0f` であることを確認してください。 |
| 色がくすんで見える | 間違った `ColorSpaceType` を使用している | `MultipleGradientPaint.ColorSpaceType.LINEAR_RGB` に切り替えて、より鮮やかな出力にします。 |
| 出力ファイルが生成されない | `FileOutputStream` のパスが無効か書き込み不可 | `dataDir` が存在し、アプリケーションに書き込み権限があることを確認してください。 |

## よくある質問

**Q: Aspose.Page for Java を商用プロジェクトで使用できますか？**  
A: はい。製品環境での使用には商用ライセンスが必要です。ライセンスは [Aspose ライセンスページ](https://purchase.aspose.com/buy) から購入できます。

**Q: 公式 API リファレンスはどこにありますか？**  
A: 完全なドキュメントは [こちら](https://reference.aspose.com/page/java/) にあります。

**Q: 無料トライアルは利用できますか？**  
A: もちろんです。トライアル版は [Aspose.Page リリースページ](https://releases.aspose.com/) からダウンロードできます。

**Q: 評価用の一時ライセンスはどう取得しますか？**  
A: 一時ライセンスは [こちら](https://purchase.aspose.com/temporary-license/) からリクエストできます。

**Q: コミュニティサポートはどこで受けられますか？**  
A: Aspose.Page コミュニティフォーラムは [forum.aspose.com/c/page/39](https://forum.aspose.com/c/page/39) で利用できます。

## 結論
これで **Java PostScript ドキュメントに放射状グラデーションを追加する方法** が分かりました。矩形サイズ、カラー ストップ、グラデーション半径を調整すれば、微妙な背景塗りから大胆なスポットライト表現まで、無限に近いビジュアル効果を作り出せます。`AffineTransform` の値を変えて回転や歪みを加える実験もぜひ行い、テキストや画像と組み合わせて PDF や EPS の出力をさらにリッチにしてください。

---

**Last Updated:** 2026-02-13  
**Tested With:** Aspose.Page for Java latest (as of writing)  
**Author:** Aspose  

{{< /blocks/products/pf/tutorial-page-section >}}

{{< /blocks/products/pf/main-container >}}
{{< /blocks/products/pf/main-wrap-class >}}

{{< blocks/products/products-backtop-button >}}