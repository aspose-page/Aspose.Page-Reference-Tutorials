---
date: 2025-12-18
description: Aspose.Page を使用して Java の XPS ドキュメントにグリッドと透明な矩形を追加する方法を学びましょう。XPS ドキュメントを効率的に保存するためのステップバイステップガイドです。
linktitle: How to Add Grid using Visual Brush in Java
second_title: Aspose.Page Java API
title: JavaでVisual Brushを使ってグリッドを追加する方法
url: /ja/java/visual-elements/add-grid/
weight: 10
---

{{< blocks/products/pf/main-wrap-class >}}
{{< blocks/products/pf/main-container >}}
{{< blocks/products/pf/tutorial-page-section >}}

# JavaでVisual Brushを使用してグリッドを追加する方法

## はじめに
Javaで生成したXPSドキュメントに **グリッドを追加する方法** を探しているなら、ここが適切な場所です。このチュートリアルでは、Visual Brush を使用してグリッドを追加し、透明な長方形を重ね、最後に Aspose.Page Java API を使って **XPS ドキュメントを保存** する手順を説明します。最後まで実行すれば、レポートや請求書、その他ドキュメント中心のアプリケーションで再利用できる洗練されたビジュアルが得られます。

## クイック回答
- **Visual Brush は何をするものですか？** 再利用可能なビジュアルコンテンツで定義された領域を塗りつぶし、グリッドのような繰り返しパターンに最適です。  
- **グリッドの色を変更できますか？** はい – ブラシのソリッドカラー設定を変更します。  
- **グリッドの上に透明な長方形を追加するには？** ソリッドカラーで塗りつぶしたパスに `setOpacity` を使用します。  
- **ファイルを保存するメソッドは？** `doc.save(...)` が XPS ファイルをディスクに書き込みます。  
- **ライセンスは必要ですか？** 本番環境で使用するには、一時ライセンスまたはフルライセンスが必要です。

## Visual Brush グリッドとは？
Visual Brush を使用すると、小さなビジュアル（グリッドパターン）を定義し、それを大きな領域全体にタイル状に配置できます。この方法は各線を個別に描画するよりもメモリ効率が高く、ピクセル単位で完璧に繰り返すことができます。

## このタスクに Aspose.Page を使用する理由
- **クロスプラットフォーム** – Java をサポートする任意の OS で動作します。  
- **高忠実度レンダリング** – 色、透明度、タイル配置を正確に制御できます。  
- **外部依存なし** – すべて Aspose.Page ライブラリで処理されます。

## 前提条件
Before we dive in, ensure you have:

