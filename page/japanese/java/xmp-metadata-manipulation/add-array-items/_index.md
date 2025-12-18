---
date: 2025-12-18
description: Aspose.Page for Java を使用して、EPS ファイルの XMP メタデータに配列項目を挿入し、メタデータを追加する方法を学びましょう。ステップバイステップのガイドをご覧ください。
linktitle: Add Array Items in XMP Metadata using Java
second_title: Aspose.Page Java API
title: メタデータの追加方法 – XMPで配列項目を追加する（Java）
url: /ja/java/xmp-metadata-manipulation/add-array-items/
weight: 10
---

{{< blocks/products/pf/main-wrap-class >}}
{{< blocks/products/pf/main-container >}}
{{< blocks/products/pf/tutorial-page-section >}}

# Java を使用した XMP メタデータへの配列項目の追加

## メタデータの追加方法
Welcome to our step‑by‑step guide on **メタデータの追加方法** to EPS files with Aspose.Page for Java. In this tutorial we’ll walk you through adding array items to XMP metadata—a common requirement when you need to enrich document information such as titles or creators. By the end, you’ll understand why XMP is valuable, how to manipulate it programmatically, and how to save the updated EPS file.

## クイック回答
- **使用されているライブラリは何ですか？** Aspose.Page for Java  
- **対象となるファイル形式は何ですか？** EPS (Encapsulated PostScript)  
- **複数のタイトルを追加できますか？** はい、`xmp.addArrayItem("dc:title", ...)` を繰り返し使用します  
- **本番環境でライセンスが必要ですか？** はい、有効な Aspose.Page ライセンスが必要です  
- **コードは Java 8+ と互換性がありますか？** 絶対に、すべての最新 Java バージョンで動作します  

## 前提条件
Before we dive into the tutorial, make sure you have the following prerequisites:
- Aspose.Page for Java ライブラリがインストールされていること。  
- Java プログラミングの基本的な理解。  
- 既存の XMP メタデータまたは PS メタデータコメントが含まれる有効な EPS ファイル。  

## パッケージのインポート
To get started, you need to import the necessary packages for working with Aspose.Page. Include the following lines at the beginning of your Java file:
```java
import java.io.FileInputStream;
import java.io.FileOutputStream;
import com.aspose.eps.PsDocument;
import com.aspose.eps.xmp.XmpMetadata;
import com.aspose.eps.xmp.XmpValue;
import com.aspose.page.BaseExamplesTest;
import com.aspose.page.License;
```

## 手順 1: XMP メタデータの取得
```java
// The path to the documents directory.
String dataDir = "Your Document Directory";
// Initialize input EPS file stream
FileInputStream psStream = new FileInputStream(dataDir + "xmp3.eps");
PsDocument document = new PsDocument(psStream);
// Get XMP metadata. If EPS file doesn't contain XMP metadata, we get a new one filled with values from PS metadata comments (%%Creator, %%CreateDate, %%Title, etc.)
XmpMetadata xmp = document.getXmpMetadata();
```
In this step, we retrieve the existing XMP metadata from the EPS file. If the EPS file doesn't already contain XMP metadata, Aspose.Page generates a new one and fills it with values from PS metadata comments.

## 手順 2: "dc:title" 配列項目の追加
```java
// Add one more "dc:title" array item 
xmp.addArrayItem("dc:title", new XmpValue("NewTitle"));
```
Now, we add a new array item to the **dc:title** property in the XMP metadata. Replace `"NewTitle"` with the desired title.

## 手順 3: "dc:creator" 配列項目の追加
```java
// Add one more "dc:creator" array item
xmp.addArrayItem("dc:creator", new XmpValue("NewCreator"));
```
Similarly, we add a new array item to the **dc:creator** property in the XMP metadata. Replace `"NewCreator"` with the desired creator information.

## 手順 4: 出力 EPS ファイルストリームの初期化
```java
// Initialize output EPS file stream
FileOutputStream outPsStream = new FileOutputStream(dataDir + "xmp3_changed.eps");
```
Prepare the output EPS file stream where the modified document with updated XMP metadata will be saved.

## 手順 5: 変更された XMP メタデータでドキュメントを保存
```java
// Save document with changed XMP metadata
try {			
    document.save(outPsStream);
} finally {
    outPsStream.close();
}
```
Save the document with the updated XMP metadata to the output EPS file.

## 結論
Congratulations! You've successfully learned **メタデータの追加方法** by inserting array items in XMP metadata using Aspose.Page for Java. This powerful library simplifies the process of manipulating EPS files and provides extensive functionality for document processing.

## よくある質問

### Aspose.Page for Java を他のドキュメント形式と併用できますか？
はい、Aspose.Page は EPS、PDF、XPS などのさまざまなドキュメント形式をサポートしています。

### Aspose.Page for Java の無料トライアルは利用できますか？
はい、無料トライアルは[こちら](https://releases.aspose.com/)から利用できます。

### Aspose.Page for Java のドキュメントはどこで見つけられますか？
ドキュメントは[こちら](https://reference.aspose.com/page/java/)で入手可能です。

### Aspose.Page for Java を購入するには？
製品は[こちら](https://purchase.aspose.com/buy)から購入できます。

### Aspose.Page for Java の一時ライセンスは利用可能ですか？
はい、一時ライセンスは[こちら](https://purchase.aspose.com/temporary-license/)で取得できます。

## 追加のよくある質問

**Q: 同じプロパティに複数の配列項目を追加できますか？**  
**A:** もちろんです。同じプロパティに対して `xmp.addArrayItem` を複数回呼び出すことで、値のリストを構築できます。

**Q: このアプローチは Dublin Core 以外の既存 XMP スキーマでも機能しますか？**  
**A:** はい、名前空間が正しく参照されている限り、任意の XMP プロパティに配列項目を追加できます。

**Q: メタデータが正しく追加されたかどうかを確認する方法は？**  
**A:** XMP をサポートするビューア（例: Adobe Bridge）で生成された EPS ファイルを開くか、`XmpMetadata` メソッドを使用してプログラム的にメタデータを抽出してください。

---

**最終更新日:** 2025-12-18  
**テスト環境:** Aspose.Page for Java 24.11  
**著者:** Aspose  

{{< /blocks/products/pf/tutorial-page-section >}}

{{< /blocks/products/pf/main-container >}}
{{< /blocks/products/pf/main-wrap-class >}}
{{< blocks/products/products-backtop-button >}}