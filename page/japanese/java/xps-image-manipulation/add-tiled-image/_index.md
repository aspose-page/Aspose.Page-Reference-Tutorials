---
title: Java XPS でタイル化されたイメージを追加する
linktitle: Java XPS でタイル化されたイメージを追加する
second_title: Aspose.Page Java API
description: Aspose.Page を使用してシームレスな Java XPS ドキュメント操作を体験してください。このステップバイステップのガイドを使用して、タイル画像を簡単に追加する方法を学びましょう。
weight: 11
url: /ja/java/xps-image-manipulation/add-tiled-image/
---

{{< blocks/products/pf/main-wrap-class >}}
{{< blocks/products/pf/main-container >}}
{{< blocks/products/pf/tutorial-page-section >}}

# Java XPS でタイル化されたイメージを追加する

## 導入
Java 開発の動的な世界では、効率的なドキュメントの操作と作成に対するニーズがますます高まっています。 Aspose.Page for Java は強力なツールとして登場し、開発者に XPS ドキュメントをシームレスに操作する機能を提供します。このチュートリアルでは、タイル化されたイメージを Java XPS ドキュメントに追加するという特定のタスクに焦点を当てます。
## 前提条件
チュートリアルに入る前に、次の前提条件が満たされていることを確認してください。
1. Java Development Kit (JDK): システムに JDK がインストールされていることを確認してください。
2.  Aspose.Page for Java: 次の場所から Aspose.Page for Java をダウンロードしてインストールします。[Webサイト](https://releases.aspose.com/page/java/).
3. ドキュメント ディレクトリ: XPS ドキュメントを保存するディレクトリを選択または作成します。
## パッケージのインポート
Java プロジェクトで、Aspose.Page 機能を利用するために必要なパッケージをインポートします。
```java
import com.aspose.xps.XpsDocument;
import com.aspose.xps.XpsImageBrush;
import com.aspose.xps.XpsPath;
import com.aspose.xps.XpsTileMode;
import java.awt.geom.Rectangle2D;
```
ここで、タイル化されたイメージを Java XPS ドキュメントに追加するプロセスを、明確で管理しやすい手順に分割してみましょう。
## ステップ 1: プロジェクトをセットアップする
まず Java プロジェクトを設定し、Aspose.Page for Java が適切に統合されていることを確認します。
## ステップ 2: XPS ドキュメントの作成
次のコードを使用して、新しい XPS ドキュメントを初期化します。
```java
//ドキュメントディレクトリへのパス。
String dataDir = "Your Document Directory";
//新しい XPS ドキュメントの作成
XpsDocument doc = new XpsDocument();
```
## ステップ 3: タイル化されたイメージのパスを定義する
XPS ドキュメントに追加するタイル化されたイメージへのパスを指定します。
## ステップ 4: タイル画像を追加する
以下のコード スニペットを利用して、タイル化されたイメージを XPS ドキュメントに追加します。
```java
//タイル画像
//右上下の ImageBrush で塗りつぶされた四角形
XpsPath path = doc.addPath(doc.createPathGeometry("M 10,160 L 228,160 228,305 10,305"));
path.setFill(doc.createImageBrush(dataDir +  "R08LN_NN.jpg",
                                new Rectangle2D.Float(0f, 0f, 128f, 96f), new Rectangle2D.Float(0f, 0f, 64f, 48f)));
((XpsImageBrush)path.getFill()).setTileMode(XpsTileMode.Tile);
path.getFill().setOpacity(0.5f);
```
## ステップ 5: ドキュメントを保存する
最後に、以下のコードを使用して、結果の XPS ドキュメントを保存します。
```java
//結果の XPS ドキュメントを保存する
doc.save(dataDir + "AddTiledImage_out.xps"); 
```
これらの手順を繰り返して、Aspose.Page を使用してタイル化されたイメージを Java XPS ドキュメントに簡単に組み込みます。
## 結論
Aspose.Page for Java は、XPS ドキュメントの操作プロセスを合理化し、開発者にドキュメント操作のための効率的なソリューションを提供します。このステップバイステップのガイドに従うことで、タイル化されたイメージを Java XPS ドキュメントに簡単に追加できます。

## よくある質問
### Aspose.Page はすべての Java バージョンと互換性がありますか?
 Aspose.Page は、さまざまな Java バージョンで動作するように設計されています。ドキュメントを確認して互換性を確認してください[ここ](https://reference.aspose.com/page/java/).
### Aspose.Page を商用プロジェクトに使用できますか?
はい、Aspose.Page は商用ライセンスを提供しています。購入してください[ここ](https://purchase.aspose.com/buy).
### 無料トライアルはありますか?
はい、無料トライアルで Aspose.Page の機能を試してください[ここ](https://releases.aspose.com/).
### コミュニティのサポートやディスカッションはどこで見つけられますか?
 Aspose.Page コミュニティに参加してください。[フォーラム](https://forum.aspose.com/c/page/39).
### Aspose.Page の一時ライセンスを取得するにはどうすればよいですか?
仮免許を取得する[ここ](https://purchase.aspose.com/temporary-license/).
{{< /blocks/products/pf/tutorial-page-section >}}

{{< /blocks/products/pf/main-container >}}
{{< /blocks/products/pf/main-wrap-class >}}

{{< blocks/products/products-backtop-button >}}
