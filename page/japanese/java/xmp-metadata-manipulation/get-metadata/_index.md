---
title: Java を使用して XMP からメタデータを取得する
linktitle: Java を使用して XMP からメタデータを取得する
second_title: Aspose.Page Java API
description: Aspose.Page for Java の機能を解放して、XMP メタデータを簡単に抽出します。ステップバイステップのガイドでドキュメント分析を強化しましょう!
weight: 18
url: /ja/java/xmp-metadata-manipulation/get-metadata/
---

{{< blocks/products/pf/main-wrap-class >}}
{{< blocks/products/pf/main-container >}}
{{< blocks/products/pf/tutorial-page-section >}}

# Java を使用して XMP からメタデータを取得する

## 導入
Aspose.Page for Java を利用して XMP ファイルからメタデータを抽出するためのステップバイステップ ガイドへようこそ。 XMP (Extensible Metadata Platform) は、メタデータをファイルに保存する標準化された方法を提供します。このチュートリアルでは、Java を使用して XMP から重要な情報を取得することに重点を置き、ドキュメントの詳細についての洞察を提供します。
## 前提条件
チュートリアルに進む前に、次の前提条件を満たしていることを確認してください。
- Java Development Kit (JDK): マシンに Java がインストールされていることを確認してください。
-  Aspose.Page for Java: Aspose.Page ライブラリをダウンロードしてインストールします。[ここ](https://releases.aspose.com/page/java/).
## パッケージのインポート
Java プロジェクトで、必要なパッケージをインポートします。
```java
import java.io.FileInputStream;
import com.aspose.eps.PsDocument;
import com.aspose.eps.xmp.XmpMetadata;
import com.aspose.eps.xmp.XmpValue;
import com.aspose.page.BaseExamplesTest;
import com.aspose.page.License;
```
## ステップ 1: 入力 EPS ファイル ストリームを初期化する
まず、ドキュメント ディレクトリへのパスを設定し、入力 EPS ファイル ストリームを初期化します。
```java
String dataDir = "Your Document Directory";
FileInputStream psStream = new FileInputStream(dataDir + "xmp1.eps");
PsDocument document = new PsDocument(psStream);
```
## ステップ 2: XMP メタデータを取得する
EPS ファイルから XMP メタデータを取得します。ファイルに XMP メタデータがない場合は、PS メタデータ コメントの値を使用して新しいメタデータが生成されます。
```java
XmpMetadata xmp = document.getXmpMetadata();
```
## ステップ 3: CreatorTool 情報を抽出する
XMP メタデータから「CreatorTool」値を確認して印刷します。
```java
if (xmp.containsKey("xmp:CreatorTool"))
    System.out.println("CreatorTool: " + xmp.get("xmp:CreatorTool").toStringValue());
```
## ステップ 4: CreateDate 情報を抽出する
XMP メタデータから「CreateDate」値を確認して出力します。
```java
if (xmp.containsKey("xmp:CreateDate"))
    System.out.println("CreateDate: " + xmp.get("xmp:CreateDate").toStringValue());
```
## ステップ 5: サムネイルの幅を取得する
サムネイルが存在する場合は、最初のサムネイルの幅を抽出して印刷します。
```java
if (xmp.containsKey("xmp:Thumbnails") && xmp.get("xmp:Thumbnails").isArray()) {
    XmpValue val = xmp.get("xmp:Thumbnails").toArray()[0];
    if (val.isNamedValues() && val.toNamedValues().containsKey("xmpGImg:width"))
        System.out.println("Thumbnail Width: " + val.toNamedValues().get("xmpGImg:width").toInteger());
}
```
## ステップ 6: 形式情報を抽出する
XMP メタデータから「format」値を確認して出力します。
```java
if (xmp.containsKey("dc:format"))
    System.out.println("Format: " + xmp.get("dc:format").toStringValue());
```
## ステップ 7: DocumentID を取得する
XMP メタデータから「DocumentID」値を確認して印刷します。
```java
if (xmp.containsKey("xmpMM:DocumentID"))
    System.out.println("DocumentID: " + xmp.get("xmpMM:DocumentID").toStringValue());
```
## 結論
おめでとう！ Aspose.Page for Java を使用して XMP メタデータを抽出する方法を学習しました。このガイドでは、プロセスの包括的な概要を説明し、ドキュメントから重要な情報を効果的に取得できるようにします。
## よくある質問
### Aspose.Page for Java を他のプログラミング言語で使用できますか?
はい、Aspose.Page は Java、.NET などを含む複数の言語をサポートしています。チェックしてください[ドキュメンテーション](https://reference.aspose.com/page/java/)詳細については。
### Aspose.Page for Java の無料トライアルは利用できますか?
はい、無料トライアルにアクセスできます[ここ](https://releases.aspose.com/).
### Aspose.Page for Java のサポートはどこで見つけられますか?
訪問[Aspose.Page フォーラム](https://forum.aspose.com/c/page/39)コミュニティサポートのために。
### Aspose.Page for Java の一時ライセンスを取得するにはどうすればよいですか?
仮免許が取得できる[ここ](https://purchase.aspose.com/temporary-license/).
### Aspose.Page for Java に関する追加のリソースはありますか?
完全なものを探索する[ドキュメンテーション](https://reference.aspose.com/page/java/)そしてライブラリをダウンロードします[ここ](https://releases.aspose.com/page/java/).
{{< /blocks/products/pf/tutorial-page-section >}}

{{< /blocks/products/pf/main-container >}}
{{< /blocks/products/pf/main-wrap-class >}}

{{< blocks/products/products-backtop-button >}}