- 基本的な Java プログラミングの知識。  
- Aspose.Page ライブラリがインストールされていること – [Aspose.Page for Java ドキュメント](https://reference.aspose.com/page/java/) からダウンロードできます。  
- 開発マシンに JDK 8 以降が設定されていること。

## パッケージのインポート
First, import the required classes so the compiler knows where to find the types we’ll use:

```java
import java.awt.geom.Point2D;
import java.awt.geom.Rectangle2D;
import com.aspose.xps.XpsCanvas;
import com.aspose.xps.XpsDocument;
import com.aspose.xps.XpsPath;
import com.aspose.xps.XpsPathGeometry;
import com.aspose.xps.XpsTileMode;
import com.aspose.xps.XpsVisualBrush;
```

## ステップバイステップガイド

### ステップ 1: プロジェクトのセットアップ
Create a new `XpsDocument` instance and point to the folder where you want the output file saved.

`XpsDocument` の新しいインスタンスを作成し、出力ファイルを保存したいフォルダーを指定します。

```java
String dataDir = "Your Document Directory";
XpsDocument doc = new XpsDocument();
```

### ステップ 2: マゼンタグリッドの Visual Brush を作成
We define a small magenta shape that will be tiled across the grid area.

グリッド領域全体にタイル状に配置する小さなマゼンタの形状を定義します。

```java
XpsCanvas visualCanvas = doc.createCanvas();
XpsPath visualPath = visualCanvas.addPath(doc.createPathGeometry("M 0,4 L 4,4 4,0 6,0 6,4 10,4 10,6 6,6 6,10 4,10 4,6 0,6 Z"));
visualPath.setFill(doc.createSolidColorBrush(doc.createColor(1f, .61f, 0.1f, 0.61f)));
```

### ステップ 3: グリッドブラシのジオメトリを定義
Set up the rectangular area that will receive the tiled visual.

タイル状のビジュアルを受け取る矩形領域を設定します。

```java
XpsPathGeometry pathGeometry = doc.createPathGeometry();
pathGeometry.addSegment(doc.createPolyLineSegment(new Point2D.Float[] {
    new Point2D.Float(240f, 5f),
    new Point2D.Float(240f, 310f),
    new Point2D.Float(0f, 310f)
}));
pathGeometry.get(0).setStartPoint(new Point2D.Float(0f, 5f));
```

### ステップ 4: ドキュメント用の新しいキャンバスを作成
Add a canvas to the document and position it where the grid will appear.

ドキュメントにキャンバスを追加し、グリッドが表示される位置に配置します。

```java
XpsCanvas canvas = doc.addCanvas();
canvas.setRenderTransform(doc.createMatrix(1f, 0f, 0f, 1f, 268f, 70f));
```

### ステップ 5: キャンバスにグリッドを追加
Apply the visual brush to the geometry, enabling tiling.

ジオメトリに Visual Brush を適用し、タイル配置を有効にします。

```java
XpsPath gridPath = canvas.addPath(pathGeometry);
gridPath.setFill(doc.createVisualBrush(visualCanvas,
    new Rectangle2D.Float(0f, 0f, 10f, 10f), new Rectangle2D.Float(0f, 0f, 10f, 10f)));
((XpsVisualBrush)gridPath.getFill()).setTileMode(XpsTileMode.Tile);
```

### ステップ 6: 透明な赤い長方形を追加 (セカンダリ機能)
Here we demonstrate **add transparent rectangle** on top of the grid for emphasis.

ここでは、強調のためにグリッドの上に **透明な長方形を追加** する方法を示します。

```java
XpsPath path = canvas.addPath(doc.createPathGeometry("M 10,10 L 228,10 228,100 10,100"));
path.setFill(doc.createSolidColorBrush(doc.createColor(1.0f, 0.0f, 0.0f)));
path.setOpacity(0.7f);
```

### ステップ 7: 生成された XPS ドキュメントを保存
Finally, write the document to disk—this is the **save XPS document** step.

最後に、ドキュメントをディスクに書き込みます—これが **XPS ドキュメントを保存** するステップです。

```java
doc.save(dataDir + "AddGrid_out.xps");
```

これらの手順に従えば、プログラムで生成された透明オーバーレイ付きのプロフェッショナルな見た目のグリッドが手に入ります。

## 一般的な問題とヒント

- **タイルサイズが不正**: ブラシに使用する `Rectangle2D` が意図した繰り返しサイズと一致していることを確認してください。そうでないとパターンが伸びてしまいます。  
- **透明度が適用されない**: 透明にしたいパスに対して `setOpacity` を呼び出すことを忘れないでください。ブラシ自体には影響しません。  
- **ファイルが保存されない**: `dataDir` が既存のフォルダーを指しているか、アプリケーションに書き込み権限があるか確認してください。

## よくある質問

**Q: Aspose.Page はプロフェッショナルなドキュメント生成に適していますか？**  
A: はい、Aspose.Page は Java で高品質な XPS および PDF を生成するために設計された堅牢なライブラリです。

**Q: Visual Brush を使用してグリッドの色をカスタマイズできますか？**  
A: もちろんです！ブラシの `setFill` 呼び出しで `createColor` のパラメータを任意の RGBA 値に変更すれば可能です。

**Q: Aspose.Page の追加サポートはどこで得られますか？**  
A: コミュニティの支援や公式の回答は [Aspose.Page フォーラム](https://forum.aspose.com/c/page/39) をご覧ください。

**Q: Aspose.Page の無料トライアルはありますか？**  
A: はい、購入前にすべての機能を試せる [無料トライアル](https://releases.aspose.com/) が利用できます。

**Q: テスト用の一時ライセンスはどう取得できますか？**  
A: 開発および評価に使用できる [一時ライセンス](https://purchase.aspose.com/temporary-license/) を取得してください。

---

**最終更新日:** 2025-12-18  
**テスト環境:** Aspose.Page for Java 23.12 (最新)  
**作者:** Aspose  

{{< /blocks/products/pf/tutorial-page-section >}}

{{< /blocks/products/pf/main-container >}}
{{< /blocks/products/pf/main-wrap-class >}}

{{< blocks/products/products-backtop-button >}}