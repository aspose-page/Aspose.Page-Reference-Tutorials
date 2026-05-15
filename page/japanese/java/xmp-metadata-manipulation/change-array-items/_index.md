---
date: 2026-05-15
description: aspose.page の Java 用 XMP チュートリアルを探求しましょう—XMP メタデータの配列項目の変更方法や、EPS タイトルや作成者の更新などを、数行のコードで学べます。
keywords:
- aspose.page xmp tutorial
- change array items java
- xmp metadata java
linktitle: Java を使用して XMP の配列項目を変更する
schemas:
- author: Aspose
  dateModified: '2026-05-15'
  description: Explore the aspose.page xmp tutorial for Java—learn how to change array
    items in XMP metadata, update EPS titles, creators, and more in just a few lines
    of code.
  headline: 'aspose.page xmp tutorial: Change Array Items in XMP using Java'
  type: TechArticle
- description: Explore the aspose.page xmp tutorial for Java—learn how to change array
    items in XMP metadata, update EPS titles, creators, and more in just a few lines
    of code.
  name: 'aspose.page xmp tutorial: Change Array Items in XMP using Java'
  steps:
  - name: Get XMP Metadata
    text: Call `document.getXmpMetadata()` to retrieve the XMP metadata object associated
      with the EPS file.
  - name: Set "dc:title" Array Item
    text: Use `xmpMetadata.setArrayItem("dc:title", 0, "New Title")` to replace the
      first title entry.
  - name: Set "dc:creator" Array Item
    text: Similarly, `xmpMetadata.setArrayItem("dc:creator", 0, "New Author")` updates
      the first creator entry.
  - name: Initialize Output EPS File Stream
    text: Create a `FileOutputStream` pointing to the destination EPS file to write
      the updated document.
  - name: Save Document with Changed XMP Metadata
    text: The `PsDocument` class represents an EPS document and provides the `save`
      method to write changes to a stream.
  type: HowTo
- questions:
  - answer: No. You must invoke `setArrayItem` for each index you wish to modify;
      the API does not provide a bulk‑update method.
    question: Can I update multiple array items in one call?
  - answer: Yes. Provide the full prefix (e.g., `myNS:customProp`) when calling `setArrayItem`
      or `removeArrayItem`.
    question: Does aspose.page xmp java support custom namespaces?
  - answer: Reload the EPS with `PsDocument`, call `getXmpMetadata()`, and inspect
      the returned values, or open the file in an XMP viewer.
    question: How do I verify that the metadata was updated correctly?
  - answer: Use `removeArrayItem(namespace, index)` to delete a specific entry from
      an XMP array.
    question: Is it possible to remove an array item entirely?
  - answer: No. XMP metadata is stored separately from the graphic content and does
      not alter how the EPS renders.
    question: Will the changes affect the visual appearance of the EPS?
  type: FAQPage
second_title: Aspose.Page Java API
title: 'aspose.page XMP チュートリアル: Java を使用して XMP の配列項目を変更する'
url: /ja/java/xmp-metadata-manipulation/change-array-items/
weight: 15
---

{{< blocks/products/pf/main-wrap-class >}}
{{< blocks/products/pf/main-container >}}
{{< blocks/products/pf/tutorial-page-section >}}

# aspose.page xmp チュートリアル: JavaでXMPの配列項目を変更する

## はじめに
私たちの包括的な **aspose.page xmp tutorial**へようこそ。このガイドでは、Aspose.Page for Java を使用して EPS ファイル内の XMP メタデータの配列項目を変更する方法をステップバイステップで示します。ドキュメントのタイトル、著者リスト、またはその他の XMP 配列を更新する必要がある場合でも、手順はシンプルで完全にプログラムで実行でき、Java 8 + に対応しています。

## クイック回答
- **aspose.page xmp java は何をしますか？** Java から直接 EPS ファイルの XMP メタデータを読み書きします。  
- **試用するのにライセンスは必要ですか？** はい、30 日間の無料トライアルが利用可能です。商用利用には商用ライセンスが必要です。  
- **サポートされている JDK バージョンはどれですか？** Java 8 以降（Java 11、17、21 を含む）。  
- **他のメタデータフィールドを変更できますか？** もちろんです。カスタム名前空間を含む任意の XMP プロパティを読み取りまたは更新できます。  
- **API はスレッドセーフですか？** 各スレッドが独自の `PsDocument` インスタンスを使用する場合、ほとんどの読み書き操作は安全です。

## aspose.page xmp java とは何ですか？
`aspose.page xmp java` は、Aspose.Page for Java のコンポーネントで、拡張メタデータプラットフォーム (XMP) を使いやすい Java オブジェクトに抽象化します。配列、バッグ、構造化プロパティを生の XML を扱わずに操作できます。実際には、`setArrayItem` や `removeArrayItem` といった高レベルメソッドを使用してメタデータを即座に編集します。

## なぜ EPS メタデータに aspose.page xmp java を使用するのですか？
大規模に EPS メタデータを正確かつ自動的に制御する必要がある場合にこのライブラリを使用すべきです。Aspose.Page は **30 以上の XMP スキーマ フィールド** をサポートし、**500 MB** までのファイルをドキュメント全体をメモリに読み込まずに処理でき、速度と低メモリフットプリントを実現します。API は変更が元のグラフィックを保持することも保証するため、ビジュアルレンダリングは影響を受けません。

