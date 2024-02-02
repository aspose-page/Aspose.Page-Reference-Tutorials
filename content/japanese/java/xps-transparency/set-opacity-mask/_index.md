---
title: Java XPS で不透明マスクを設定する
linktitle: Java XPS で不透明マスクを設定する
second_title: Aspose.Page Java API
description: Aspose.Page を使用して Java XPS で不透明マスクを設定する能力を発見してください。視覚的に強化されたドキュメント エクスペリエンスについては、ステップバイステップ ガイドに従ってください。
type: docs
weight: 11
url: /ja/java/xps-transparency/set-opacity-mask/
---
## 導入
Aspose.Page を使用して Java XPS で不透明マスクを設定するための包括的なガイドへようこそ。このチュートリアルでは、Aspose.Page for Java の強力な機能を使用して、XPS ドキュメントを作成し、キャンバスを追加し、長方形に不透明マスクを適用するプロセスを説明します。
## 前提条件
このチュートリアルに入る前に、次のものが揃っていることを確認してください。
- Java プログラミングの基本的な理解。
-  Aspose.Page for Java ライブラリがインストールされています。ダウンロードできます[ここ](https://releases.aspose.com/page/java/).
-  Aspose.Page の有効なライセンス。持っていない場合は、一時ライセンスを取得できます[ここ](https://purchase.aspose.com/temporary-license/).
- Java アプリケーションを実行するためにセットアップされた開発環境。
## パッケージのインポート
まず、必要なパッケージを Java プロジェクトにインポートします。 Aspose.Page ライブラリが適切に統合されていることを確認してください。以下はガイドとなるスニペットです。
```java
import com.aspose.xps.XpsCanvas;
import com.aspose.xps.XpsDocument;
import com.aspose.xps.XpsImageBrush;
import com.aspose.xps.XpsPath;
import com.aspose.xps.XpsTileMode;
import java.awt.geom.Rectangle2D;
```
ここで、サンプル コードを複数のステップに分割してみましょう。
## ステップ 1: 新しい XPS ドキュメントを作成する
```java
//新しい XPS ドキュメントを作成する
XpsDocument doc = new XpsDocument();
```
## ステップ 2: キャンバスを追加する
```java
//新しいキャンバス
XpsCanvas canvas = doc.addCanvas();
```
## ステップ 3: 不透明マスクを使用して長方形を追加する
```java
//ImageBrush で不透明度をマスクした左中央の長方形
XpsPath path = canvas.addPath(doc.createPathGeometry("M 10,180 L 228,180 228,285 10,285"));
path.setFill(doc.createSolidColorBrush(doc.createColor(1.0f, 0.0f, 0.0f)));
```
## ステップ 4: ImageBrush で不透明マスクを設定する
```java
path.setOpacityMask(doc.createImageBrush(dataDir +  "R08SY_NN.tif", 
                    new Rectangle2D.Float(0f, 0f, 128f, 192f), new Rectangle2D.Float(0f, 0f, 64f, 96f)));
((XpsImageBrush)path.getOpacityMask()).setTileMode(XpsTileMode.Tile);
```
## ステップ 5: 結果の XPS ドキュメントを保存する
```java
//結果の XPS ドキュメントを保存する
doc.save(dataDir + "OpacityMask_out.xps"); 
```
Aspose.Page を使用して不透明マスクを Java XPS ドキュメントに組み込むには、次の手順を注意深く実行してください。
## 結論
おめでとう！ Aspose.Page を使用して Java XPS で不透明マスクを設定する方法を学習しました。この機能は、ドキュメントに視覚的な豊かさのレイヤーを追加し、ドキュメントをより魅力的でダイナミックなものにします。
## よくある質問
### Aspose.Page はすべての Java 開発環境と互換性がありますか?
はい、Aspose.Page はさまざまな Java 開発環境とシームレスに動作するように設計されています。
### Aspose.Page はライセンスなしで使用できますか?
Aspose.Page はライセンスなしで使用できますが、あらゆる機能とサポートを利用するにはライセンスを取得することをお勧めします。
### 体験版に制限はありますか?
試用版にはいくつかの機能制限がある場合があります。詳細についてはドキュメントを確認することをお勧めします。
### Aspose.Page のサポートを受けるにはどうすればよいですか?
訪問できます。[Aspose.Page フォーラム](https://forum.aspose.com/c/page/39)コミュニティ サポートを利用するか、プレミアム サポートのライセンスを購入してください。
### Aspose.Page には返金保証はありますか?
を参照してください。[購入ページ](https://purchase.aspose.com/buy)返金ポリシーについては、こちらをご覧ください。