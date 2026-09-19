---
date: 2026-09-19
description: Aspose.Page for Java を使用して EPS ファイルに XMP の名前付き値を追加する方法を学びましょう – コード例付きのステップバイステップガイドです。
keywords:
- how to add xmp
- add named value XMP Java
- Aspose.Page XMP metadata
- EPS XMP manipulation
- Java metadata API
lastmod: 2026-09-19
linktitle: Java で XMP に名前付き値を追加する
og_description: Aspose.Page for Java を使用して EPS ファイルに XMP の名前付き値を追加する方法。数分でカスタムメタデータを注入できる簡潔なガイドをご覧ください。
og_image_alt: Screenshot of Java code adding XMP named value to an EPS file with Aspose.Page
og_title: Java を使用して EPS ファイルに XMP の名前付き値を追加する方法
schemas:
- author: Aspose
  dateModified: '2026-09-19'
  description: Learn how to add XMP named values to EPS files using Aspose.Page for
    Java – a step‑by‑step guide with code examples.
  headline: How to add XMP named value in EPS files using Java
  type: TechArticle
- description: Learn how to add XMP named values to EPS files using Aspose.Page for
    Java – a step‑by‑step guide with code examples.
  name: How to add XMP named value in EPS files using Java
  steps:
  - name: Initialize input EPS file stream
    text: '**FileInputStream** is a Java I/O class that reads raw bytes from a file.
      Load the source EPS file into a `FileInputStream`. This stream feeds the document
      into Aspose’s API. > **Pro tip:** Keep the `dataDir` variable configurable so
      the same code works across environments.'
  - name: Obtain XMP metadata
    text: '**XmpMetadata** represents the XMP packet associated with an EPS document.
      Retrieve the existing XMP packet; if the EPS file lacks one, Aspose creates
      a fresh XMP object populated from the PS comments.'
  - name: Add named value
    text: '**NamedValue** is a key‑value pair stored within the XMP metadata namespace.
      Insert a custom named value into the XMP structure. In this example we add a
      new key under the `xmpTPg:MaxPageSize` namespace. > **Why this matters:** Named
      values let you store arbitrary key‑value pairs that downstream app'
  - name: Initialize output EPS file stream
    text: '**FileOutputStream** is a Java I/O class that writes raw bytes to a file.
      Prepare a `FileOutputStream` where the modified EPS will be saved.'
  - name: Save document
    text: The `save` method persists the changes. It writes the updated XMP packet
      back into the EPS file, guaranteeing that the new named value becomes part of
      the document’s metadata.
  - name: Close input EPS stream
    text: Closing the original file handle prevents resource leaks and ensures that
      the file is not locked for subsequent operations. By following these six steps,
      you have successfully **added a named value in XMP metadata** using **Aspose.Page
      for Java**.
  type: HowTo
