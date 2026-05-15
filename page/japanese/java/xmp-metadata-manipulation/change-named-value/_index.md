---
date: 2026-05-15
description: Aspose.Page for Java を使用して、XMP メタデータの編集方法と EPS ファイル内の XMP 値の変更方法を学びます
  – 明確なステップバイステップ ガイド
keywords:
- how to edit xmp
- how to change xmp
- Aspose.Page XMP Java
- edit EPS metadata
- XMP manipulation Java
linktitle: Java を使用した XMP の名前付き値の変更
schemas:
- author: Aspose
  dateModified: '2026-05-15'
  description: Learn how to edit XMP metadata and how to change XMP values in EPS
    files with Aspose.Page for Java – a clear step‑by‑step guide.
  headline: how to edit xmp – Change Named Value in XMP using Java
  type: TechArticle
- description: Learn how to edit XMP metadata and how to change XMP values in EPS
    files with Aspose.Page for Java – a clear step‑by‑step guide.
  name: how to edit xmp – Change Named Value in XMP using Java
  steps:
  - name: '**Java Development Environment** – A JDK (8 or higher) and an IDE or build
      tool (Maven/Gradle).'
    text: '**Java Development Environment** – A JDK (8 or higher) and an IDE or build
      tool (Maven/Gradle).'
  - name: '**Aspose.Page for Java Library** – Download and integrate the Aspose.Page
      for Java library into your project. You can find the library and detailed documentation
      [here](https://reference.aspose.com/page/java/).'
    text: '**Aspose.Page for Java Library** – Download and integrate the Aspose.Page
      for Java library into your project. You can find the library and detailed documentation
      [here](https://reference.aspose.com/page/java/).'
  - name: '**Sample EPS File** – Have a sample EPS file ready for experimentation.
      If you don''t have one, use the provided example file named **"xmp4.eps."**'
    text: '**Sample EPS File** – Have a sample EPS file ready for experimentation.
      If you don''t have one, use the provided example file named **"xmp4.eps."**'
  type: HowTo
- questions:
  - answer: Aspose.Page primarily supports Java, but Aspose offers equivalent libraries
      for .NET, C++, and Python that expose similar XMP manipulation capabilities.
    question: Can I use Aspose.Page for Java with other programming languages?
  - answer: Yes, you can explore a free trial of Aspose.Page for Java [here](https://releases.aspose.com/).
    question: Is there a free trial available for Aspose.Page for Java?
  - answer: Visit the [Aspose.Page forum](https://forum.aspose.com/c/page/39) for
      community support and discussions.
    question: Where can I find additional support and discussions about Aspose.Page
      for Java?
  - answer: You can acquire a temporary license [here](https://purchase.aspose.com/temporary-license/).
    question: How can I obtain a temporary license for Aspose.Page for Java?
  - answer: To buy Aspose.Page for Java, visit the [purchase page](https://purchase.aspose.com/buy).
    question: Where can I purchase Aspose.Page for Java?
  type: FAQPage
second_title: Aspose.Page Java API
title: XMP の編集方法 – Java を使用した XMP の名前付き値の変更
url: /ja/java/xmp-metadata-manipulation/change-named-value/
weight: 16
---

{{< blocks/products/pf/main-wrap-class >}}
{{< blocks/products/pf/main-container >}}
{{< blocks/products/pf/tutorial-page-section >}}

# XMP を編集する方法 – Java を使用した XMP の名前付き値の変更

モダンな文書ワークフローにおいて、**Aspose.Page for Java** は EPS ファイル内の XMP メタデータを簡単に読み取り、編集し、書き込むことができます。**このチュートリアルでは XMP を編集する方法を示します**。Aspose.Page API を使用して EPS ドキュメントの XMP メタデータを操作することで、文書情報を正確かつ検索可能に保ち、業界標準に準拠させることができます。ページサイズ、作成者情報、カスタムタグの更新など、以下の手順で Java による処理方法を解説します。

## クイック回答
- **What does this tutorial cover?** Changing a named XMP value in an EPS file with Aspose.Page for Java.  
- **Which library version is required?** Any recent Aspose.Page for Java release (the API has been stable for several years).  
- **Do I need a license?** A temporary or full license is required for production; a free trial works for testing.  
- **How long does implementation take?** Roughly 10‑15 minutes for a developer familiar with Java I/O.  
- **Can I use this with other file formats?** The XMP API is also available for PDF, SVG, and other formats supported by Aspose.Page.

## XMP メタデータとは？

XMP (Extensible Metadata Platform) は、作成者、タイトル、カスタムプロパティなどのリッチなメタデータを XML ベースで標準化した形式で、ファイル内部に直接埋め込むことができます。EPS ドキュメントでは、XMP は従来の PostScript コメントと並存して存在し、ビジュアルコンテンツを変更せずにメタデータの読み書きが可能です。

## なぜ Aspose.Page for Java を使用して XMP を編集するのか？

Aspose.Page は **full control over more than 150 XMP schema properties** を提供し、EPS、PDF、SVG 形式で一貫して動作します。ファイルを **500 MB** まで、ドキュメント全体をメモリにロードせずに処理でき、組み込みのバリデーションにより生成された EPS が標準準拠であることを保証します。外部の XML パーサやネイティブライブラリは不要です。

## はじめに

Aspose.Page for Java は EPS ファイルの操作と処理を支援する堅牢なライブラリです。これらのファイル内の XMP メタデータを扱う際、Aspose.Page は開発者に包括的な機能セットを提供します。本チュートリアルでは XMP の名前付き値を変更する方法に焦点を当て、ドキュメント処理機能を強化したい開発者向けに分かりやすく解説します。

## 前提条件

チュートリアルに入る前に、以下の前提条件が整っていることを確認してください：
1. **Java Development Environment** – A JDK (8 or higher) and an IDE or build tool (Maven/Gradle).  
2. **Aspose.Page for Java Library** – Download and integrate the Aspose.Page for Java library into your project. You can find the library and detailed documentation [こちら](https://reference.aspose.com/page/java/)。  
3. **Sample EPS File** – Have a sample EPS file ready for experimentation. If you don't have one, use the provided example file named **"xmp4.eps."**  

## パッケージのインポート

The `import` statements bring the essential Aspose.Page classes into scope.

The `PsDocument` class is Aspose.Page's core object that represents an EPS document in memory.  
The `XmpMetadata` class provides access to the XMP packet embedded in the EPS file.  

```java
import java.io.FileInputStream;
import java.io.FileOutputStream;
import com.aspose.eps.PsDocument;
import com.aspose.eps.xmp.XmpMetadata;
import com.aspose.eps.xmp.XmpValue;
import com.aspose.page.BaseExamplesTest;
import com.aspose.page.License;
```

## XMP メタデータの編集方法

Load the EPS file, retrieve its XMP packet, modify the desired property, and save the document—all in a few straightforward lines. This approach works for any named XMP value, whether it’s a standard Dublin Core field or a custom namespace you’ve defined.

## 手順 1: 入力 EPS ファイルストリームの初期化

`FileInputStream` opens a read‑only stream to the source EPS file, allowing Aspose.Page to ingest the document without locking the file system.

```java
// The path to the documents directory.
String dataDir = "Your Document Directory";
        
// Initialize input EPS file stream
FileInputStream psStream = new FileInputStream(dataDir + "xmp4.eps");
```

## 手順 2: PsDocument の初期化

`PsDocument` is the primary object that encapsulates the EPS content and provides access to its metadata, pages, and resources.

```java
PsDocument document = new PsDocument(psStream);
```

## 手順 3: XMP メタデータの取得

`XmpMetadata` represents the XMP packet inside the EPS file and offers methods to read, modify, or delete individual properties.

```java
// Get XMP metadata. If EPS file doesn't contain XMP metadata, we get a new one filled with values from PS metadata comments (%%Creator, %%CreateDate, %%Title, etc.)
XmpMetadata xmp = document.getXmpMetadata();
```

## 手順 4: XMP に新しい値を設定

`setProperty` sets the value of a specified XMP property in the metadata packet.

```java
// Set new string value "Inches" for named value "stDim:unit" of structure "xmpTPg:MaxPageSize" 
xmp.setNamedValue("xmpTPg:MaxPageSize", "stDim:unit", new XmpValue("Inches"));
```

## 手順 5: 出力 EPS ファイルストリームの初期化

`FileOutputStream` creates a writable stream for saving the modified EPS file.

```java
// Initialize output EPS file stream
FileOutputStream outPsStream = new FileOutputStream(dataDir + "xmp4_changed.eps");
```

## 手順 6: 変更された XMP メタデータでドキュメントを保存

`save` writes the in‑memory PsDocument, including updated XMP, to the output stream.

```java
// Save document with changed XMP metadata
try {			
    document.save(outPsStream);
} finally {
    outPsStream.close();
}
```

## 手順 7: 入力 EPS ストリームを閉じる

`close` releases the file handle and frees resources associated with the input stream.

```java
// Close input EPS stream
psStream.close();
```

## よくある問題と解決策
- **FileNotFoundException** – Verify that `dataDir` points to the correct folder and that `xmp4.eps` exists.  
- **LicenseException** – If you see licensing errors, make sure a valid Aspose.Page license file is loaded before creating `PsDocument`.  
- **Metadata Not Updated** – After saving, open the resulting EPS in a metadata viewer (e.g., Adobe Bridge) to confirm the new value appears.

## よくある質問

**Q: Aspose.Page for Java を他のプログラミング言語と併用できますか？**  
A: Aspose.Page は主に Java をサポートしていますが、.NET、C++、Python 用の同等ライブラリも提供されており、同様の XMP 操作機能を利用できます。

**Q: Aspose.Page for Java の無料トライアルはありますか？**  
A: はい、Aspose.Page for Java の無料トライアルは [こちら](https://releases.aspose.com/) からお試しいただけます。

**Q: Aspose.Page for Java に関する追加サポートやディスカッションはどこで見つけられますか？**  
A: コミュニティサポートやディスカッションは [Aspose.Page フォーラム](https://forum.aspose.com/c/page/39) でご確認ください。

**Q: Aspose.Page for Java の一時ライセンスはどのように取得できますか？**  
A: 一時ライセンスは [こちら](https://purchase.aspose.com/temporary-license/) から取得できます。

**Q: Aspose.Page for Java を購入するにはどこへ行けばよいですか？**  
A: 購入は [購入ページ](https://purchase.aspose.com/buy) から行えます。

**最終更新日:** 2026-05-15  
**テスト環境:** Aspose.Page for Java (latest release)  
**作者:** Aspose

## 関連チュートリアル

- [Java を使用した XMP メタデータの読み取り – Aspose.Page ガイド](/page/java/xmp-metadata-manipulation/get-metadata/)
- [Aspose Page Java チュートリアル – EPS ファイルに XMP メタデータを追加](/page/java/xmp-metadata-manipulation/add-metadata/)
- [aspose.page modify xmp – Java を使用した XMP の値変更](/page/java/xmp-metadata-manipulation/change-values/)

{{< /blocks/products/pf/tutorial-page-section >}}

{{< /blocks/products/pf/main-container >}}
{{< /blocks/products/pf/main-wrap-class >}}

{{< blocks/products/products-backtop-button >}}