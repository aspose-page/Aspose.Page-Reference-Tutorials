---
date: 2025-12-25
description: Aspose.Page を使用して Java XPS に垂直グラデーションを追加する方法を学びましょう。このステップバイステップガイドに従って、ドキュメントの視覚的魅力を高めてください。
linktitle: How to Add Vertical Gradient in Java XPS
second_title: Aspose.Page Java API
title: Java XPSで垂直グラデーションを追加する方法
url: /ja/java/xps-gradient-addition/vertical/
weight: 12
---

{{< blocks/products/pf/main-wrap-class >}}
{{< blocks/products/pf/main-container >}}
{{< blocks/products/pf/tutorial-page-section >}}

# Java XPS で垂直グラデーションを追加する方法

## はじめに
このチュートリアルでは、Java で作業する際に XPS ドキュメントへ **垂直グラデーションを追加する方法** を学びます。垂直グラデーションを適用すると、レポート、請求書、または任意の印刷可能コンテンツの視覚的インパクトが劇的に向上します。強力な Aspose.Page for Java ライブラリを使用して、プロジェクトのセットアップから最終 XPS ファイルの保存まで、各ステップを順に解説します。

## クイック回答
- **垂直グラデーションは何をするのですか？** 形状の上部から下部へ滑らかな色の遷移を作ります。  
- **必要なライブラリは？** Aspose.Page for Java（公式サイトからダウンロード可能）。  
- **ライセンスは必要ですか？** 開発には無料トライアルで動作しますが、本番環境では商用ライセンスが必要です。  
- **Java 8+ と互換性がありますか？** はい、API は Java 8 以降をサポートしています。  
- **実装にどれくらい時間がかかりますか？** 環境設定後、通常は 10 分未満です。

## 前提条件
コードに入る前に、以下が揃っていることを確認してください：

- JDK 8 以上の動作する Java 開発環境。  
- Aspose.Page for Java ライブラリ。ダウンロードは [here](https://releases.aspose.com/page/java/) から。  
- Java プログラミングの基本概念の理解。  

## パッケージのインポート
Java プロジェクトに必要なパッケージをインポートします。Aspose.Page for Java ライブラリがプロジェクトのクラスパスに追加されていることを確認してください。

```java
import com.aspose.xps.XpsDocument;
import com.aspose.xps.XpsGradientBrush;
import com.aspose.xps.XpsGradientStop;
import com.aspose.xps.XpsPath;
import java.awt.geom.Point2D;
import java.util.LinkedList;
import java.util.List;
// The path to the documents directory.
String dataDir = "Your Document Directory";
        
// Import Aspose.Page for Java
```

## ステップ 1: ドキュメントの初期化
新しい XPS ドキュメントを作成します。このオブジェクトは、後で追加するすべての描画要素を保持します。

```java
// Initialize document
XpsDocument doc = new XpsDocument();
```

## ステップ 2: 垂直グラデーション付きパスの作成
次に、矩形パスを定義し、垂直方向の線形グラデーションを適用します。グラデーションストップは、色とそれらの垂直軸上の位置を決定します。

```java
// Create a path with geometry
XpsPath path = doc.addPath(doc.createPathGeometry("M 30,20 l 258.24,0 0,56.64 -258.24,0 Z"));
// Define vertical gradient stops
List<XpsGradientStop> stops = new LinkedList<XpsGradientStop>();
stops.add(doc.createGradientStop(doc.createColor(253, 255, 12, 0), 0f));
stops.add(doc.createGradientStop(doc.createColor(252, 255, 154, 0), 0.359375f));
stops.add(doc.createGradientStop(doc.createColor(252, 255, 56, 0), 0.424805f));
stops.add(doc.createGradientStop(doc.createColor(253, 255, 229, 0), 0.879883f));
stops.add(doc.createGradientStop(doc.createColor(252, 255, 255, 234), 1f));
// Apply the vertical gradient to the path
path.setFill(doc.createLinearGradientBrush(new Point2D.Float(10f, 110f), new Point2D.Float(10f, 200f)));
((XpsGradientBrush)path.getFill()).getGradientStops().addAll(stops);
```

## ステップ 3: ドキュメントの保存
最後に、XPS ファイルを書き出してディスクに保存します。生成されたファイルには、定義した垂直グラデーションで塗りつぶされた矩形が含まれます。

```java
// Save the document
doc.save(dataDir + "VerticalGradient.xps");
```

おめでとうございます！Aspose.Page を使用して、Java XPS ドキュメントに **垂直グラデーションを追加する方法** を習得しました。

## なぜ垂直グラデーションを使用するのか？
- **美観の向上:** グラデーションは深みとモダンな印象を静的な形状にもたらします。  
- **ブランドの一貫性:** 企業カラーをページ全体に滑らかに適用できます。  
- **簡単なカスタマイズ:** グラフィックを作り直すことなく、色やストップ位置を変更可能です。

## 一般的な問題とトラブルシューティング
- **グラデーションが表示されない:** `LinearGradientBrush` の開始点と終了点が垂直方向に正しく設定されているか確認してください。  
- **ファイルが保存されない:** `dataDir` が書き込み可能なフォルダーを指しているか、書き込み権限があるか確認してください。  
- **ライブラリが見つからない:** Aspose.Page の JAR がプロジェクトのビルドパスに含まれているか再確認してください。

## よくある質問

**Q: Aspose.Page for Java を商用プロジェクトで使用できますか？**  
A: はい、Aspose.Page for Java は商用利用が可能です。購入は [here](https://purchase.aspose.com/buy) から。

**Q: Aspose.Page for Java の無料トライアルはありますか？**  
A: はい、無料トライアルは [here](https://releases.aspose.com/) で入手できます。

**Q: Aspose.Page for Java のドキュメントはどこで見つけられますか？**  
A: ドキュメントは [here](https://reference.aspose.com/page/java/) にあります。

**Q: Aspose.Page for Java の一時ライセンスはどう取得できますか？**  
A: 一時ライセンスは [here](https://purchase.aspose.com/temporary-license/) から取得できます。

**Q: サポートが必要、または質問がありますか？**  
A: Aspose.Page コミュニティの [forum](https://forum.aspose.com/c/page/39) をご利用ください。

---

**最終更新日:** 2025-12-25  
**テスト環境:** Aspose.Page for Java 24.12（執筆時点での最新バージョン）  
**作者:** Aspose  

{{< /blocks/products/pf/tutorial-page-section >}}

{{< /blocks/products/pf/main-container >}}
{{< /blocks/products/pf/main-wrap-class >}}

{{< blocks/products/products-backtop-button >}}