---
date: 2026-05-20
description: Aspose.Page for Java を使用して EPS ファイルに XMP メタデータを追加する方法を学びます。プログラムでシンプルな
  XMP プロパティを埋め込むステップバイステップガイドです。
keywords:
- add xmp metadata
- how to add xmp
- Aspose.Page Java XMP
linktitle: Java で XMP にシンプルなプロパティを追加する
schemas:
- author: Aspose
  dateModified: '2026-05-20'
  description: Learn how to add XMP metadata to EPS files with Aspose.Page for Java.
    Step‑by‑step guide to embed simple XMP properties programmatically.
  headline: Add XMP Metadata to EPS Files Using Java
  type: TechArticle
- questions:
  - answer: Aspose.Page primarily supports Java, but equivalent libraries are available
      for .NET, C++, and Python.
    question: Can I use Aspose.Page for Java with other programming languages?
  - answer: Yes, you can explore the features of Aspose.Page by obtaining a free trial
      **[here](https://releases.aspose.com/)**.
    question: Is a free trial available for Aspose.Page for Java?
  - answer: The documentation is available **[here](https://reference.aspose.com/page/java/)**.
    question: Where can I find detailed documentation for Aspose.Page for Java?
  - answer: A temporary license can be acquired **[here](https://purchase.aspose.com/temporary-license/)**.
    question: How can I obtain a temporary license for Aspose.Page for Java?
  - answer: You can purchase the product **[here](https://purchase.aspose.com/buy)**.
    question: Where can I purchase Aspose.Page for Java?
  type: FAQPage
second_title: Aspose.Page Java API
title: Java を使用して EPS ファイルに XMP メタデータを追加する
url: /ja/java/xmp-metadata-manipulation/add-simple-properties/
weight: 14
---

{{< blocks/products/pf/main-wrap-class >}}
{{< blocks/products/pf/main-container >}}
{{< blocks/products/pf/tutorial-page-section >}}

# EPSファイルにXMPメタデータを追加する（Java）

## はじめに
モダンなグラフィックパイプラインでは、**add XMP metadata** をプログラムで EPS ファイルに追加できることで、イラストの記述、検索、アーカイブ方法を完全にコントロールできます。Aspose.Page for Java を使用すれば、Java エコシステムを離れることなく EPS ドキュメント内の XMP パケットを読み取り、変更、書き込みが可能です。このチュートリアルでは、EPS ファイルにシンプルな XMP プロパティを追加する手順を詳しく解説し、カスタムメタデータでグラフィックを迅速かつ確実に強化できるようにします。

## クイック回答
- **What does “add XMP metadata to EPS” mean?** EPS ファイル内に XMP パケット（XML ベースのメタデータ）を埋め込むことです。  
- **Which library is required?** Aspose.Page for Java（Aspose サイトからダウンロード可能）。  
- **Do I need a license for testing?** 開発には無料トライアルで動作しますが、本番環境では商用ライセンスが必要です。  
- **How many lines of code?** Java のコードは 30 行未満で、インポート文が数行だけです。  
- **Can I add other data types?** はい、日付、整数、倍精度浮動小数点数、文字列、さらには配列もサポートされています。

## Java で EPS ファイルに XMP メタデータを追加する方法
`new PsDocument("input.eps")` で EPS ファイルをロードし、XMP パケットを取得または作成し、目的のプロパティを挿入してから、ドキュメントをディスクに保存します—すべて Java コードで 10 行未満です。このアプローチにより、EPS ソースを手動で編集することなく、検索可能で標準準拠のメタデータを埋め込むことができます。

## EPS における XMP メタデータとは
EPS の XMP メタデータは、EPS ファイル内部に存在する XML パケットで、作者、作成日、カスタムタグなどの情報を格納します。このパケットを埋め込むことで、下流のツールは別個のサイドカーファイルを必要とせずにデータを読み取り、利用できます。

## なぜ EPS ファイルに XMP メタデータを追加するのか
XMP メタデータを埋め込むことで、EPS アセットは即座に検索可能になり、ファイル内にライセンス情報を保存することでコンプライアンスが確保され、埋め込まれたタグに基づいて自動パイプラインが判断を下すことができ、メタデータがすべてのプラットフォームでグラフィックと共に移動することが保証されます。Aspose.Page は、ドキュメント全体をメモリにロードせずに最大 500 MB のファイルを処理でき、大規模なワークロードでも高速なパフォーマンスを提供します。

## 前提条件
開始する前に、以下を確認してください：

- Java プログラミングの基本的な知識。  
- Aspose.Page for Java ライブラリがインストールされていること。**[here](https://releases.aspose.com/page/java/)** からダウンロードできます。  
- メタデータを含むサンプル EPS ファイル。お持ちでない場合は、提供されている **`xmp3.eps`** ファイルをご利用ください。

## パッケージのインポート
まず、必要なクラスをインポートします。インポート文は元の例と全く同じです：

```java
import java.io.FileInputStream;
import java.io.FileOutputStream;
import java.util.Date;
import java.util.TimeZone;
import com.aspose.eps.PsDocument;
import com.aspose.eps.xmp.XmpMetadata;
import com.aspose.eps.xmp.XmpValue;
import com.aspose.page.BaseExamplesTest;
```

## ステップ 1: EPS ドキュメントをロードして XMP メタデータを取得
`PsDocument` クラスは EPS ファイルを表し、その内容とメタデータにアクセスするメソッドを提供します。  
`XmpMetadata` オブジェクトはドキュメントに関連付けられた XMP パケットを保持します。

```java
// The path to the documents directory.
String dataDir = "Your Document Directory";
// Initialize input EPS file stream
FileInputStream psStream = new FileInputStream(dataDir + "xmp3.eps");
PsDocument document = new PsDocument(psStream);
// Get XMP metadata. If EPS file doesn't contain XMP metadata, we get a new one filled with values from PS metadata comments (%%Creator, %%CreateDate, %%Title, etc.)
XmpMetadata xmp = document.getXmpMetadata();
```

## ステップ 2: Date プロパティを追加
`Date` クラスはミリ秒精度で特定の時点を表します。

```java
// Add date property "xmp:Date1" value
TimeZone.setDefault(TimeZone.getTimeZone("UTC"));
Date now = new Date();
xmp.put("xmp:Date1", new XmpValue(now));
```

## ステップ 3: Integer プロパティを追加
`Integer` クラスはプリミティブな `int` 値をオブジェクトとしてラップします。

```java
// Add integer property "xmp:Intg1" value
xmp.put("xmp:Intg1", new XmpValue(111));
```

## ステップ 4: Double プロパティを追加
`Double` クラスはプリミティブな `double` 値をオブジェクトとしてラップします。

```java
// Add double property "xmp:Double1" value
xmp.put("xmp:Double1", new XmpValue(111.11D));
```

## ステップ 5: String プロパティを追加
`String` クラスは文字列（文字のシーケンス）を表します。

```java
// Add string property "xmp:String1" value
xmp.put("xmp:String1", new XmpValue("ABC"));
```

## ステップ 6: 更新された EPS ファイルを保存
`save` メソッドは変更されたドキュメントをディスクに書き戻し、EPS の構造を保持します。

```java
// Initialize output EPS file stream
FileOutputStream outPsStream = new FileOutputStream(dataDir + "xmp3_changed.eps");
// Save document with changed XMP metadata
try {
    document.save(outPsStream);
} finally {
    outPsStream.close();
}
```

## ステップ 7: リソースのクリーンアップ
ファイルハンドルのリークを防ぎ、すべてのバッファがフラッシュされるように、常にストリームを閉じてください。

```java
// Close input EPS stream
psStream.close();
```

## よくある問題と解決策
| Issue | Reason | Fix |
|-------|--------|-----|
| **Null XMP metadata** | EPS ファイルに XMP パケットがなく、ライブラリが PS コメントを推測できませんでした。 | ソース EPS に少なくとも 1 つの PS コメント（例: `%%Creator`）が含まれていることを確認してください。ライブラリは自動的に最小限の XMP パケットを生成します。 |
| **Time zone mismatch** | 別のアプリケーションで開くと日付がずれて表示されます。 | `Date` オブジェクトを作成する前に `TimeZone.setDefault(TimeZone.getTimeZone("UTC"))` を設定してください（ステップ 2 参照）。 |
| **License exception** | 実行時に `LicenseException` がスローされます。 | API を使用する前に有効な Aspose.Page ライセンスを適用するか、評価用にトライアルモードで実行してください。 |

## よくある質問
**Q: Aspose.Page for Java を他のプログラミング言語で使用できますか？**  
A: Aspose.Page は主に Java をサポートしていますが、.NET、C++、Python 用の同等ライブラリも利用可能です。

**Q: Aspose.Page for Java の無料トライアルは利用できますか？**  
A: はい、**[here](https://releases.aspose.com/)** から無料トライアルを取得して Aspose.Page の機能を試すことができます。

**Q: Aspose.Page for Java の詳細なドキュメントはどこで見つけられますか？**  
A: ドキュメントは **[here](https://reference.aspose.com/page/java/)** で入手可能です。

**Q: Aspose.Page for Java の一時ライセンスはどこで取得できますか？**  
A: 一時ライセンスは **[here](https://purchase.aspose.com/temporary-license/)** から取得できます。

**Q: Aspose.Page for Java をどこで購入できますか？**  
A: 製品は **[here](https://purchase.aspose.com/buy)** から購入できます。

**最終更新日:** 2026-05-20  
**テスト環境:** Aspose.Page for Java 24.12 (latest at time of writing)  
**作者:** Aspose  

{{< blocks/products/products-backtop-button >}}

## 関連チュートリアル

- [Java を使用した XMP メタデータの読み取り方法 – Aspose.Page ガイド](/page/java/xmp-metadata-manipulation/get-metadata/)
- [aspose.page XMP チュートリアル – Java で XMP に名前空間を追加](/page/java/xmp-metadata-manipulation/add-namespace/)
- [Java を使用した XMP メタデータへの配列項目の追加](/page/java/xmp-metadata-manipulation/add-array-items/)


{{< /blocks/products/pf/tutorial-page-section >}}
{{< /blocks/products/pf/main-container >}}
{{< /blocks/products/pf/main-wrap-class >}}