- questions:
  - answer: Yes, Aspose.Page for Java is designed to work seamlessly with other Java
      libraries, providing flexibility in your development environment.
    question: Can I use Aspose.Page for Java with other Java libraries?
  - answer: Yes, you can access a free trial of Aspose.Page for Java on the [Aspose
      releases page](https://releases.aspose.com/).
    question: Is a free trial available for Aspose.Page for Java?
  - answer: Visit the [temporary license page](https://purchase.aspose.com/temporary-license/)
      to obtain a temporary license for Aspose.Page for Java.
    question: How can I obtain a temporary license for Aspose.Page for Java?
  - answer: Explore the [documentation](https://reference.aspose.com/page/java/) for
      comprehensive tutorials and examples.
    question: Where can I find more tutorials and examples for Aspose.Page for Java?
  - answer: Absolutely, Aspose.Page for Java is designed to handle large‑scale projects
      efficiently, providing robust document manipulation capabilities.
    question: Is Aspose.Page for Java suitable for large‑scale projects?
  type: FAQPage
second_title: Aspose.Page Java API
tags:
- XMP metadata
- Aspose.Page
- Java EPS
- document automation
title: Java を使用して EPS ファイルに XMP の名前付き値を追加する方法
url: /ja/java/xmp-metadata-manipulation/add-named-value/
weight: 12
---

{{< blocks/products/pf/main-wrap-class >}}
{{< blocks/products/pf/main-container >}}
{{< blocks/products/pf/tutorial-page-section >}}

# Java を使用して XMP メタデータに名前付き値を追加する

## はじめに
最新の Java 開発において、EPS ファイル内に **XMP の追加方法** メタデータを学ぶことは、ドキュメントの出所を保持し、検索性を向上させるために不可欠です。**Aspose.Page for Java** を使用すれば、XMP パケットにカスタムの名前付き値を簡単に注入できます。このチュートリアルでは、コードスニペットを含む正確な手順を順を追って説明しますので、すぐに EPS ドキュメントに XMP メタデータを追加し始めることができます。

## クイック回答
- **必要なライブラリは何ですか？** Aspose.Page for Java (Aspose)  
- **対象となるファイルタイプは何ですか？** EPS files containing XMP metadata  
- **主な使用例は？** Add custom named values (e.g., page size limits) to XMP  
- **前提条件は？** JDK 8+ and the Aspose.Page for Java library  
- **一般的な実装時間は？** 5–10 minutes once the library is set up  

## asp とは何ですか？
Aspose は Aspose の略称で、外部ソフトウェアを必要とせずに、さまざまなドキュメント形式の作成、編集、変換、レンダリングを可能にする API スイートです。Aspose.Page for Java コンポーネントは特に PostScript と EPS の処理に焦点を当てており、ページコンテンツ、グラフィックス、XMP などのメタデータへのプログラムからのアクセスを提供します。

## なぜ XMP メタデータに名前付き値を追加するのか？
名前付き値を使用すると、任意のキー‑バリューのペアを XMP パケット内に直接保存でき、下流ツールが即座に読み取ることができます。これにより検索エンジンフレンドリーになり、ワークフローの自動化が可能になり、視覚的コンテンツを変更せずに規制情報を埋め込むことでコンプライアンス要件を満たすことができます。

## なぜ重要なのか
XMP に名前付き値を追加すると、EPS ファイル全体を解析せずに任意のキー‑バリューのペアを保存でき、読み取ることができます。この機能は、メタデータが下流のアクションを駆動する自動出版パイプライン、デジタル資産管理システム、コンプライアンス主導のワークフローで特に有用です。

## 前提条件
始める前に、以下が揃っていることを確認してください：

- **Java Development Kit (JDK):** マシンにインストールされた最新の JDK（8 以上）。
- **Aspose.Page for Java Library:** 公式の [Aspose.Page for Java download](https://releases.aspose.com/page/java/) からダウンロードしてください。JAR をプロジェクトのクラスパスに追加します。
- **An EPS file** 既に XMP メタデータを含んでいるか、または自動的に生成される EPS ファイル。

## パッケージのインポート
まず必要な Java パッケージをインポートします。これらのインポートにより、ファイルストリーム、EPS ドキュメントモデル、XMP 処理クラスにアクセスできるようになります。

```java
import java.io.FileInputStream;
import java.io.FileOutputStream;
import com.aspose.eps.PsDocument;
import com.aspose.eps.xmp.XmpMetadata;
import com.aspose.eps.xmp.XmpValue;
import com.aspose.page.BaseExamplesTest;
```

## Java を使用して EPS ファイルに XMP 名前付き値を追加する方法
名前付き値を追加するには、`FileInputStream` で EPS ファイルを読み込み、`XmpMetadata` オブジェクトを取得または作成し、目的の `NamedValue` を適切な名前空間に挿入し、`FileOutputStream` を使用して変更されたドキュメントを書き戻します。Aspose.Page は XMP パケットが存在しない場合に自動的に作成し、新しいメタデータが正しく埋め込まれるようにします。

### 手順 1: 入力 EPS ファイルストリームの初期化
**FileInputStream** はファイルから生のバイトを読み取る Java I/O クラスです。ソース EPS ファイルを `FileInputStream` にロードします。このストリームはドキュメントを Aspose の API に供給します。

```java
// The path to the documents directory.
String dataDir = "Your Document Directory";
// Initialize input EPS file stream
FileInputStream psStream = new FileInputStream(dataDir + "xmp4.eps");
PsDocument document = new PsDocument(psStream);
FileInputStream psStream = new FileInputStream(dataDir + "xmp4.eps");
PsDocument document = new PsDocument(psStream);
```

> **プロのコツ:** `dataDir` 変数を設定可能にしておくと、同じコードがさまざまな環境で動作します。

### 手順 2: XMP メタデータの取得
**XmpMetadata** は EPS ドキュメントに関連付けられた XMP パケットを表します。既存の XMP パケットを取得します。EPS ファイルに XMP がない場合、Aspose は PS コメントから情報を取得して新しい XMP オブジェクトを作成します。

```java
XmpMetadata xmp = document.getXmpMetadata();
```

### 手順 3: 名前付き値の追加
**NamedValue** は XMP メタデータ名前空間内に保存されるキー‑バリューのペアです。カスタムの名前付き値を XMP 構造に挿入します。この例では `xmpTPg:MaxPageSize` 名前空間の下に新しいキーを追加します。

```java
xmp.addNamedValue("xmpTPg:MaxPageSize", "stDim:newKey", new XmpValue("NewValue"));
```

> **なぜ重要なのか:** 名前付き値により、下流アプリケーションがドキュメント全体を解析せずに任意のキー‑バリューのペアを読み取ることができます。

### 手順 4: 出力 EPS ファイルストリームの初期化
**FileOutputStream** はファイルに生のバイトを書き込む Java I/O クラスです。変更された EPS を保存するための `FileOutputStream` を用意します。

```java
FileOutputStream outPsStream = new FileOutputStream(dataDir + "xmp4_changed.eps");
```

### 手順 5: ドキュメントの保存
`save` メソッドは変更を永続化します。更新された XMP パケットを EPS ファイルに書き戻し、新しい名前付き値がドキュメントのメタデータの一部になることを保証します。

```java
try {
    document.save(outPsStream);
} finally {
    outPsStream.close();
}
```

### 手順 6: 入力 EPS ストリームのクローズ
元のファイルハンドルを閉じることでリソースリークを防止し、後続の操作でファイルがロックされないようにします。

```java
psStream.close();
```

これらの 6 つの手順に従うことで、**Aspose.Page for Java** を使用して **XMP メタデータに名前付き値を追加** することに成功しました。

## よくある問題と解決策
| 問題 | 原因 | 対策 |
|-------|-------|-----|
| `NullPointerException` on `xmp` | EPS ファイルに XMP がなく、Aspose が生成できなかった | EPS に少なくとも 1 つの PS コメントが含まれていることを確認するか、手動で新しい `XmpMetadata` インスタンスを作成してください。 |
| Output file is empty | 出力ストリームがフラッシュまたはクローズされていない | `outPsStream.close()` が `finally` ブロックで呼び出されていることを確認してください（例参照）。 |
| Duplicate key error | 同じ名前付き値が 2 回追加された | 追加する前に `xmp.containsNamedValue(...)` でキーが既に存在するか確認してください。 |

## よくある質問

**Q:** Aspose.Page for Java を他の Java ライブラリと併用できますか？  
**A:** はい、Aspose.Page for Java は他の Java ライブラリとシームレスに連携できるよう設計されており、開発環境に柔軟性を提供します。

**Q:** Aspose.Page for Java の無料トライアルは利用可能ですか？  
**A:** はい、[Aspose releases page](https://releases.aspose.com/) で Aspose.Page for Java の無料トライアルにアクセスできます。

**Q:** Aspose.Page for Java の一時ライセンスはどのように取得できますか？  
**A:** [temporary license page](https://purchase.aspose.com/temporary-license/) を訪れて、Aspose.Page for Java の一時ライセンスを取得してください。

**Q:** Aspose.Page for Java のチュートリアルやサンプルはどこで見つけられますか？  
**A:** 包括的なチュートリアルとサンプルについては、[documentation](https://reference.aspose.com/page/java/) をご覧ください。

**Q:** Aspose.Page for Java は大規模プロジェクトに適していますか？  
**A:** はい、Aspose.Page for Java は大規模プロジェクトを効率的に処理できるよう設計されており、堅牢なドキュメント操作機能を提供します。

## 結論
このガイドでは、**Aspose.Page for Java** を使用して EPS ファイル内の **XMP メタデータに名前付き値を追加** する方法を示しました。上記の手順に従うことで、ドキュメントにカスタムメタデータを付加し、検索性を向上させ、より賢い下流処理を実現できます。

---

**最終更新日:** 2026-09-19  
**テスト環境:** Aspose.Page for Java 24.12 (latest at time of writing)  
**作者:** Aspose

## 関連チュートリアル

- [Aspose.Page を使用して EPS ファイルに XMP 名前空間を追加する方法 – Java チュートリアル](/page/java/xmp-metadata-manipulation/add-namespace/)
- [Java を使用して EPS ファイルに XMP メタデータを追加する](/page/java/xmp-metadata-manipulation/add-simple-properties/)
- [Aspose.Page を使用した XMP の読み取り – Java ガイド](/page/java/xmp-metadata-manipulation/get-metadata/)

{{< /blocks/products/pf/tutorial-page-section >}}

{{< /blocks/products/pf/main-container >}}
{{< /blocks/products/pf/main-wrap-class >}}

{{< blocks/products/products-backtop-button >}}