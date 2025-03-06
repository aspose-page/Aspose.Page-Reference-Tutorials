---
title: Java を使用して XMP にメタデータを追加する
linktitle: Java を使用して XMP にメタデータを追加する
second_title: Aspose.Page Java API
description: Aspose.Page for Java のシームレスな統合を検討し、XMP メタデータを EPS ファイルに簡単に追加する方法を学びましょう。今すぐドキュメント管理ゲームをレベルアップしましょう!
weight: 11
url: /ja/java/xmp-metadata-manipulation/add-metadata/
---

{{< blocks/products/pf/main-wrap-class >}}
{{< blocks/products/pf/main-container >}}
{{< blocks/products/pf/tutorial-page-section >}}

# Java を使用して XMP にメタデータを追加する

## 導入
Java を使用して XMP 情報を追加して、ドキュメントのメタデータを強化したいと考えていますか?これ以上探さない！このステップバイステップのガイドでは、Aspose.Page for Java ライブラリを使用して EPS ファイルにメタデータを追加するプロセスについて説明します。 Aspose.Page は、Java アプリケーションでのドキュメント操作タスクを簡素化する強力なツールです。
## 前提条件
チュートリアルに入る前に、次の前提条件を満たしていることを確認してください。
- Java プログラミングの基本的な知識。
-  Aspose.Page for Java ライブラリがインストールされています。ダウンロードできます[ここ](https://releases.aspose.com/page/java/).
- 変更する EPS ファイル。
## パッケージのインポート
まず、必要なパッケージを Java プログラムにインポートします。
```java
import java.io.FileInputStream;
import java.io.FileOutputStream;
import com.aspose.eps.PsDocument;
import com.aspose.eps.xmp.XmpMetadata;
import com.aspose.page.BaseExamplesTest;
```
## ステップ 1: XMP メタデータを取得する
```java
//ドキュメントディレクトリへのパス。
String dataDir = "Your Document Directory";
//入力EPSファイルストリームを初期化します
FileInputStream psStream = new FileInputStream(dataDir + "xmp2.eps");
PsDocument document = new PsDocument(psStream);
// XMP メタデータを取得します。 EPS ファイルに XMP メタデータが含まれていない場合は、PS メタデータ コメント (%%Creator、%%CreateDate、%%Title など) の値を使用して新しいファイルが作成されます。
XmpMetadata xmp = document.getXmpMetadata();
```
「ドキュメント ディレクトリ」をドキュメントが保存されている実際のパスに置き換えてください。

## ステップ 2: CreatorTool 値を取得する
```java
//「CreatorTool」の値を取得する
if (xmp.containsKey("xmp:CreatorTool"))
    System.out.println("CreatorTool: " + xmp.get("xmp:CreatorTool").toStringValue());
```
## ステップ 3: CreateDate 値を取得する
```java
//「CreateDate」値を取得する
if (xmp.containsKey("xmp:CreateDate"))
    System.out.println("CreateDate: " + xmp.get("xmp:CreateDate").toStringValue());
```
## ステップ 4: タイトル値を取得する
```java
//「タイトル」の値を取得する
if (xmp.containsKey("dc:title"))
    System.out.println("Title: " + xmp.get("dc:title").toArray()[0].toStringValue());
```
## ステップ 5: フォーマット値の取得
```java
//「フォーマット」値を取得する
if (xmp.containsKey("dc:format"))
    System.out.println("Format: " + xmp.get("dc:format").toStringValue());
```
## ステップ 6: 作成者の値を取得する
```java
//「作成者」の値を取得する
if (xmp.containsKey("dc:creator"))
    System.out.println("Creator: " + xmp.get("dc:creator").toArray()[0].toStringValue());
```
## ステップ 7: MetadataDate 値を取得する
```java
//「MetadataDate」値を取得する
if (xmp.containsKey("xmp:MetadataDate"))
    System.out.println("MetadataDate: " + xmp.get("xmp:MetadataDate").toStringValue());
```
## ステップ 8: 新しい XMP メタデータを含むドキュメントを保存する
```java
//出力EPSファイルストリームを初期化する
FileOutputStream outPsStream = new FileOutputStream(dataDir + "xmp2_changed.eps");
//新しい XMP メタデータを含むドキュメントを保存する
try {			
    document.save(outPsStream);
} finally {
    outPsStream.close();
}
```
最後に、入力 EPS ストリームを閉じることを忘れないでください。
```java
//入力 EPS ストリームを閉じる
psStream.close();
```
これで、Aspose.Page for Java を使用して EPS ファイルにメタデータが正常に追加されました。
## 結論
このチュートリアルでは、Aspose.Page for Java ライブラリを使用して XMP メタデータを EPS ファイルに追加するプロセスについて説明しました。この強力なツールを使用すると、ドキュメントをシームレスに操作できるようになり、全体的なドキュメント管理エクスペリエンスが向上します。
## よくある質問
### Q: Aspose.Page for Java は無料で使用できますか?
 A: Aspose.Page for Java は商用製品です。無料トライアルを通じてその機能を試すことができます[ここ](https://releases.aspose.com/).
### Q: Aspose.Page for Java のドキュメントはどこで見つけられますか?
 A: ドキュメントは入手可能です[ここ](https://reference.aspose.com/page/java/).
### Q: Aspose.Page for Java の一時ライセンスはどのように取得できますか?
 A: 仮免許を取得できます。[ここ](https://purchase.aspose.com/temporary-license/).
### Q: Aspose.Page for Java はどのようなファイル形式をサポートしていますか?
A: Aspose.Page for Java は、EPS、PDF、XPS などのさまざまな形式をサポートしています。
### Q: Java 用の Aspose.Page を購入できますか?
 A: はい、Aspose.Page for Java を購入できます。[ここ](https://purchase.aspose.com/buy).
{{< /blocks/products/pf/tutorial-page-section >}}

{{< /blocks/products/pf/main-container >}}
{{< /blocks/products/pf/main-wrap-class >}}

{{< blocks/products/products-backtop-button >}}
