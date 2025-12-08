---
date: 2025-12-08
description: Aspose.Page を使用して Java の PostScript に放射状グラデーションを追加する方法を学びましょう。このステップバイステップガイドでは、ドキュメントに驚くべきグラデーション効果を作成する方法を示します。
language: ja
linktitle: Mastering Radial Gradients in Java
second_title: Aspose.Page Java API
title: Aspose.Page を使用した Java PostScript での放射状グラデーションの追加方法
url: /java/postscript-gradient-addition/radial1/
weight: 12
---

{{< blocks/products/pf/main-wrap-class >}}
{{< blocks/products/pf/main-container >}}
{{< blocks/products/pf/tutorial-page-section >}}

# Java PostScript で放射状グラデーションを追加する方法

## Introduction
PostScript の出力に滑らかで目を引く色の遷移を加えたいときは、**放射状グラデーションの追加方法** を学ぶのが最適です。このチュートリアルでは、**Aspose.Page for Java** ライブラリを使用して、美しい放射状グラデーションを含む PostScript ファイルを生成する手順をすべて解説します。最後まで読めば API の使い方が分かり、実行可能なサンプルコードを確認でき、色・位置・半径の調整方法もマスターできます。

## Quick Answers
- **PostScript で放射状グラデーションを作成するライブラリは？** Aspose.Page for Java。  
- **実装にかかる時間は？** 基本的な例で約 10〜15 分。  
- **コード実行にライセンスは必要？** 開発段階は無料トライアルで動作します。商用利用には商用ライセンスが必要です。  
- **対応している Java バージョンは？** Java 8 以降。  
- **グラデーションの形状は変更できる？** はい。`RadialGradientPaint` コンストラクタの半径と中心点を調整します。

## What is a Radial Gradient?
放射状グラデーションは、中心点から外側へ向かって色が放射状に変化し、端に向かって徐々にブレンドされます。線形グラデーションとは異なり、色の遷移は円形（または楕円形）パターンになるため、ハイライトやスポットライト、柔らかな背景塗りに最適です。

## Why Use Aspose.Page for Radial Gradients?
- **PostScript 出力をフルコントロール** – 低レベルの PS コマンドを手書きする必要がありません。  
- **クロスプラットフォーム** – Java が動作する OS ならどこでも利用可能。  
- **リッチなカラー管理** – 複数のカラーストップ、さまざまなカラースペース、サイクルメソッドに対応。  
- **統合が容易** – テキスト、画像、ベクタ形状など、他の Aspose.Page 機能と組み合わせて使用可能。

## Prerequisites
コードに入る前に、以下の環境を準備してください。

