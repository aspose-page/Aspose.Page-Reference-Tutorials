---
date: 2025-12-08
description: Aspose.Page を使用して Java PostScript で放射状グラデーションの例を作成する方法を学びましょう。フルコードとトラブルシューティングを含むステップバイステップガイド。
linktitle: Java PostScript Radial Gradient with Aspose.Page
second_title: Aspose.Page Java API
title: 放射状グラデーション例：Aspose.Page を使用した Java PostScript
url: /ja/java/postscript-gradient-addition/radial2/
weight: 13
---

{{< blocks/products/pf/main-wrap-class >}}
{{< blocks/products/pf/main-container >}}
{{< blocks/products/pf/tutorial-page-section >}}

# 放射状グラデーション例：Java PostScript と Aspose.Page

## Introduction
このチュートリアルでは、Aspose.Page for Java を使用して PostScript ドキュメント用の **放射状グラデーション例** を作成します。プロジェクトのセットアップから、滑らかな放射状グラデーションで塗りつぶされた円の描画まで、すべての手順を詳しく解説するので、Java アプリケーションにすぐに目を引くグラフィックを追加できます。

## Quick Answers
- **このチュートリアルが作成するものは何ですか？** 放射状グラデーションで塗りつぶされた円を含む PostScript ファイル（`.ps`）。  
- **必要なライブラリはどれですか？** Aspose.Page for Java（最新バージョン）。  
- **実装にどれくらい時間がかかりますか？** 動作する例を作るのに約 10〜15 分。  
- **ライセンスは必要ですか？** 本番利用には一時的またはフルライセンスが必要です。開発時は無料トライアルで動作します。  
- **PDF や SVG 用にコードを再利用できますか？** はい。Aspose.Page は最小限の変更で複数の出力形式をサポートします。

## What Is a Radial Gradient?
放射状グラデーションは、中心点から外側へ色が変化していく円形の滑らかなブレンドです。ハイライトやボタンの背景、自然な「光」効果が必要なビジュアルに最適です。

## Why Use Aspose.Page for Radial Gradients?
- **Device‑independent rendering** – PostScript、PDF、SVG などで同じ結果が得られます。  
- **Full Java integration** – ネイティブコード不要、純粋な Java API だけです。  
- **High‑quality output** – アンチエイリアスとカラースペース制御をサポートします。

## Prerequisites
始める前に以下を用意してください。

