---
title: Java XPSで四角形を追加する
linktitle: Java XPSで四角形を追加する
second_title: Aspose.Page Java API
description: Aspose.Page を使用して Java XPS に四角形を追加する方法を学びます。シームレスなドキュメント操作については、ステップバイステップのガイドに従ってください。 #JavaXPS #AsposePage
type: docs
weight: 11
url: /ja/java/xps-shapes/add-rectangle/
---
## 導入
Aspose.Page を使用して Java XPS に四角形を追加するためのこの包括的なガイドへようこそ。経験豊富な開発者でも、Java XPS を始めたばかりでも、このチュートリアルでは段階的な手順でプロセスを説明し、トピックを深く理解できるようにします。
## 前提条件
チュートリアルに入る前に、次の前提条件が満たされていることを確認してください。
- Java プログラミング言語の基本的な知識。
-  Aspose.Page ライブラリがインストールされています。そうでない場合は、からダウンロードできます。[Aspose.Page Java ドキュメント](https://reference.aspose.com/page/java/).
- 実用的な Java 開発環境。
## パッケージのインポート
まず、必要なパッケージを Java プロジェクトにインポートします。 Aspose.Page ライブラリがクラスパスに正しく追加されていることを確認してください。基本的な例を次に示します。
```java
import com.aspose.xps.XpsDocument;
import com.aspose.xps.XpsPath;
```
ここで、Java XPS に四角形を追加するために提供された例を複数の手順に分解してみましょう。
## ステップ 1: ドキュメント ディレクトリを設定する
```java
//ドキュメントディレクトリへのパス。
String dataDir = "Your Document Directory";
```
「Your Document Directory」を目的のディレクトリへのパスに置き換えます。
## ステップ 2: 新しい XPS ドキュメントを作成する
```java
//新しい XPS ドキュメントの作成
XpsDocument doc = new XpsDocument();
```
これにより、新しい XPS ドキュメントが初期化されます。
## ステップ 3: CMYK ソリッドカラーのストローク長方形を追加する
```java
//左下の CMYK (青) 単色ストローク長方形
XpsPath path = doc.addPath(doc.createPathGeometry("M 20,10 L 220,10 220,100 20,100 Z"));
path.setStroke(doc.createSolidColorBrush(
    doc.createColor(dataDir + "uswebuncoated.icc", 1.0f, 1.000f, 0.000f, 0.000f, 0.000f)));
path.setStrokeThickness(12f);
```
この手順では、CMYK 単色でストロークされた長方形を追加します。
## ステップ 4: 結果の XPS ドキュメントを保存する
```java
//結果の XPS ドキュメントを保存する
doc.save(dataDir + "AddRectangle_out.xps");
```
最後に、追加された四角形を含む変更された XPS ドキュメントを保存します。
必要に応じてパラメータを調整しながらこれらの手順を繰り返し、長方形をさらにカスタマイズします。
## 結論
おめでとう！ Aspose.Page を使用して Java XPS に四角形を追加する方法を学習しました。このチュートリアルは、XPS ドキュメント操作の取り組みのための強固な基盤を提供します。
## よくある質問
### 1 つの XPS ドキュメントに複数の四角形を追加できますか?
はい、チュートリアルで説明されている手順を繰り返すことで、必要なだけ四角形を追加できます。
### 長方形の色を変更するにはどうすればよいですか?
の色の値を変更します。`createColor`希望の色を実現する方法。
### Aspose.Page は複雑な XPS ドキュメント操作の処理に適していますか?
絶対に！ Aspose.Page は、さまざまな XPS ドキュメント タスクを処理するための堅牢な機能セットを提供します。
### 追加の例やサポートはどこで入手できますか?
を探索してください[Aspose.Page フォーラム](https://forum.aspose.com/c/page/39)さらに多くの例を確認し、コミュニティからの支援を求めてください。
### 購入する前に Aspose.Page を試してみることはできますか?
はい、探索できます[無料トライアル](https://releases.aspose.com/)Aspose.Page の機能を体験してください。