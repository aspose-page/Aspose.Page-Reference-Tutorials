---
title: Java XPSに垂直グラデーションを追加する
linktitle: Java XPSに垂直グラデーションを追加する
second_title: Aspose.Page Java API
description: Aspose.Page を使用して Java XPS ドキュメントに垂直グラデーションを追加する方法を学びます。視覚的な魅力を簡単に強化します。内部のステップバイステップガイド。
weight: 12
url: /ja/java/xps-gradient-addition/vertical/
---

{{< blocks/products/pf/main-wrap-class >}}
{{< blocks/products/pf/main-container >}}
{{< blocks/products/pf/tutorial-page-section >}}

# Java XPSに垂直グラデーションを追加する

## 導入
このチュートリアルでは、Aspose.Page for Java を使用して Java XPS に垂直グラデーションを追加する方法を検討します。 XPS ドキュメントにグラデーションを追加すると、コンテンツの視覚的な魅力が向上し、より魅力的で美しいものになります。
## 前提条件
チュートリアルに入る前に、次の前提条件が満たされていることを確認してください。
- 実用的な Java 開発環境。
-  Java ライブラリの Aspose.Page。からダウンロードできます[ここ](https://releases.aspose.com/page/java/).
- Java プログラミングの基本的な理解。
## パッケージのインポート
まず、Java プロジェクトに必要なパッケージをインポートします。 Aspose.Page for Java ライブラリがプロジェクトの依存関係に含まれていることを確認してください。
```java
import com.aspose.xps.XpsDocument;
import com.aspose.xps.XpsGradientBrush;
import com.aspose.xps.XpsGradientStop;
import com.aspose.xps.XpsPath;
import java.awt.geom.Point2D;
import java.util.LinkedList;
import java.util.List;
//ドキュメントディレクトリへのパス。
String dataDir = "Your Document Directory";
        
// Java 用 Aspose.Page をインポート
```
## ステップ 1: ドキュメントを初期化する
まず、XPS ドキュメントを初期化します。これにより、パスやグラデーションなどの要素をドキュメントに追加するための基礎が設定されます。
```java
//ドキュメントの初期化
XpsDocument doc = new XpsDocument();
```
## ステップ 2: 垂直グラデーションのあるパスを作成する
それでは、垂直方向のグラデーションのあるパスを作成してみましょう。これには、パス ジオメトリの定義とグラデーションの停止点の指定が含まれます。
```java
//ジオメトリを使用してパスを作成する
XpsPath path = doc.addPath(doc.createPathGeometry("M 30,20 l 258.24,0 0,56.64 -258.24,0 Z"));
//垂直方向のグラデーションの停止点を定義する
List<XpsGradientStop> stops = new LinkedList<XpsGradientStop>();
stops.add(doc.createGradientStop(doc.createColor(253, 255, 12, 0), 0f));
stops.add(doc.createGradientStop(doc.createColor(252, 255, 154, 0), 0.359375f));
stops.add(doc.createGradientStop(doc.createColor(252, 255, 56, 0), 0.424805f));
stops.add(doc.createGradientStop(doc.createColor(253, 255, 229, 0), 0.879883f));
stops.add(doc.createGradientStop(doc.createColor(252, 255, 255, 234), 1f));
//パスに垂直グラデーションを適用します
path.setFill(doc.createLinearGradientBrush(new Point2D.Float(10f, 110f), new Point2D.Float(10f, 200f)));
((XpsGradientBrush)path.getFill()).getGradientStops().addAll(stops);
```
## ステップ 3: ドキュメントを保存する
最後に、垂直グラデーションを追加した XPS ドキュメントを目的のディレクトリに保存します。
```java
//文書を保存する
doc.save(dataDir + "VerticalGradient.xps");
```
おめでとう！ Aspose.Page を使用して、Java XPS ドキュメントに垂直グラデーションを正常に追加しました。
## 結論
XPS ドキュメントをグラデーションで強化すると、見た目の魅力が大幅に向上します。 Aspose.Page for Java はこのプロセスを簡素化し、魅力的なドキュメントを簡単に作成できるようにします。

### よくある質問
### Aspose.Page for Java を商用プロジェクトで使用できますか?
はい、Aspose.Page for Java は商用利用が可能です。購入できます[ここ](https://purchase.aspose.com/buy).
### Aspose.Page for Java に利用できる無料トライアルはありますか?
はい、無料トライアルにアクセスできます[ここ](https://releases.aspose.com/).
### Aspose.Page for Java のドキュメントはどこで見つけられますか?
ドキュメントは利用可能です[ここ](https://reference.aspose.com/page/java/).
### Aspose.Page for Java の一時ライセンスを取得するにはどうすればよいですか?
仮免許を取得する[ここ](https://purchase.aspose.com/temporary-license/).
### 助けが必要ですか、それとも質問がありますか?
 Aspose.Page コミュニティにアクセスしてください[フォーラム](https://forum.aspose.com/c/page/39).
{{< /blocks/products/pf/tutorial-page-section >}}

{{< /blocks/products/pf/main-container >}}
{{< /blocks/products/pf/main-wrap-class >}}

{{< blocks/products/products-backtop-button >}}
