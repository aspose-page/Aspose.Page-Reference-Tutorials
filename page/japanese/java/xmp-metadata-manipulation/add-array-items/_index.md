---
title: Java を使用して XMP メタデータに配列項目を追加する
linktitle: Java を使用して XMP メタデータに配列項目を追加する
second_title: Aspose.Page Java API
description: Aspose.Page for Java を使用して EPS ファイルを拡張します。配列項目を XMP メタデータに簡単に追加する方法を学びます。今すぐステップバイステップガイドに従ってください。
weight: 10
url: /ja/java/xmp-metadata-manipulation/add-array-items/
---

{{< blocks/products/pf/main-wrap-class >}}
{{< blocks/products/pf/main-container >}}
{{< blocks/products/pf/tutorial-page-section >}}

# Java を使用して XMP メタデータに配列項目を追加する

## 導入
Aspose.Page for Java を使用して XMP メタデータに配列項目を追加するためのステップバイステップ ガイドへようこそ。 Aspose.Page は、EPS ファイルを含むさまざまなドキュメント形式の操作と作業を可能にする強力な Java ライブラリです。このチュートリアルでは、Java を使用して XMP メタデータに配列項目を追加するという特定のタスクに焦点を当てます。
## 前提条件
チュートリアルに入る前に、次の前提条件を満たしていることを確認してください。
- Aspose.Page for Java ライブラリがインストールされています。
- Java プログラミングの基本的な理解。
- 既存の XMP メタデータまたは PS メタデータ コメントを含む有効な EPS ファイル。
## パッケージのインポート
まず、Aspose.Page を操作するために必要なパッケージをインポートする必要があります。 Java ファイルの先頭に次の行を含めます。
```java
import java.io.FileInputStream;
import java.io.FileOutputStream;
import com.aspose.eps.PsDocument;
import com.aspose.eps.xmp.XmpMetadata;
import com.aspose.eps.xmp.XmpValue;
import com.aspose.page.BaseExamplesTest;
import com.aspose.page.License;
```
## ステップ 1: XMP メタデータを取得する
```java
//ドキュメントディレクトリへのパス。
String dataDir = "Your Document Directory";
//入力EPSファイルストリームを初期化します
FileInputStream psStream = new FileInputStream(dataDir + "xmp3.eps");
PsDocument document = new PsDocument(psStream);
//XMP メタデータを取得します。 EPS ファイルに XMP メタデータが含まれていない場合は、PS メタデータ コメント (%%Creator、%%CreateDate、%%Title など) からの値が埋め込まれた新しいファイルを取得します。
XmpMetadata xmp = document.getXmpMetadata();
```
このステップでは、EPS ファイルから既存の XMP メタデータを取得します。 EPS ファイルにまだ XMP メタデータが含まれていない場合、Aspose.Page は新しいメタデータを生成し、PS メタデータ コメントの値をそのファイルに埋め込みます。
## ステップ 2: 「dc:title」配列項目を追加する
```java
//「dc:title」配列項目をもう 1 つ追加します
xmp.addArrayItem("dc:title", new XmpValue("NewTitle"));
```
ここで、XMP メタデータの「dc:title」プロパティに新しい配列項目を追加します。 「NewTitle」を希望のタイトルに置き換えます。
## ステップ 3: 「dc:creator」配列項目を追加する
```java
//「dc:creator」配列項目をもう 1 つ追加します
xmp.addArrayItem("dc:creator", new XmpValue("NewCreator"));
```
同様に、XMP メタデータの「dc:creator」プロパティに新しい配列項目を追加します。 「NewCreator」を目的の作成者情報に置き換えます。
## ステップ 4: 出力 EPS ファイル ストリームを初期化する
```java
//出力EPSファイルストリームを初期化する
FileOutputStream outPsStream = new FileOutputStream(dataDir + "xmp3_changed.eps");
```
更新された XMP メタデータを含む変更されたドキュメントが保存される出力 EPS ファイル ストリームを準備します。
## ステップ 5: 変更された XMP メタデータを含むドキュメントを保存する
```java
//変更された XMP メタデータを含むドキュメントを保存する
try {			
    document.save(outPsStream);
} finally {
    outPsStream.close();
}
```
更新された XMP メタデータを含むドキュメントを出力 EPS ファイルに保存します。
## 結論
おめでとう！ Aspose.Page for Java を使用して XMP メタデータに配列項目を追加する方法を学習しました。この強力なライブラリは、EPS ファイルの操作プロセスを簡素化し、ドキュメント処理のための広範な機能を提供します。
## よくある質問

### Aspose.Page for Java を他のドキュメント形式で使用できますか?
はい、Aspose.Page は、EPS、PDF、XPS などのさまざまなドキュメント形式をサポートしています。
### Aspose.Page for Java に利用できる無料トライアルはありますか?
はい、無料トライアルにアクセスできます[ここ](https://releases.aspose.com/).
### Aspose.Page for Java のドキュメントはどこで見つけられますか?
ドキュメントは利用可能です[ここ](https://reference.aspose.com/page/java/).
### Aspose.Page for Java を購入するにはどうすればよいですか?
製品を購入できます[ここ](https://purchase.aspose.com/buy).
### Aspose.Page for Java の一時ライセンスは利用できますか?
はい、一時ライセンスを取得できます[ここ](https://purchase.aspose.com/temporary-license/).
{{< /blocks/products/pf/tutorial-page-section >}}

{{< /blocks/products/pf/main-container >}}
{{< /blocks/products/pf/main-wrap-class >}}

{{< blocks/products/products-backtop-button >}}
