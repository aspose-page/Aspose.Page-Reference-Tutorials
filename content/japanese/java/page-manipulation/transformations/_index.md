---
title: Aspose.Page を使用した高度な変換ガイド
linktitle: Java ページ操作における変換
second_title: Aspose.Page Java API
description: Aspose.Page for Java を使用して Java で高度なページ変換を実行する方法を学びます。強力な操作機能で Java アプリケーションを強化します。
type: docs
weight: 11
url: /ja/java/page-manipulation/transformations/
---
## 導入
Aspose.Page for Java の強力な機能を利用して Java ページ操作で変換を実行するための包括的なガイドへようこそ。 Aspose.Page は、開発者がさまざまなページ操作タスクを効率的に処理できるようにする多用途の Java ライブラリです。
## 前提条件
ステップバイステップのガイドに進む前に、次の前提条件が満たされていることを確認してください。
- Java プログラミングの基本的な知識。
-  Aspose.Page for Java ライブラリがインストールされています。からダウンロードできます。[Aspose.Page for Java ドキュメント](https://reference.aspose.com/page/java/).
- マシン上にセットアップされた Java 統合開発環境 (IDE)。
## パッケージのインポート
Java プロジェクトで、Aspose.Page for Java を利用するために必要なパッケージをインポートします。
```java
import java.awt.Color;
import java.awt.Shape;
import java.awt.geom.AffineTransform;
import java.awt.geom.Rectangle2D;
import java.io.FileOutputStream;
import com.aspose.eps.PsDocument;
import com.aspose.eps.device.PsSaveOptions;

```
## 例 1: 変換なし
```java
//ドキュメントディレクトリへのパス。
String dataDir = "Your Document Directory";
//PostScript ドキュメントの出力ストリームを作成する
FileOutputStream outPsStream = new FileOutputStream(dataDir + "Tranformations_outPS.ps");
//A4サイズで保存オプションを作成する
PsSaveOptions options = new PsSaveOptions();
//ページを開いた状態で新しい PS ドキュメントを作成します
PsDocument document = new PsDocument(outPsStream, options, false);
//長方形を作成する
Shape shape = new Rectangle2D.Float(0, 0, 150, 100);
//上位レベルのグラフィックス状態にペイントを設定します
document.setPaint(Color.ORANGE);
//最初の長方形を変形せずに塗りつぶします。
document.fill(shape);
//現在のページを閉じる
document.closePage();
//文書を保存する
document.save();
```
## 例 2: 翻訳
```java
//グラフィックス状態を保存して変換後に戻す
document.writeGraphicsSave();
//現在のグラフィックス状態を右に 250 ずらします
document.translate(250, 0);
//現在のグラフィックス状態でペイントを設定する
document.setPaint(Color.BLUE);
// 番目の長方形を移動変換で塗りつぶします。
document.fill(shape);
//グラフィックス状態を以前の (上位) レベルに復元します
document.writeGraphicsRestore();
```
## 例 3: スケーリング
```java
//グラフィックス状態を保存して変換後に戻す
document.writeGraphicsSave();
//現在のグラフィックス状態を X 軸で 0.5、Y 軸で 0.75f にスケールします。
document.scale(0.5f, 0.75f);
//現在のグラフィックス状態でペイントを設定する
document.setPaint(Color.RED);
// 3 番目の長方形をスケール変換で塗りつぶします。
document.fill(shape);
//グラフィックス状態を以前の (上位) レベルに復元します
document.writeGraphicsRestore();
```
提供された Java コード スニペットに従って、回転、せん断、および複雑な変換の例を使用してパターンを続けます。
## 結論
このチュートリアルでは、Aspose.Page for Java を使用した Java ページ操作のさまざまな変換を検討しました。これらの例に従うことで、高度なページ操作機能を使用して Java アプリケーションを強化できます。
## よくある質問
### Aspose.Page for Java を他のドキュメント形式に使用できますか?
Aspose.Page は主に、PostScript および XPS 形式のページ操作に焦点を当てています。
### Aspose.Page for Java のその他の例やドキュメントはどこで見つけられますか?
訪問[Aspose.Page for Java ドキュメント](https://reference.aspose.com/page/java/)包括的な情報については。
### Aspose.Page for Java に利用できる無料トライアルはありますか?
はい、無料トライアルにアクセスできます[ここ](https://releases.aspose.com/).
### Aspose.Page for Java の一時ライセンスを取得するにはどうすればよいですか?
仮免許を取得する[ここ](https://purchase.aspose.com/temporary-license/).
### Aspose.Page for Java についてコミュニティ サポートを求めたり、質問したりするにはどこで行えばよいですか?
訪問[Aspose.Page for Java フォーラム](https://forum.aspose.com/c/page/39)コミュニティのディスカッション用に。