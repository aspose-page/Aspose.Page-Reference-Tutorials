---
title: Aspose.Page を使用して放射状グラデーション楕円を追加する
linktitle: Java XPSに楕円を追加する
second_title: Aspose.Page Java API
description: Aspose.Page for Java を使用して Java XPS に放射状グラデーション ストローク楕円を追加するためのステップバイステップ ガイドをご覧ください。ドキュメント作成を簡単に強化します。
weight: 10
url: /ja/java/xps-shapes/add-ellipse/
---

{{< blocks/products/pf/main-wrap-class >}}
{{< blocks/products/pf/main-container >}}
{{< blocks/products/pf/tutorial-page-section >}}

# Aspose.Page を使用して放射状グラデーション楕円を追加する

## 導入
Aspose.Page for Java を使用して Java XPS に楕円を追加するためのステップバイステップ ガイドへようこそ。 Aspose.Page は、開発者が XPS ドキュメントを簡単に操作できるようにする強力な Java ライブラリです。このチュートリアルでは、放射状のグラデーション ストローク楕円を作成し、それを XPS ドキュメントとして保存するプロセスを説明します。
## 前提条件
始める前に、次の前提条件が満たされていることを確認してください。
- Java Development Kit (JDK) がマシンにインストールされています。
-  Java ライブラリ用の Aspose.Page がダウンロードされました。がんばって[ここ](https://releases.aspose.com/page/java/).
- Java コードを作成および実行するための任意のコード エディター (Eclipse、IntelliJ など)。
## パッケージのインポート
Aspose.Page を使用するために必要なパッケージが Java プロジェクトにインポートされていることを確認してください。次のインポート ステートメントを Java ファイルの先頭に追加します。
```java
import java.awt.geom.Point2D;
import java.util.LinkedList;
import java.util.List;
import com.aspose.xps.XpsCanvas;
import com.aspose.xps.XpsDocument;
import com.aspose.xps.XpsGradientBrush;
import com.aspose.xps.XpsGradientStop;
import com.aspose.xps.XpsPath;
import com.aspose.xps.XpsPathGeometry;
import com.aspose.xps.XpsSpreadMethod;
```
## ステップ 1: ドキュメント ディレクトリを設定する
XPS ドキュメントが保存されるドキュメント ディレクトリへのパスを定義します。
```java
String dataDir = "Your Document Directory";
```
## ステップ 2: XPS ドキュメントの作成
次のコードを使用して、新しい XPS ドキュメントを初期化します。
```java
XpsDocument doc = new XpsDocument();
```
## ステップ 3: 放射状グラデーション停止点を定義する
放射状グラデーション ストローク楕円のグラデーション停止点のリストを作成します。
```java
List<XpsGradientStop> stops = new LinkedList<>();
stops.add(doc.createGradientStop(doc.createColor(0, 0, 255), 0f));
stops.add(doc.createGradientStop(doc.createColor(255, 0, 0), .25f));
stops.add(doc.createGradientStop(doc.createColor(0, 255, 0), .5f));
stops.add(doc.createGradientStop(doc.createColor(255, 255, 0), .75f));
stops.add(doc.createGradientStop(doc.createColor(255, 0, 0), 1f));
```
## ステップ 4: パス ジオメトリの作成
パス ジオメトリを使用して放射状グラデーション ストローク楕円を定義します。
```java
XpsPathGeometry pathGeometry = doc.createPathGeometry("M 20,250 A 100,50 0 1 1 220,250 100,50 0 1 1 20,250");
```
## ステップ 5: キャンバスとパスを追加する
新しいキャンバスをドキュメントに追加し、定義されたジオメトリを含むパスを追加します。
```java
XpsCanvas canvas = doc.addCanvas();
XpsPath path = canvas.addPath(pathGeometry);
```
## ステップ 6: ストロークとグラデーションを設定する
放射状グラデーション ブラシを使用してパスのストロークを構成します。
```java
path.setStroke(doc.createRadialGradientBrush(new Point2D.Float(575f, 125f), new Point2D.Float(575f, 100f), 75f, 50f));
((XpsGradientBrush)path.getStroke()).setSpreadMethod(XpsSpreadMethod.Reflect);
((XpsGradientBrush)path.getStroke()).getGradientStops().addAll(stops);
stops.clear();
```
## ステップ 7: ストロークの太さを設定する
パスのストロークの太さを指定します。
```java
path.setStrokeThickness(12f);
```
## ステップ 8: ドキュメントを保存する
結果の XPS ドキュメントを保存します。
```java
doc.save(dataDir + "AddEllipse_out.xps");
```
おめでとう！ Aspose.Page for Java を使用して、Java XPS に放射状グラデーション ストローク楕円を正常に追加しました。
## 結論
このチュートリアルでは、視覚的に魅力的な放射状グラデーション ストロークの楕円を含む XPS ドキュメントを作成する手順を説明しました。 Aspose.Page for Java は、XPS ドキュメントの操作を簡素化し、開発者に強力なツールセットを提供します。
## よくある質問
### Aspose.Page for Java を他の Java ライブラリと一緒に使用できますか?
はい、Aspose.Page for Java は他の Java ライブラリとシームレスに統合できます。
### Aspose.Page は大規模なドキュメント処理に適していますか?
絶対に！ Aspose.Page は、大規模なドキュメント処理を効率的に処理できるように設計されています。
### Aspose.Page for Java のその他のチュートリアルと例はどこで見つけられますか?
訪問[Aspose.Page for Java ドキュメント](https://reference.aspose.com/page/java/)包括的なチュートリアルと例を参照してください。
### Aspose.Page for Java の一時ライセンスを取得するにはどうすればよいですか?
仮免許が取得できる[ここ](https://purchase.aspose.com/temporary-license/).
### Aspose.Page ディスカッションのためのコミュニティ フォーラムはありますか?
はい、参加してください[Aspose.Page コミュニティ フォーラム](https://forum.aspose.com/c/page/39)他の開発者と交流し、支援を受けるため。
{{< /blocks/products/pf/tutorial-page-section >}}

{{< /blocks/products/pf/main-container >}}
{{< /blocks/products/pf/main-wrap-class >}}

{{< blocks/products/products-backtop-button >}}