- Java プログラミングの基本的な知識。  
- JDK 8 以上がインストールされていること。  
- Aspose.Page for Java ライブラリ（[Aspose.Page Java documentation](https://reference.aspose.com/page/java/) からダウンロード）。

## Import Packages
まず、必要なクラスをインポートします。標準の AWT グラフィック型と Aspose.Page API が含まれます。

```java
import java.awt.Color;
import java.awt.MultipleGradientPaint;
import java.awt.RadialGradientPaint;
import java.awt.geom.AffineTransform;
import java.awt.geom.Ellipse2D;
import java.awt.geom.Point2D;
import java.io.FileOutputStream;
import com.aspose.eps.PsDocument;
import com.aspose.eps.device.PsSaveOptions;
```

## Step 1: Set Up Document Directory
生成された PostScript ファイルを保存するフォルダーを定義します。プレースホルダーは実際のパスに置き換えてください。

```java
String dataDir = "Your Document Directory";
```

## Step 2: Create Output Stream
対象の `.ps` ファイルを指す `FileOutputStream` を開きます。このストリームが Aspose.Page によって生成されたバイナリデータを受け取ります。

```java
FileOutputStream outPsStream = new FileOutputStream(dataDir + "RadialGradient2_outPS.ps");
```

## Step 3: Create Save Options
`PsSaveOptions` をインスタンス化します。ページサイズや圧縮などをカスタマイズできますが、デフォルトでこの例は問題ありません。

```java
PsSaveOptions options = new PsSaveOptions();
```

## Step 4: Create PS Document
出力ストリームと保存オプションを渡して `PsDocument` オブジェクトを作成します。`false` フラグは Aspose.Page に自動でページを開かせず、手動で行うことを示します。

```java
PsDocument document = new PsDocument(outPsStream, options, false);
```

## Step 5: Create a Circle
`Ellipse2D.Float` を使って円を描きます。パラメータは `(x, y, width, height)` です。幅と高さを同じにすると完全な円になります。

```java
Ellipse2D.Float circle = new Ellipse2D.Float(200, 100, 200, 200);
```

## Step 6: Define Gradient Colors
グラデーションに使用する色の配列と、対応する位置（0 = 中心、1 = 端）を示す分数配列の 2 つを用意します。

```java
Color[] colors = { Color.WHITE, Color.WHITE, Color.BLUE };
float[] fractions = { 0.0f, 0.2f, 1.0f };
```

## Step 7: Create AffineTransform
`AffineTransform` はグラデーションを円に合わせて拡大・平行移動します。行列 `(scaleX, 0, 0, scaleY, translateX, translateY)` がその役割を果たします。

```java
AffineTransform transform = new AffineTransform(200, 0, 0, 200, 200, 100);
```

## Step 8: Create Radial Gradient Paint
ここで `RadialGradientPaint` オブジェクトを構築します。中心点、半径、焦点、色の分数、色配列、サイクルメソッド、カラースペース、先ほど定義した変換を渡します。

```java
RadialGradientPaint paint = new RadialGradientPaint(
        new Point2D.Float(64, 64),   // gradient center
        68,                          // radius
        new Point2D.Float(24, 24),   // focus point
        fractions,
        colors,
        MultipleGradientPaint.CycleMethod.NO_CYCLE,
        MultipleGradientPaint.ColorSpaceType.SRGB,
        transform);
```

## Step 9: Set Paint and Fill Circle
ドキュメントにグラデーションペイントを設定し、先に定義した円を塗りつぶします。これが **放射状グラデーション例** の核心です。

```java
document.setPaint(paint);
document.fill(circle);
```

## Step 10: Close Page and Save Document
ページを確定し、内容をディスクに書き込み、ストリームを閉じます。これで PostScript ファイルが任意の PS ビューアで閲覧可能になります。

```java
document.closePage();
document.save();
```

おめでとうございます！Aspose.Page を使用して Java PostScript で放射状グラデーション例を正常に作成できました。

## Common Issues and Solutions
| Problem | Solution |
|---------|----------|
| **FileNotFoundException** が出力ストリームのオープン時に発生 | `dataDir` が実在するフォルダーを指しているか、書き込み権限があるか確認してください。 |
| グラデーションが平坦または表示されない | `fractions` 配列の長さが `colors` 配列と一致しているか、`AffineTransform` のスケーリングが正しいか確認してください。 |
| 色が逆転して表示される | `colors` 配列の順序を入れ替えるか、`focus` 点の座標を調整してください。 |

## Frequently Asked Questions

**Q: Aspose.Page for Java のドキュメントはどこで確認できますか？**  
A: 完全な API リファレンスは [here](https://reference.aspose.com/page/java/) にあります。

**Q: Aspose.Page for Java をダウンロードするには？**  
A: 最新の JAR は [releases page](https://releases.aspose.com/page/java/) から取得してください。

**Q: 無料トライアルはありますか？**  
A: はい、トライアル版は [here](https://releases.aspose.com/) からダウンロードできます。

**Q: テスト用の一時ライセンスは取得できますか？**  
A: もちろんです。取得は [temporary license page](https://purchase.aspose.com/temporary-license/) から行えます。

**Q: コミュニティサポートはどこで受けられますか？**  
A: [Aspose.Page forum](https://forum.aspose.com/c/page/39) で議論に参加してください。

## Conclusion
このガイドでは、Aspose.Page for Java を使用して PostScript ドキュメント用の **放射状グラデーション例** を作成しました。手順に従うことで、PDF、SVG、その他のサポート形式にも応用できる再利用可能なパターンが手に入ります。さまざまな色、半径、形状を試して、Java グラフィックプロジェクトをさらに豊かにしてください。

---

**Last Updated:** 2025-12-08  
**Tested With:** Aspose.Page for Java 24.11 (latest at time of writing)  
**Author:** Aspose  

{{< /blocks/products/pf/tutorial-page-section >}}

{{< /blocks/products/pf/main-container >}}
{{< /blocks/products/pf/main-wrap-class >}}

{{< blocks/products/products-backtop-button >}}