- **Java Development Kit (JDK) 8+** – `java -version` で確認。  
- **Aspose.Page for Java** – 公式の [Aspose.Page ダウンロードページ](https://releases.aspose.com/page/java/) から最新 JAR を取得。  
- **お好みの IDE** – Eclipse、IntelliJ IDEA、または Java 拡張機能付き VS Code。  
- **書き込み可能なフォルダー** – 生成される `.ps` ファイルを保存する場所。

## Import Packages
まず、必要なクラスをインポートします。`java.awt` パッケージはグラデーションペイントオブジェクトを提供し、`com.aspose.eps` が PostScript ドキュメント操作クラスを含みます。

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

## Step‑by‑Step Guide

### Step 1: Create a Rectangle and Open a PS Document
出力ストリームを作成し、ページサイズ（デフォルトは A4）を設定し、グラデーションを描画する矩形を定義します。

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

> **Pro tip:** 矩形の座標 (`200, 100, 200, 200`) を調整すれば、ページ上の任意の位置にグラデーションを配置できます。

### Step 2: Define Colors and Fractions
放射状グラデーションは *カラーストップ*（色）と *フラクション*（それらの相対位置）から構成されます。ここでは 6 色と対応するフラクションの配列を作成します。

```java
// Create arrays of colors and fractions for the gradient
Color[] colors = { Color.GREEN, Color.BLUE, Color.BLACK, Color.YELLOW, new Color(245, 245, 220), Color.RED };
float[] fractions = { 0.0f, 0.2f, 0.3f, 0.4f, 0.9f, 1.0f };
```

> **Why this matters:** `fractions` を調整することで、色の遷移速度を制御でき、微妙な効果からドラマチックな効果まで実現できます。

### Step 3: Create Radial Gradient Paint
次に `RadialGradientPaint` オブジェクトを作成します。コンストラクタは中心点、半径、焦点、フラクション、色、サイクルメソッド、カラースペース、オプションの変換を受け取ります。

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

> **Note:** 追加のスケーリングや回転が不要な場合は `transform` を `null` にできます。`AffineTransform` を使って傾斜したグラデーションを試すのも面白いでしょう。

### Step 4: Set Paint and Fill the Rectangle
ペイントが準備できたら、`PsDocument` に設定し、先ほど定義した矩形を塗りつぶします。

```java
// Set paint
document.setPaint(paint);
// Fill the rectangle
document.fill(rectangle);
```

この時点で、PostScript ページには放射状グラデーションで滑らかに塗りつぶされた矩形が描画されています。

### Step 5: Close and Save the Document
最後に現在のページを閉じ、ファイルをディスクに書き出します。

```java
// Close current page
document.closePage();
// Save the document
document.save();
```

`RadialGradient1_outPS.ps` を任意の PostScript ビューア（例: Ghostscript）で開くと、定義通りのグラデーションが表示されます。

## Common Issues & Solutions
| 症状 | 想定原因 | 対策 |
|------|----------|------|
| グラデーションが単色になる | `fractions` 配列が `0.0f` で始まっていない、または `1.0f` で終わっていない | 最初のフラクションを `0.0f`、最後を `1.0f` にしてください。 |
| 色がくすんで見える | 誤った `ColorSpaceType` を使用している | より鮮やかな出力には `MultipleGradientPaint.ColorSpaceType.LINEAR_RGB` に切り替えてください。 |
| 出力ファイルが生成されない | `FileOutputStream` のパスが無効、または書き込み権限がない | `dataDir` が存在し、アプリケーションに書き込み権限があることを確認してください。 |

## Frequently Asked Questions

**Q: Aspose.Page for Java を商用プロジェクトで使用できますか？**  
A: はい。商用利用には商用ライセンスが必要です。ライセンスは [Aspose ライセンスページ](https://purchase.aspose.com/buy) から購入できます。

**Q: 公式 API リファレンスはどこにありますか？**  
A: 完全なドキュメントは [こちら](https://reference.aspose.com/page/java/) にあります。

**Q: 無料トライアルは利用できますか？**  
A: もちろんです。トライアル版は [Aspose.Page リリースページ](https://releases.aspose.com/) からダウンロードできます。

**Q: 評価用の一時ライセンスはどう取得しますか？**  
A: 一時ライセンスは [こちら](https://purchase.aspose.com/temporary-license/) からリクエストできます。

**Q: コミュニティサポートはどこで受けられますか？**  
A: Aspose.Page のフォーラムは [forum.aspose.com/c/page/39](https://forum.aspose.com/c/page/39) で参加できます。

## Conclusion
これで **Java の PostScript ドキュメントに放射状グラデーションを追加する方法** が分かりました。矩形サイズ、カラーストップ、グラデーション半径を調整すれば、微妙な背景から大胆なスポットライトまで、無限のビジュアル効果を作り出せます。`AffineTransform` の値を変えて回転や歪みを加えたり、テキストや画像と組み合わせて PDF や EPS の出力をさらにリッチに仕上げてみてください。

---

**Last Updated:** 2025-12-08  
**Tested With:** Aspose.Page for Java 24.12 (latest at time of writing)  
**Author:** Aspose  

{{< /blocks/products/pf/tutorial-page-section >}}

{{< /blocks/products/pf/main-container >}}
{{< /blocks/products/pf/main-wrap-class >}}

{{< blocks/products/products-backtop-button >}}