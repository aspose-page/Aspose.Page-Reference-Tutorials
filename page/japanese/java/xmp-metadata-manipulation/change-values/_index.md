---
date: 2025-12-21
description: Java を使用して EPS ドキュメントの XMP を変更する方法を学びましょう。Aspose.Page for Java でメタデータをすばやく強化できます。
linktitle: Change Values in XMP using Java
second_title: Aspose.Page Java API
title: aspose.pageでXMPを変更 – Javaを使用してXMPの値を変更
url: /ja/java/xmp-metadata-manipulation/change-values/
weight: 17
---

{{< blocks/products/pf/main-wrap-class >}}
{{< blocks/products/pf/main-container >}}
{{< blocks/products/pf/tutorial-page-section >}}

# Java を使用して XMP の値を変更する

## はじめに
EPS ファイル内の **aspose.page modify xmp** データを変更する必要がある場合、ここが適切な場所です。このチュートリアルでは、Aspose.Page ライブラリ for Java を使用して XMP (Extensible Metadata Platform) の値を読み取り、更新し、保存するために必要な正確な手順を順に説明します。最後まで読むと、作成者、タイトル、変更日などのドキュメントメタデータをプロジェクトの要件に合わせて調整できるようになります。

## クイックアンサー
- **「aspose.page modify xmp」は何をするものですか？** Aspose.Page Java API を介して EPS ファイルの XMP メタデータを読み書きできます。  
- **必要なライブラリのバージョンは？** 最近の Aspose.Page for Java のリリースであればどれでも構いません（API はバージョン間で安定しています）。  
- **サンプル実行にライセンスは必要ですか？** 評価用の無料トライアルで動作しますが、本番環境では商用ライセンスが必要です。  
- **複数の XMP フィールドを同時に変更できますか？** はい。ドキュメントを保存する前に各フィールドに対して `put` を呼び出します。  
- **タイムゾーンの取り扱いは必要ですか？** デフォルトのタイムゾーン（例: UTC）を設定すると、日付の一貫性が保たれます。

## XMP とは何か、そしてなぜ変更する必要があるのか​​？
XMP (Extensible Metadata Platform) は、EPS、PDF、画像などのファイルにリッチなメタデータを直接埋め込むための標準化された方式です。XMP を更新することで、ドキュメントのインデックス付け、表示、検索方法を制御でき、ブランディング、コンプライアンス、ワークフロー自動化にとって重要です。

## Aspose.Page for Java を使用する理由
- **フル機能 API** – 外部ツールは不要で、すべてプロセス内で処理できます。  
- **クロスプラットフォーム** – Java が動作するあらゆる OS で利用可能です。  
- **ネイティブ依存なし** – 純粋な Java 実装のため、デプロイが簡単です。  
- **堅牢なサポート** – 既存の XMP ブロックを処理し、欠如している場合は PS コメントから新規作成します。

## 前提条件
1. **Java 開発環境** – JDK（8 以上）とお好みの IDE またはビルドツール。  
2. **Aspose.Page for Java ライブラリ** – Aspose.Page for Java ライブラリをダウンロードしてインストールします。必要なパッケージは [here](https://releases.aspose.com/page/java/) で入手できます。

## パッケージのインポート
まず、必要なパッケージを Java プロジェクトにインポートします。これらのパッケージは EPS ドキュメントとやり取りし、操作するために不可欠です。

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

## ステップ 1: XMP メタデータの取得
EPS ドキュメントから XMP メタデータを取得します。EPS ファイルに XMP メタデータが含まれていない場合、%%Creator、%%CreateDate、%%Title などの PS メタデータコメントから値を取得して新規に作成されます。

```java
// The path to the documents directory.
String dataDir = "Your Document Directory";
// Initialize input EPS file stream
FileInputStream psStream = new FileInputStream(dataDir + "xmp1.eps");
PsDocument document = new PsDocument(psStream);
// Get XMP metadata. If EPS file doesn't contain XMP metadata, a new one is created with values from PS metadata comments
XmpMetadata xmp = document.getXmpMetadata();
```

## 手順 2: 「ModifyDate」の値を変更する
XMP メタデータ内の "ModifyDate" の値を、目的の日付に変更します。

```java
// Change "ModifyDate" value
TimeZone.setDefault(TimeZone.getTimeZone("UTC"));
Date now = new Date();
xmp.put("xmp:ModifyDate", new XmpValue(now));
```

## 手順 3: 「Creator」の値を変更する
XMP メタデータ内の "Creator" の値を更新し、ドキュメントの作成者を指定します。

```java
// Change "creator" value
XmpValue value = new XmpValue("Aspose.Page");
xmp.put("dc:creator", value);
```

## 手順 4: 「Title」の値を変更する
XMP メタデータ内の "Title" の値を変更し、ドキュメントに適切なタイトルを設定します。

```java
// Change "title" value
value = new XmpValue("(PAGEJAVA-29.eps)");
xmp.put("dc:title", value);
```

## 手順 5: 変更した XMP メタデータを含むドキュメントを保存する
更新された XMP メタデータを含むドキュメントを新しい EPS ファイルとして保存します。

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

## よくある問題と解決策
- **XMP ブロックが欠如している** – API は PS コメントから自動的に作成しますが、必要に応じて `XmpMetadata` を手動でインスタンス化することも可能です。  
- **タイムゾーンの不一致** – `Date` オブジェクトを作成する前に必ず `TimeZone.setDefault` を設定し、予期しないオフセットを防ぎます。  
- **ファイルアクセスエラー** – 入出力パスが正しいこと、アプリケーションに読み書き権限があることを確認してください。

## よくある質問

**Q: XMP の値を変更する際にタイムゾーンの考慮はどうすればよいですか？**  
A: `TimeZone.setDefault(TimeZone.getTimeZone("UTC"))` を使用して、タイムゾーン設定の一貫性を保ちます。

**Q: 1 回の操作で複数の XMP 値を変更できますか？**  
A: はい。目的の各値に対して `put` メソッドを使用すれば、複数の XMP 値を同時に変更できます。

**Q: Aspose.Page for Java の追加ドキュメントはどこで見つけられますか？**  
A: 包括的なドキュメントは [here](https://reference.aspose.com/page/java/) で確認できます。

**Q: Aspose.Page for Java の無料トライアルはありますか？**  
A: はい、無料トライアルは [here](https://releases.aspose.com/) から利用できます。

**Q: Aspose.Page for Java の一時ライセンスはどこで取得できますか？**  
A: 一時ライセンスは [here](https://purchase.aspose.com/temporary-license/) で取得できます。

**Q: XMP を変更すると EPS のビジュアルコンテンツに影響しますか？**  
A: いいえ。XMP の変更はメタデータのみであり、EPS ファイルのグラフィック要素は変更されません。

**Q: プログラム上で更新された値を読み戻して変更を確認できますか？**  
A: もちろんです。保存後かつドキュメントを閉じる前に `xmp.get("dc:creator")`（または該当キー）を呼び出すだけです。

## 結論
おめでとうございます！Aspose.Page for Java を使用して EPS ドキュメントの **aspose.page modify xmp** 値を正常に変更できました。このチュートリアルにより、メタデータを変更する方法を習得し、ドキュメントが特定の要件にシームレスに合致するようにできるようになりました。

**Last Updated:** 2025-12-21  
**Tested With:** Aspose.Page for Java (latest release)  
**Author:** Aspose

{{< /blocks/products/pf/tutorial-page-section >}}

{{< /blocks/products/pf/main-container >}}
{{< /blocks/products/pf/main-wrap-class >}}

{{< blocks/products/products-backtop-button >}}