## 前提条件
- Java Development Kit (JDK) 8 以上がインストールされていること。  
- Aspose.Page for Java ライブラリ。最新の JAR は [here](https://releases.aspose.com/page/java/) からダウンロードしてください。  
- 有効な Aspose ライセンスファイル（またはトライアル ライセンス）をクラスパスに配置する。

## aspose.page xmp java で配列項目を変更する方法
このセクションでは、完全なワークフローを示します：EPS ファイルを開き、XMP メタデータオブジェクトを取得し、特定の配列エントリを変更し、最後に更新されたドキュメントをディスクに書き戻します。各ステップは簡潔な Java コードで示されており、独自のアプリケーションに簡単に組み込めます。

### ステップ 1: XMP メタデータを取得
`document.getXmpMetadata()` を呼び出して、EPS ファイルに関連付けられた XMP メタデータオブジェクトを取得します。

```java
import java.io.FileInputStream;
import java.io.FileOutputStream;
import com.aspose.eps.PsDocument;
import com.aspose.eps.xmp.XmpMetadata;
import com.aspose.eps.xmp.XmpValue;
import com.aspose.page.BaseExamplesTest;
```

### ステップ 2: "dc:title" 配列項目を設定
`xmpMetadata.setArrayItem("dc:title", 0, "New Title")` を使用して、最初のタイトルエントリを置き換えます。

```java
// The path to the documents directory.
String dataDir = "Your Document Directory";
// Initialize input EPS file stream
FileInputStream psStream = new FileInputStream(dataDir + "xmp3.eps");
PsDocument document = new PsDocument(psStream);
// Get XMP metadata. If EPS file doesn't contain XMP metadata, a new one will be filled with values from PS metadata comments.
XmpMetadata xmp = document.getXmpMetadata();
```

### ステップ 3: "dc:creator" 配列項目を設定
同様に、`xmpMetadata.setArrayItem("dc:creator", 0, "New Author")` は最初の作成者エントリを更新します。

```java
// Set "dc:title" array item by index 0 
xmp.setArrayItem("dc:title", 0, new XmpValue("NewTitle"));
```

### ステップ 4: 出力 EPS ファイルストリームを初期化
更新されたドキュメントを書き込むために、宛先 EPS ファイルを指す `FileOutputStream` を作成します。

```java
// Set "dc:creator" array item by index 0
xmp.setArrayItem("dc:creator", 0, new XmpValue("NewCreator"));
```

### ステップ 5: 変更された XMP メタデータでドキュメントを保存
`PsDocument` クラスは EPS ドキュメントを表し、変更をストリームに書き込むための `save` メソッドを提供します。

```java
// Initialize output EPS file stream
FileOutputStream outPsStream = new FileOutputStream(dataDir + "xmp3_changed.eps");
```

## よくある落とし穴とヒント
- **インデックス範囲外:** 対象のインデックスが存在することを確認してください。存在しない場合、Aspose は `ArrayIndexOutOfBoundsException` をスローします。  
- **ストリーム管理:** `finally` ブロックでストリームを必ず閉じるか、try‑with‑resources を使用してファイルロックを防止してください。  
- **ライセンスの有効化:** 有効なライセンスを適用し忘れると、トライアルモードで透かし入りの EPS が生成されます。  
- **大きなファイル:** 200 MB を超える EPS ファイルの場合、メモリ圧迫を防ぐために JVM ヒープサイズ（`-Xmx2g` など）を増やすことを検討してください。

## よくある質問

**Q: 複数の配列項目を一度に更新できますか？**  
A: いいえ。変更したい各インデックスに対して `setArrayItem` を呼び出す必要があります。API には一括更新メソッドは用意されていません。

**Q: aspose.page xmp java はカスタム名前空間をサポートしていますか？**  
A: はい。`setArrayItem` や `removeArrayItem` を呼び出す際に、完全なプレフィックス（例: `myNS:customProp`）を指定してください。

**Q: メタデータが正しく更新されたかどうかを確認するには？**  
A: `PsDocument` で EPS を再ロードし、`getXmpMetadata()` を呼び出して返された値を確認するか、XMP ビューアでファイルを開いて確認してください。

**Q: 配列項目を完全に削除することは可能ですか？**  
A: XMP 配列から特定のエントリを削除するには、`removeArrayItem(namespace, index)` を使用します。

**Q: 変更は EPS のビジュアル外観に影響しますか？**  
A: いいえ。XMP メタデータはグラフィックコンテンツとは別に保存されており、EPS のレンダリング方法には影響しません。

## 結論
これで **aspose.page xmp tutorial**（Java）をマスターし、EPS の XMP メタデータ内の配列項目を自信を持って変更できるようになりました。この機能により、ビジュアルデータに手を加えることなく、ドキュメントパイプラインの自動化、メタデータの一括更新、資産管理の向上が可能になります。

---

**最終更新日:** 2026-05-15  
**テスト環境:** Aspose.Page for Java 24.11 (latest at time of writing)  
**作者:** Aspose  

{{< blocks/products/products-backtop-button >}}

```java
// Save document with changed XMP metadata
try {
    document.save(outPsStream);
} finally {
    outPsStream.close();
}
```

## 関連チュートリアル

- [JavaでXMPメタデータに配列項目を追加](/page/java/xmp-metadata-manipulation/add-array-items/)
- [aspose page xmp チュートリアル – JavaでXMPの名前付き値を変更](/page/java/xmp-metadata-manipulation/change-named-value/)
- [JavaでXMPメタデータを読み取る方法 – Aspose.Page ガイド](/page/java/xmp-metadata-manipulation/get-metadata/)


{{< /blocks/products/pf/tutorial-page-section >}}
{{< /blocks/products/pf/main-container >}}
{{< /blocks/products/pf/main-wrap-class >}}