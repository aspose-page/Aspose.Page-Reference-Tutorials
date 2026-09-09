---
date: 2026-09-09
description: Aspose.Pageを使用してJava PostScriptでgradientを作成し、shapeにgradientを追加する方法を学びます。コードとtipsを含むstep‑by‑stepガイドです。
keywords:
- how to create gradient
- add gradient to shape
- radial gradient Java
lastmod: 2026-09-09
linktitle: Aspose.Pageを使用したJava PostScriptのRadial Gradient
og_description: Aspose.Pageを使用してJava PostScriptでgradientを作成し、shapeにgradientを追加する方法を学びます。コードとtipsを含むstep‑by‑stepガイドです。
og_image_alt: 'Developer guide: create gradient in Java PostScript with radial fill
  using Aspose.Page'
og_title: Java PostScriptでradial fillを使用したgradientの作成方法
schemas:
- author: Aspose
  dateModified: '2026-09-09'
  description: Learn how to create gradient in Java PostScript and add gradient to
    shape using Aspose.Page. Follow this step‑by‑step guide with code and tips.
  headline: How to create gradient in Java PostScript with radial fill
  type: TechArticle
- questions:
  - answer: The full API reference is available in the [Aspose.Page Java API documentation](https://reference.aspose.com/page/java/).
    question: Where can I find the documentation for Aspose.Page for Java?
  - answer: Grab the latest JAR from the [releases page](https://releases.aspose.com/page/java/).
    question: How can I download Aspose.Page for Java?
  - answer: Yes—download a trial version from the [Aspose free trial download page](https://releases.aspose.com/).
    question: Is there a free trial available?
  - answer: Absolutely, request one from the [temporary license page](https://purchase.aspose.com/temporary-license/).
    question: Can I obtain a temporary license for testing?
  - answer: Join the discussion on the [Aspose.Page forum](https://forum.aspose.com/c/page/39).
    question: Where can I get community support?
  type: FAQPage
second_title: Aspose.Page Java API
tags:
- gradient
- Aspose.Page
- Java PostScript
- radial gradient
- fill shape
title: Java PostScriptでradial fillを使用したgradientの作成方法
url: /ja/java/postscript-gradient-addition/radial2/
weight: 13
---

{{< blocks/products/pf/main-wrap-class >}}
{{< blocks/products/pf/main-container >}}
{{< blocks/products/pf/tutorial-page-section >}}

# Java PostScriptで放射状塗りつぶしのグラデーションを作成する方法

## はじめに
このチュートリアルでは、Java と Aspose.Page を使用して PostScript ドキュメント内に **グラデーションの作成方法** のグラフィックを作成する方法を学びます。プロジェクトのセットアップから滑らかな放射状グラデーションで塗りつぶされた円の描画まで、すべての手順を順に解説します。これにより、**シェイプへのグラデーションの追加** を即座に行い、Java アプリケーションのビジュアル品質を向上させることができます。

## クイック回答
- **このチュートリアルは何を作成しますか？** 放射状グラデーションで塗りつぶされた円を含む PostScript ファイル (`.ps`) です。  
- **必要なライブラリはどれですか？** Java 用 Aspose.Page（最新バージョン）です。  
- **実装にどれくらい時間がかかりますか？** 動作する例の場合、約 10‑15 分です。  
- **ライセンスは必要ですか？** 本番利用には一時的または完全なライセンスが必要です。開発には無料トライアルが使用できます。  
- **コードを PDF や SVG 用に再利用できますか？** はい—Aspose.Page は最小の変更で複数の出力フォーマットをサポートしています。  

## PostScript でシェイプをグラデーションで塗りつぶす方法
PostScript でシェイプをグラデーションで塗りつぶすには、`PsDocument` を作成し、`RadialGradientPaint` を定義して対象シェイプに適用し、最後にドキュメントを保存します。この簡潔なワークフローにより、ラスタ画像なしでプロフェッショナルなベクターグラフィックを生成でき、同じコードを PDF や SVG 出力にも再利用できます。プロセスはシンプルで、すべてのサポートフォーマットで一貫して動作します。

## 放射状グラデーションとは？
放射状グラデーションは、中心点から外側へ色が移行する円形のブレンドです。ハイライトやボタンの背景、自然な「光」効果が必要なビジュアルに最適です。カラー ストップと半径を変えることで、照明、奥行き、素材特性を純粋なベクター形式でシミュレートできます。

## 放射状グラデーションに Aspose.Page を使用する理由は？
Aspose.Page は単一の Java API でデバイス非依存のベクターグラフィックを生成できます。PostScript、PDF、SVG など 50 以上の入力・出力フォーマットをサポートし、色精度とアンチエイリアスを保持した高解像度出力が可能です。ライブラリは使いやすいグラデーション クラスも提供し、複雑な視覚効果の実装をシンプルにします。

## 前提条件
- Java プログラミングの基本的な知識。  
- JDK 8 以上がマシンにインストールされていること。  
- Aspose.Page for Java ライブラリ（[Aspose.Page Java ドキュメント](https://reference.aspose.com/page/java/) からダウンロード）。  

## パッケージのインポート
まず、必要なクラスをインポートします。これには標準の AWT グラフィック型と Aspose.Page API が含まれます。

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

## ステップ 1: ドキュメントディレクトリの設定
生成された PostScript ファイルを保存するフォルダーを定義します。プレースホルダーを実際のパスに置き換えてください。

```java
String dataDir = "Your Document Directory";
```

## ステップ 2: 出力ストリームの作成
FileOutputStream は生のバイトをファイルに書き込み、バイナリデータの保存を可能にします。`.ps` ファイルを対象に開くことで、Aspose.Page が生成した PostScript データを直接ディスクにストリームできます。

```java
FileOutputStream outPsStream = new FileOutputStream(dataDir + "RadialGradient2_outPS.ps");
```

## ステップ 3: 保存オプションの作成
PsSaveOptions は PostScript ファイルの保存方法（ページサイズや圧縮など）を構成します。設定をカスタマイズできますが、この例ではデフォルトで問題ありません。

```java
PsSaveOptions options = new PsSaveOptions();
```

## ステップ 4: PS ドキュメントの作成
PsDocument はメモリ内の PostScript ドキュメントを表し、ページやグラフィックを追加するメソッドを提供します。

```java
PsDocument document = new PsDocument(outPsStream, options, false);
```

## ステップ 5: 円の作成
`Ellipse2D.Float` は楕円形状を表します。幅 = 高さのとき、完全な円になります。このオブジェクトがグラデーション塗りつぶしのキャンバスとして使用されます。

```java
Ellipse2D.Float circle = new Ellipse2D.Float(200, 100, 200, 200);
```

## グラデーションで円を描く方法
放射状グラデーションで円を描くには、`RadialGradientPaint` をグラフィックコンテキストにロードし、先に定義した楕円を塗りつぶします。この単一の操作で、中心から外側へ滑らかな色の遷移でシェイプが塗られ、視覚的に魅力的な効果が得られます。

## ステップ 6: グラデーションカラーの定義
2 つの配列を用意します。1 つはグラデーションに使用する色の配列、もう 1 つは対応する位置（0 = 中心、1 = 端）を示す小数配列です。

```java
Color[] colors = { Color.WHITE, Color.WHITE, Color.BLUE };
float[] fractions = { 0.0f, 0.2f, 1.0f };
```

## ステップ 7: AffineTransform の作成
AffineTransform は、グラフィックオブジェクトを平行移動、回転、拡大縮小、せん断できる行列です。ここでは、グラデーションを拡大縮小および平行移動して、円の内部に正確に収まるようにしています。

```java
AffineTransform transform = new AffineTransform(200, 0, 0, 200, 200, 100);
```

## ステップ 8: 放射状グラデーションペイントの作成
RadialGradientPaint は、中心点、半径、カラー ストップに基づいて放射状のカラ―グラデーションを作成します。

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

## ステップ 9: ペイントを設定して円を塗りつぶす
ドキュメントにグラデーションペイントを適用し、先に定義した円を塗りつぶします。これが **放射状グラデーションの例** の核心であり、**シェイプへのグラデーションの塗りつぶし** 方法を示しています。

```java
document.setPaint(paint);
document.fill(circle);
```

## ステップ 10: ページを閉じてドキュメントを保存
ページを確定し、内容をディスクに書き込み、ストリームを閉じます。これで PostScript ファイルは任意の PS ビューアで表示できるようになりました。

```java
document.closePage();
document.save();
```

おめでとうございます！Aspose.Page を使用して Java の PostScript で放射状グラデーションの例を正常に作成しました。これで、**シェイプへのグラデーションの塗りつぶし** 用の再利用可能なパターンが手に入り、他の形状や出力フォーマットにも適用できます。

## 一般的な問題と解決策
| 問題 | 解決策 |
|---------|----------|
| **FileNotFoundException** が出力ストリームを開くときに発生 | `dataDir` が既存のフォルダーを指しており、書き込み権限があることを確認してください。 |
| グラデーションが平坦に見える、または欠落している | `fractions` 配列が `colors` 配列の長さと一致し、`AffineTransform` が正しくスケーリングされていることを確認してください。 |
| 色が逆転して表示される | `colors` 配列の順序を入れ替えるか、`focus` ポイントの座標を調整してください。 |

## よくある質問

**Q: Aspose.Page for Java のドキュメントはどこで見つけられますか？**  
A: 完全な API リファレンスは [Aspose.Page Java API ドキュメント](https://reference.aspose.com/page/java/) にあります。

**Q: Aspose.Page for Java をダウンロードするにはどうすればよいですか？**  
A: 最新の JAR は [releases page](https://releases.aspose.com/page/java/) から取得してください。

**Q: 無料トライアルは利用可能ですか？**  
A: はい—[Aspose free trial download page](https://releases.aspose.com/) からトライアル版をダウンロードしてください。

**Q: テスト用の一時ライセンスを取得できますか？**  
A: もちろんです、[temporary license page](https://purchase.aspose.com/temporary-license/) からリクエストしてください。

**Q: コミュニティサポートはどこで得られますか？**  
A: [Aspose.Page forum](https://forum.aspose.com/c/page/39) で議論に参加してください。

## 結論
このガイドでは、Aspose.Page for Java を使用して PostScript ドキュメント用の完全な **放射状グラデーションの例** を作成しました。手順に従うことで、**シェイプへのグラデーションの塗りつぶし** 用の再利用可能なパターンが手に入り、PDF、SVG、または Aspose.Page がサポートする他のフォーマットにも適用できます。さまざまな色、半径、形状を試して、Java グラフィックプロジェクトを充実させてください。

---

**最終更新日:** 2026-09-09  
**テスト環境:** Aspose.Page for Java 24.11 (執筆時点での最新)  
**作者:** Aspose

## 関連チュートリアル

- [Java で PostScript グラデーションを作成 – 垂直グラデーションを追加](/page/java/postscript-gradient-addition/vertical/)
- [Aspose.Page for Java を使用して PostScript にテクスチャパターンを作成](/page/java/postscript-texture-patterns/)
- [Aspose.Page 透過チュートリアル – Java PostScript に透過を追加](/page/java/postscript-transparency/)

{{< /blocks/products/pf/tutorial-page-section >}}

{{< /blocks/products/pf/main-container >}}
{{< /blocks/products/pf/main-wrap-class >}}

{{< blocks/products/products-backtop-button >}}