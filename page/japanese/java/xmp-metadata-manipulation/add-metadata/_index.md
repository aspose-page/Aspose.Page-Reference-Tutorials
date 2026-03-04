---
date: 2025-12-20
description: Aspose Page Java チュートリアルで EPS ファイルに XMP メタデータを追加する方法を学びましょう。ステップバイステップのガイドに従って、ドキュメント管理を強化してください。
linktitle: Add Metadata in XMP using Java
second_title: Aspose.Page Java API
title: Aspose Page Java チュートリアル – EPS ファイルに XMP メタデータを追加する
url: /ja/java/xmp-metadata-manipulation/add-metadata/
weight: 11
---

{{< blocks/products/pf/main-wrap-class >}}
{{< blocks/products/pf/main-container >}}
{{< blocks/products/pf/tutorial-page-section >}}

# Java を使用した XMP メタデータの追加

## はじめに
この **aspose page java tutorial** では、Java を使用して XMP 情報を追加することでドキュメントのメタデータを強化する方法を学びます。このステップバイステップガイドでは、既存の EPS ファイルを読み取り、XMP メタデータを抽出し、Aspose.Page for Java ライブラリを使用して変更をディスクに保存する手順を説明します。チュートリアルの最後までに、任意の EPS ワークフローで XMP を扱うための堅牢で再利用可能なパターンを習得できます。

## クイック回答
- **必要なライブラリは何ですか？** Aspose.Page for Java  
- **任意の EPS ファイルに XMP を追加できますか？** はい – 既に存在しない場合、API が新しい XMP ブロックを作成します。  
- **開発にライセンスは必要ですか？** 評価用の無料トライアルで動作しますが、商用利用には商用ライセンスが必要です。  
- **サポートされている Java バージョンはどれですか？** Java 8 以降。  
- **実装にどれくらい時間がかかりますか？** 基本的なメタデータ更新で通常 10 分未満です。

## Aspose Page Java チュートリアル概要
このチュートリアルでは、EPS ファイルの XMP メタデータを操作するために必要な主要な手順を示します。これらの手順を理解することで、メタデータ処理を大規模なドキュメント処理パイプラインに統合し、検索性を向上させ、デジタル資産管理の業界標準に準拠できるようになります。

## 前提条件
チュートリアルに入る前に、以下の前提条件を満たしていることを確認してください：
- Java プログラミングの基本的な知識。  
- Aspose.Page for Java ライブラリがインストールされていること。ダウンロードは[here](https://releases.aspose.com/page/java/)から。  
- 変更したい EPS ファイル。

## パッケージのインポート
まず、Java プログラムに必要なパッケージをインポートします：

```java
import java.io.FileInputStream;
import java.io.FileOutputStream;
import com.aspose.eps.PsDocument;
import com.aspose.eps.xmp.XmpMetadata;
import com.aspose.page.BaseExamplesTest;
```

## ステップ 1: XMP メタデータの取得
```java
// The path to the documents directory.
String dataDir = "Your Document Directory";
// Initialize input EPS file stream
FileInputStream psStream = new FileInputStream(dataDir + "xmp2.eps");
PsDocument document = new PsDocument(psStream);
// Get XMP metadata. If EPS file doesn't contain XMP metadata, a new one is created using values from PS metadata comments (%%Creator, %%CreateDate, %%Title, etc.)
XmpMetadata xmp = document.getXmpMetadata();
```

`"Your Document Directory"` を、実際にドキュメントが保存されているパスに置き換えてください。

## ステップ 2: CreatorTool の値を取得
```java
// Get "CreatorTool" value
if (xmp.containsKey("xmp:CreatorTool"))
    System.out.println("CreatorTool: " + xmp.get("xmp:CreatorTool").toStringValue());
```

## ステップ 3: CreateDate の値を取得
```java
// Get "CreateDate" value
if (xmp.containsKey("xmp:CreateDate"))
    System.out.println("CreateDate: " + xmp.get("xmp:CreateDate").toStringValue());
```

## ステップ 4: Title の値を取得
```java
// Get "Title" value
if (xmp.containsKey("dc:title"))
    System.out.println("Title: " + xmp.get("dc:title").toArray()[0].toStringValue());
```

## ステップ 5: Format の値を取得
```java
// Get "format" value
if (xmp.containsKey("dc:format"))
    System.out.println("Format: " + xmp.get("dc:format").toStringValue());
```

## ステップ 6: Creator の値を取得
```java
// Get "creator" value
if (xmp.containsKey("dc:creator"))
    System.out.println("Creator: " + xmp.get("dc:creator").toArray()[0].toStringValue());
```

## ステップ 7: MetadataDate の値を取得
```java
// Get "MetadataDate" value
if (xmp.containsKey("xmp:MetadataDate"))
    System.out.println("MetadataDate: " + xmp.get("xmp:MetadataDate").toStringValue());
```

## ステップ 8: 新しい XMP メタデータでドキュメントを保存
```java
// Initialize output EPS file stream
FileOutputStream outPsStream = new FileOutputStream(dataDir + "xmp2_changed.eps");
// Save document with new XMP metadata
try {			
    document.save(outPsStream);
} finally {
    outPsStream.close();
}
```

最後に、入力 EPS ストリームを閉じることを忘れないでください：

```java
// Close input EPS stream
psStream.close();
```

これで、Aspose.Page for Java を使用して EPS ファイルにメタデータを正常に追加できました！

## 結論
この **aspose page java tutorial** では、Aspose.Page for Java ライブラリを使用して EPS ファイルに XMP メタデータを追加する方法を検討しました。この強力な API を利用すれば、プログラムからドキュメントメタデータを操作でき、資産の整理と検索性向上に役立ちます。

## よくある質問

**Q: Aspose.Page for Java は無料で使用できますか？**  
A: Aspose.Page for Java は商用製品です。無料トライアルは[here](https://releases.aspose.com/) からお試しください。

**Q: Aspose.Page for Java のドキュメントはどこで見つけられますか？**  
A: ドキュメントは[here](https://reference.aspose.com/page/java/) にあります。

**Q: Aspose.Page for Java の一時ライセンスはどのように取得できますか？**  
A: 一時ライセンスは[here](https://purchase.aspose.com/temporary-license/) から取得できます。

**Q: Aspose.Page for Java がサポートするファイル形式は何ですか？**  
A: Aspose.Page for Java は EPS、PDF、XPS など様々な形式をサポートしています。

**Q: Aspose.Page for Java を購入できますか？**  
A: はい、購入は[here](https://purchase.aspose.com/buy) から可能です。

**Q: 大きな EPS ファイルにメタデータを追加する際の対策は？**  
A: ストリーミング方式で処理し（上記参照）、メモリ使用量を抑え、ストリームは速やかに閉じてください。

**Q: 既存の XMP フィールドを変更することはできますか？**  
A: もちろんです。`xmp.put(key, value)` を使用して、保存前にエントリを更新または新規追加できます。

---

**最終更新日:** 2025-12-20  
**テスト環境:** Aspose.Page for Java 24.12 (latest)  
**作者:** Aspose  

{{< /blocks/products/pf/tutorial-page-section >}}

{{< /blocks/products/pf/main-container >}}
{{< /blocks/products/pf/main-wrap-class >}}

{{< blocks/products/products-backtop-button >}}