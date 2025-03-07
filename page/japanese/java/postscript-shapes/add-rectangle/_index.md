---
title: Java PostScript のカスタマイズ - Aspose.Page を使用した四角形の追加
linktitle: Java PostScriptで四角形を追加
second_title: Aspose.Page Java API
description: Aspose.Page for Java を使用して Java PostScript ドキュメントに鮮やかな四角形を追加するためのステップバイステップ ガイドをご覧ください。ドキュメントのカスタマイズを簡単に強化できます。
weight: 11
url: /ja/java/postscript-shapes/add-rectangle/
---

{{< blocks/products/pf/main-wrap-class >}}
{{< blocks/products/pf/main-container >}}
{{< blocks/products/pf/tutorial-page-section >}}

# Java PostScript のカスタマイズ - Aspose.Page を使用した四角形の追加

## 導入
Java PostScript ドキュメントを鮮やかな四角形で強化したいと考えていますか?これ以上探さない！このステップバイステップ ガイドでは、Aspose.Page for Java を使用して PostScript ドキュメントに四角形を追加する方法を説明します。 Aspose.Page は、PostScript ファイルを操作するための堅牢な機能を提供する強力なライブラリであり、ドキュメントの操作やカスタマイズを求める開発者にとって理想的な選択肢となります。
## 前提条件
チュートリアルに入る前に、次の前提条件が満たされていることを確認してください。
- Java プログラミングの基本的な理解。
-  Aspose.Page for Java ライブラリがインストールされています。そうでない場合は、からダウンロードしてください。[Aspose.Page for Java ドキュメント](https://reference.aspose.com/page/java/).
- マシン上にセットアップされた Java 開発環境。
## パッケージのインポート
Java プロジェクトで、必要なパッケージをインポートすることから始めます。
```java
import java.awt.BasicStroke;
import java.awt.Color;
import java.awt.geom.Rectangle2D;
import java.io.FileOutputStream;
import com.aspose.eps.PsDocument;
import com.aspose.eps.device.PsSaveOptions;
```
## チュートリアル: Java PostScript での四角形の追加
## ステップ 1: 四角形を塗りつぶすためのペイントを設定する
```java
//ドキュメントディレクトリへのパス。
String dataDir = "Your Document Directory";
//PostScript ドキュメントの出力ストリームを作成する
FileOutputStream outPsStream = new FileOutputStream(dataDir + "AddRectangle_outPS.ps");
//A4サイズで保存オプションを作成する
PsSaveOptions options = new PsSaveOptions();
//ページを開いた状態で新しい PS ドキュメントを作成します
PsDocument document = new PsDocument(outPsStream, options, false);
//長方形を塗りつぶすペイントを設定します
document.setPaint(Color.ORANGE);        
//最初の長方形を塗りつぶします
document.fill(new Rectangle2D.Float(250, 100, 150, 100));
```
## ステップ 2: 長方形をストロークするためのペイントを設定する
```java
//長方形をストロークするためのペイントを設定する
document.setPaint(Color.RED);
//設定ストローク
document.setStroke(new BasicStroke(3));
// 番目の長方形をストローク (輪郭)
document.draw(new Rectangle2D.Float(250, 300, 150, 100));
```
## ステップ 3: 現在のページを閉じてドキュメントを保存する
```java
//現在のページを閉じる
document.closePage();
//文書を保存する
document.save();
```
おめでとう！ Aspose.Page を使用して、鮮やかな四角形を Java PostScript ドキュメントに追加することに成功しました。
## 結論
このチュートリアルでは、Aspose.Page for Java を使用して、Java PostScript ドキュメントを四角形で強化するプロセスについて説明しました。この強力なライブラリは、ドキュメントを簡単にカスタマイズして操作したいと考えている開発者に可能性の世界を開きます。
ドキュメントを視覚的に魅力的なものにするために、さまざまな形や色を楽しんで試してください。
## よくある質問

### Aspose.Page for Java を他のプログラミング言語で使用できますか?
Aspose.Page は主に Java をサポートしていますが、他の言語でも同様のライブラリが利用可能です。
### Aspose.Page for Java の試用版は利用可能ですか?
はい、次のコマンドを使用して、Aspose.Page for Java の機能を探索できます。[無料試用版](https://releases.aspose.com/).
### 追加のヘルプやディスカッションはどこで見つけられますか?
訪問[Aspose.Page フォーラム](https://forum.aspose.com/c/page/39)コミュニティと関わり、支援を受けることができます。
### Aspose.Page for Java の一時ライセンスを取得するにはどうすればよいですか?
仮免許を取得する[ここ](https://purchase.aspose.com/temporary-license/).
### Aspose.Page for Java のライセンス版はどこで購入できますか?
ライセンス版を購入する[ここ](https://purchase.aspose.com/buy).
{{< /blocks/products/pf/tutorial-page-section >}}

{{< /blocks/products/pf/main-container >}}
{{< /blocks/products/pf/main-wrap-class >}}

{{< blocks/products/products-backtop-button >}}
