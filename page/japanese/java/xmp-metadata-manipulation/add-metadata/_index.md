---
date: 2026-03-08
description: Aspose Page Java チュートリアルで EPS ファイルに XMP メタデータを追加する方法を学びましょう。このステップバイステップガイドに従って、ドキュメント管理を強化してください。
linktitle: Add Metadata in XMP using Java
second_title: Aspose.Page Java API
title: Aspose Page Java チュートリアル – EPS ファイルに XMP メタデータを追加する
url: /ja/java/xmp-metadata-manipulation/add-metadata/
weight: 11
---

{{< blocks/products/pf/main-wrap-class >}}
{{< blocks/products/pf/main-container >}}
{{< blocks/products/pf/tutorial-page-section >}}

# Java を使用して XMP にメタデータを追加する

## はじめに
この **aspose page java tutorial** では、Java を使用して XMP 情報を追加することでドキュメントのメタデータを強化する方法を学びます。このステップバイステップ ガイドでは、既存の EPS ファイルを読み取り、XMP メタデータを抽出し、Aspose.Page for Java ライブラリを使って変更をディスクに保存する手順を説明します。チュートリアルの最後までに、任意の EPS ワークフローで XMP を扱うための堅牢で再利用可能なパターンを習得できます。

## クイック回答
- **必要なライブラリは何ですか？** Aspose.Page for Java  
- **任意の EPS ファイルに XMP を追加できますか？** はい – 既に XMP ブロックが存在しない場合、API が新しい XMP ブロックを作成します。  
- **開発にライセンスは必要ですか？** 無料トライアルで評価は可能ですが、製品環境では商用ライセンスが必要です。  
- **サポートされている Java バージョンは？** Java 8 以降。  
- **実装にどれくらい時間がかかりますか？** 基本的なメタデータ更新で通常 10 分未満です。

## Aspose Page Java とは？
Aspose.Page for Java（通称 **aspose page java**）は、高性能な API で、開発者が Adobe ソフトウェアを使用せずに PostScript および EPS ファイルを作成、編集、変換できます。また、XMP メタデータへのフルアクセスを提供し、グラフィック ファイルに検索可能な情報を直接埋め込むことが可能です。

## なぜ EPS ファイルに XMP メタデータを追加するのか？
XMP メタデータを埋め込むことで、資産管理、検索性、IPTC や Dublin Core といった業界標準への準拠が向上します。作成者、タイトル、作成日などのフィールドを追加すると、DAM、検索エンジン、印刷ワークフローなどの下流システムが自動的にインデックス付けし、EPS 資産を整理できます。

## Aspose Page Java チュートリアル概要
本チュートリアルでは、EPS ファイルの XMP メタデータを操作するための基本手順を示します。これらの手順を理解すれば、メタデータ処理を大規模なドキュメント処理パイプラインに組み込んだり、検索性を向上させたり、デジタル資産管理の業界標準に準拠したりすることが容易になります。

## 前提条件
チュートリアルに入る前に、以下の前提条件を満たしていることを確認してください。
- Java プログラミングの基本的な知識。  
- Aspose.Page for Java ライブラリがインストール済み。ダウンロードは [here](https://releases.aspose.com/page/java/) から。  
- 変更したい EPS ファイル。

## パッケージのインポート
まず、Java プログラムに必要なパッケージをインポートします:

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

## ステップ 2: CreatorTool 値の取得
```java
// Get "CreatorTool" value
if (xmp.containsKey("xmp:CreatorTool"))
    System.out.println("CreatorTool: " + xmp.get("xmp:CreatorTool").toStringValue());
```

## ステップ 3: CreateDate 値の取得
```java
// Get "CreateDate" value
if (xmp.containsKey("xmp:CreateDate"))
    System.out.println("CreateDate: " + xmp.get("xmp:CreateDate").toStringValue());
```

## ステップ 4: Title 値の取得
```java
// Get "Title" value
if (xmp.containsKey("dc:title"))
    System.out.println("Title: " + xmp.get("dc:title").toArray()[0].toStringValue());
```

## ステップ 5: Format 値の取得
```java
// Get "format" value
if (xmp.containsKey("dc:format"))
    System.out.println("Format: " + xmp.get("dc:format").toStringValue());
```

## ステップ 6: Creator 値の取得
```java
// Get "creator" value
if (xmp.containsKey("dc:creator"))
    System.out.println("Creator: " + xmp.get("dc:creator").toArray()[0].toStringValue());
```

## ステップ 7: MetadataDate 値の取得
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

最後に、入力 EPS ストリームを閉じることを忘れないでください:

```java
// Close input EPS stream
psStream.close();
```

これで、Aspose.Page for Java を使用して EPS ファイルにメタデータを正常に追加できました！

## よくある問題と解決策
- **Missing XMP block** – API が自動的に作成しますが、EPS ファイルが破損していないことを確認してください。  
- **Unsupported characters** – XMP の値は UTF‑8 である必要があります。メタデータ フィールドに非標準の記号は使用しないでください。  
- **Large EPS files** – メモリ使用量を抑えるためにストリーム方式で処理し（上記参照）、`finally` ブロックで必ずストリームを閉じてください。

## 結論
この **aspose page java tutorial** では、Aspose.Page for Java ライブラリを使用して EPS ファイルに XMP メタデータを追加する方法を解説しました。この強力な API を利用すれば、プログラムからドキュメントのメタデータを操作でき、資産の整理と検索性向上に役立ちます。

## よくある質問

**Q: Aspose.Page for Java は無料で使用できますか？**  
A: Aspose.Page for Java は商用製品です。無料トライアルは [here](https://releases.aspose.com/) からお試しいただけます。

**Q: Aspose.Page for Java のドキュメントはどこで確認できますか？**  
A: ドキュメントは [here](https://reference.aspose.com/page/java/) にあります。

**Q: Aspose.Page for Java の一時ライセンスはどこで取得できますか？**  
A: 一時ライセンスは [here](https://purchase.aspose.com/temporary-license/) から取得できます。

**Q: Aspose.Page for Java がサポートするファイル形式は何ですか？**  
A: EPS、PDF、XPS など、さまざまな形式をサポートしています。

**Q: Aspose.Page for Java を購入できますか？**  
A: はい、購入は [here](https://purchase.aspose.com/buy) から可能です。

**Q: メタデータを追加する際に大きな EPS ファイルはどう扱えばよいですか？**  
A: ストリーミング方式で処理し、メモリ使用量を抑え、ストリームは速やかに閉じてください。

**Q: 既存の XMP フィールドを読み取りだけでなく変更できますか？**  
A: もちろんです。`xmp.put(key, value)` を使用して、保存前にエントリを更新または追加できます。

---

**Last Updated:** 2026-03-08  
**Tested With:** Aspose.Page for Java 24.12 (latest)  
**Author:** Aspose  

{{< /blocks/products/pf/tutorial-page-section >}}

{{< /blocks/products/pf/main-container >}}
{{< /blocks/products/pf/main-wrap-class >}}

{{< blocks/products/products-backtop-button >}}