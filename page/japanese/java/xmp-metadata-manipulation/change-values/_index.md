---
date: 2026-05-25
description: Aspose.PageとJavaを使用して、EPSドキュメント内のXMPを変更する方法を学びましょう。metadata を迅速かつ確実に更新できます。
keywords:
- how to modify xmp
- Aspose.Page Java
- XMP metadata EPS
linktitle: JavaでXMPの値を変更
schemas:
- author: Aspose
  dateModified: '2026-05-25'
  description: Learn how to modify xmp in EPS documents using Java with Aspose.Page.
    Update metadata quickly and reliably.
  headline: how to modify xmp with Aspose.Page – Change Values in XMP using Java
  type: TechArticle
- questions:
  - answer: Utilize `TimeZone.setDefault(TimeZone.getTimeZone("UTC"))` to ensure consistency
      in time zone settings.
    question: How can I handle time zone considerations when modifying XMP values?
  - answer: Yes, by using the `put` method for each desired value, you can modify
      multiple XMP values concurrently.
    question: Can I change multiple XMP values in a single operation?
  - answer: Explore the comprehensive documentation [here](https://reference.aspose.com/page/java/).
    question: Where can I find additional documentation for Aspose.Page for Java?
  - answer: Yes, you can access the free trial [here](https://releases.aspose.com/).
    question: Is there a free trial available for Aspose.Page for Java?
  - answer: Obtain a temporary license [here](https://purchase.aspose.com/temporary-license/).
    question: How can I obtain a temporary license for Aspose.Page for Java?
  type: FAQPage
second_title: Aspose.Page Java API
title: Aspose.PageでXMPを変更する方法 – JavaでXMPの値を変更
url: /ja/java/xmp-metadata-manipulation/change-values/
weight: 17
---

{{< blocks/products/pf/main-wrap-class >}}
{{< blocks/products/pf/main-container >}}
{{< blocks/products/pf/tutorial-page-section >}}

# Java を使用して XMP の値を変更する

## はじめに
Java で EPS ファイル内の **how to modify xmp** を探しているなら、ここが正しい場所です。このチュートリアルでは、既存の XMP ブロックの読み取り、creator、title、modify date などのフィールドの更新、そして最終的に変更を EPS ドキュメントに保存するまでのすべての手順を解説します。最後まで実行すれば、任意の自動化ワークフローに組み込める再利用可能なスニペットが手に入り、ブランド、コンプライアンス、検索エンジンのインデックス付けのために正しいメタデータがファイルに付与されます。

## クイック回答
- **「aspose.page modify xmp」は何をしますか？** Aspose.Page Java API を使用して EPS ファイルの XMP メタデータを読み書きできるようにします。  
- **どのライブラリ バージョンが必要ですか？** 最近の Aspose.Page for Java のリリースであればどれでも構いません（API はバージョン間で安定しています）。  
- **サンプルを実行するのにライセンスは必要ですか？** 評価には無料トライアルで動作しますが、本番環境では商用ライセンスが必要です。  
- **複数の XMP フィールドを同時に変更できますか？** はい。ドキュメントを保存する前に各フィールドに対して `put` を呼び出します。  
- **タイムゾーンの処理は必要ですか？** デフォルトのタイムゾーン（例: UTC）を設定することで、日付の一貫性が保たれます。

## XMP とは何か、そしてなぜ変更するのか
XMP（Extensible Metadata Platform）は、EPS、PDF、画像などのファイルにリッチなメタデータを直接埋め込むための標準化された XML ベースのフォーマットです。XMP を更新することで、ドキュメントのインデックス付け、表示、検索方法を制御でき、ブランドの一貫性、規制遵守、そして自動コンテンツパイプラインにとって重要です。

## なぜ Aspose.Page for Java を使用するのか？
Aspose.Page は **フル機能の純粋な Java API** を提供し、外部ツールやネイティブライブラリの必要性を排除します。**50 以上の入力および出力フォーマット** をサポートし、**500 MB** までの EPS ファイルをドキュメント全体をメモリに読み込むことなく処理でき、Java が動作するあらゆる OS で高速かつ低メモリでメタデータ操作を実現します。

## 前提条件
このチュートリアルに入る前に、以下の前提条件が整っていることを確認してください。
1. **Java 開発環境** – JDK（8 以上）とお好みの IDE またはビルドツール。  
2. **Aspose.Page for Java ライブラリ** – Aspose.Page for Java ライブラリをダウンロードしてインストールします。必要なパッケージは [here](https://releases.aspose.com/page/java/) で見つけられます。

## パッケージのインポート
Java プロジェクトに必要なパッケージをインポートすることから始めます。これらのパッケージは EPS ドキュメントとやり取りし、操作するために不可欠です。

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

## Java を使用して EPS の XMP を変更する方法
`Document` は EPS ファイルを表す Aspose.Page のクラスで、コンテンツとメタデータへのアクセスを提供します。`XmpMetadata` はドキュメントに付随する XMP ブロックを表し、メタデータフィールドの読み書きが可能です。`put` は XmpMetadata オブジェクト内のメタデータエントリを追加または更新し、`save` は更新された XMP メタデータを含む変更後のドキュメントをファイルに書き込みます。

`new Document("input.eps")` で EPS ファイルをロードし、`XmpMetadata` オブジェクトを取得し、`put` で目的のキーを更新し、最後に `save` を呼び出して変更を新しいファイルに書き出します。この簡潔なフローは、欠落している XMP ブロックを自動的に処理し、必要に応じて PostScript コメントから作成し、タイムゾーンに一貫した日付を保証します。

## ステップ 1: XMP メタデータを取得する
`XmpMetadata` クラスは EPS ドキュメントに付随する XMP ブロックを表します。`document.getXmpMetadata()` を呼び出すと、API は既存のブロックを返すか、`%%Creator`、`%%CreateDate`、`%%Title` などの PS コメントから新しいブロックを構築します。

```java
// The path to the documents directory.
String dataDir = "Your Document Directory";
// Initialize input EPS file stream
FileInputStream psStream = new FileInputStream(dataDir + "xmp1.eps");
PsDocument document = new PsDocument(psStream);
// Get XMP metadata. If EPS file doesn't contain XMP metadata, a new one is created with values from PS metadata comments
XmpMetadata xmp = document.getXmpMetadata();
```

## ステップ 2: "ModifyDate" の値を変更する
`"ModifyDate"` エントリを新しい変更タイムスタンプに更新します。`java.util.Date` と `TimeZone.setDefault(TimeZone.getTimeZone("UTC"))` を組み合わせて、保存される値がタイムゾーンに依存しないことを保証します。

```java
// Change "ModifyDate" value
TimeZone.setDefault(TimeZone.getTimeZone("UTC"));
Date now = new Date();
xmp.put("xmp:ModifyDate", new XmpValue(now));
```

## ステップ 3: "Creator" の値を変更する
`"Creator"` キーは EPS ファイルを生成したアプリケーションまたは人物の名前を保持します。`xmp.put("dc:creator", "Your Company Name")` を呼び出して、既存の値をカスタム識別子に置き換えます。

```java
// Change "creator" value
XmpValue value = new XmpValue("Aspose.Page");
xmp.put("dc:creator", value);
```

## ステップ 4: "Title" の値を変更する
`"Title"` フィールドは多くのアセット管理システムで表示されます。`xmp.put("dc:title", "New Document Title")` で設定すると、カタログや検索結果にドキュメントが正しく表示されます。

```java
// Change "title" value
value = new XmpValue("(PAGEJAVA-29.eps)");
xmp.put("dc:title", value);
```

## ステップ 5: 変更された XMP メタデータでドキュメントを保存する
すべての変更が完了したら、`document.save("output.eps")` を呼び出します。ライブラリは更新された XMP ブロックを EPS ストリームに書き戻し、元のグラフィックコンテンツは変更せずに保持します。

```java
// Initialize output EPS file stream
FileOutputStream outPsStream = new FileOutputStream(dataDir + "xmp1_changed.eps");
// Save document with changed XMP metadata
try {
    document.save(outPsStream);
} finally {
    outPsStream.close();
}
```

## 一般的な問題と解決策
- **XMP ブロックが欠落している** – API は PS コメントから自動的に作成しますが、必要に応じて `XmpMetadata` を手動でインスタンス化することも可能です。  
- **タイムゾーンの不一致** – 予期しないオフセットを防ぐため、`Date` オブジェクトを作成する前に必ず `TimeZone.setDefault` を設定してください。  
- **ファイルアクセスエラー** – 入出力パスが正しいこと、そしてアプリケーションに読み書き権限があることを確認してください。

## よくある質問

**Q: XMP の値を変更する際にタイムゾーンの考慮はどうすればよいですか？**  
A: `TimeZone.setDefault(TimeZone.getTimeZone("UTC"))` を利用して、タイムゾーン設定の一貫性を確保します。

**Q: 1 回の操作で複数の XMP 値を変更できますか？**  
A: はい、目的の各値に対して `put` メソッドを使用すれば、複数の XMP 値を同時に変更できます。

**Q: Aspose.Page for Java の追加ドキュメントはどこで見つけられますか？**  
A: 包括的なドキュメントは [here](https://reference.aspose.com/page/java/) で確認してください。

**Q: Aspose.Page for Java の無料トライアルはありますか？**  
A: はい、無料トライアルは [here](https://releases.aspose.com/) から利用できます。

**Q: Aspose.Page for Java の一時ライセンスはどこで取得できますか？**  
A: 一時ライセンスは [here](https://purchase.aspose.com/temporary-license/) で取得してください。

**Q: XMP を変更すると EPS のビジュアルコンテンツに影響しますか？**  
A: いいえ。XMP の変更はメタデータのみで、EPS ファイルのグラフィック要素は変更されません。

**Q: プログラムで更新された値を再取得して変更を検証できますか？**  
A: もちろんです。保存後かつドキュメントを閉じる前に `xmp.get("dc:creator")`（または該当するキー）を呼び出すだけです。

## 結論
おめでとうございます！Aspose.Page for Java を使用して EPS ドキュメントの **how to modify xmp** 値をマスターしました。正確な creator、title、modify‑date メタデータを埋め込むことで、資産が検索可能でコンプライアンスを満たし、ブランド基準に合わせられます。このパターンをバッチ処理パイプライン、CI/CD ステップ、または任意の自動ドキュメント生成ワークフローに自由に組み込んでください。

---

**最終更新日:** 2026-05-25  
**テスト環境:** Aspose.Page for Java (latest release)  
**作者:** Aspose

## 関連チュートリアル

- [Aspose Page Java チュートリアル – EPS ファイルに XMP メタデータを追加する](/page/java/xmp-metadata-manipulation/add-metadata/)
- [Java を使用して XMP メタデータを読み取る方法 – Aspose.Page ガイド](/page/java/xmp-metadata-manipulation/get-metadata/)
- [aspose.page xmp java - Java で XMP の配列項目を変更する](/page/java/xmp-metadata-manipulation/change-array-items/)


{{< /blocks/products/pf/tutorial-page-section >}}

{{< /blocks/products/pf/main-container >}}

{{< blocks/products/products-backtop-button >}}

{{< /blocks/products/pf/main-wrap-class >}}