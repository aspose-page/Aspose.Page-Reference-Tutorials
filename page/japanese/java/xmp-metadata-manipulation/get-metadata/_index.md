---
date: 2026-05-25
description: Java と Aspose.Page を使用して XMP を読み取る方法を学びます。このステップバイステップ ガイドでは、XMP metadata、作成者情報、タイムスタンプ、サムネイルなどの抽出方法を示します。
keywords:
- read xmp using aspose.page
- xmp metadata java
- aspose.page java
linktitle: Java を使用した XMP metadata の読み取り方法
schemas:
- author: Aspose
  dateModified: '2026-05-25'
  description: Learn how to read xmp using aspose.page with Java. This step‑by‑step
    guide shows extracting XMP metadata, creator info, timestamps, thumbnails, and
    more.
  headline: Read XMP using Aspose.Page – Java Guide
  type: TechArticle
- questions:
  - answer: Yes, Aspose.Page can read XMP from PDF, EPS, and several image formats.
    question: Does this approach work with PDF files that contain XMP?
  - answer: Absolutely. The `XmpMetadata` object is mutable; you can add, update,
      or remove keys and then save the document.
    question: Can I modify XMP metadata after reading it?
  - answer: You can retrieve the binary data from the `xmpGImg:data` property of each
      thumbnail entry and write it to a file.
    question: Is there a way to extract all thumbnail images, not just dimensions?
  type: FAQPage
second_title: Aspose.Page Java API
title: Aspose.Page を使用した XMP の読み取り – Java ガイド
url: /ja/java/xmp-metadata-manipulation/get-metadata/
weight: 18
---

{{< blocks/products/pf/main-wrap-class >}}
{{< blocks/products/pf/main-container >}}
{{< blocks/products/pf/tutorial-page-section >}}

# Java を使用して XMP からメタデータを取得する

## Aspose.Page (Java) を使用して XMP を読み取る方法

EPS ファイルは `new Document("file.eps")` でロードします — `Document` クラスはロードされたファイルを表します。`getXmpMetadata()` を呼び出すと XMP パケットが抽出され、返された `XmpMetadata` オブジェクト（XMP プロパティ用のマップのようなインターフェイス）をクエリして必要なキーを取得します。これが Aspose.Page を使用して XMP を読み取るために必要なすべてです。API は低レベルのパースを抽象化するため、たった 2 行のコードで使用可能なプロパティマップが得られます。

ステップバイステップのチュートリアルへようこそ。このチュートリアルでは Java と Aspose.Page ライブラリを使用して **XMP を読み取る** 方法を示します。XMP（Extensible Metadata Platform）は、ドキュメント内にリッチなメタデータを埋め込むために広く採用されている標準です。このガイドの最後までに、ドキュメント形式の XMP を読み取り、作成者情報、タイムスタンプ、サムネイルなどを取得できるようになり、よりスマートなドキュメント分析ソリューションを構築できるようになります。

## クイック回答
- **“read XMP” とは何ですか？** ファイル内にメタデータを格納する XMP パケットをプログラムで抽出することを意味します。  
- **どのライブラリが必要ですか？** Aspose.Page for Java（公式ページから[here](https://releases.aspose.com/page/java/)でダウンロード）。  
- **ライセンスは必要ですか？** 本番環境では一時的またはフルライセンスが必要です。評価には無料トライアルが使用できます。  
- **サポートされている Java バージョンは何ですか？** Java 8 以上。  
- **他の形式から XMP を読み取れますか？** はい — Aspose.Page は EPS、PDF、JPEG、PNG など 20 以上の形式から XMP を抽出します。

## 前提条件
コードに入る前に、以下が揃っていることを確認してください：

- **Java Development Kit (JDK)** – Java 8+ がインストールされ、マシンで設定されていること。  
- **Aspose.Page for Java** – 公式サイトからライブラリをダウンロードしてください [here](https://releases.aspose.com/page/java/)。  
- XMP メタデータを含む EPS ファイル（例：`xmp1.eps`）。

## パッケージのインポート
`XmpMetadata` クラスは `com.aspose.page.xmp` 名前空間にあり、`Document` クラスは `com.aspose.page` にあります。両方をインポートして EPS ファイルとそのメタデータを操作できるようにします。  
```java
import java.io.FileInputStream;
import com.aspose.eps.PsDocument;
import com.aspose.eps.xmp.XmpMetadata;
import com.aspose.eps.xmp.XmpValue;
import com.aspose.page.BaseExamplesTest;
import com.aspose.page.License;
```

## ステップ 1: 入力 EPS ファイルストリームの初期化
まず、ドキュメントディレクトリへのパスを設定し、入力 EPS ファイルストリームを初期化します。  
```java
String dataDir = "Your Document Directory";
FileInputStream psStream = new FileInputStream(dataDir + "xmp1.eps");
PsDocument document = new PsDocument(psStream);
```

## ステップ 2: XMP メタデータの取得
`XmpMetadata` は、ドキュメントから抽出された XMP パケットを保持する Aspose.Page のオブジェクトです。`document.getXmpMetadata()` で取得します。ファイルに XMP がない場合、API は既存の PostScript コメントから最小限のパケットを合成します。  
```java
XmpMetadata xmp = document.getXmpMetadata();
```

## ステップ 3: CreatorTool 情報の抽出
`CreatorTool` キーは `xmp` 名前空間にあり、ファイルを生成したアプリケーションを記録します。その存在を確認し、値を出力します。  
```java
if (xmp.containsKey("xmp:CreatorTool"))
    System.out.println("CreatorTool: " + xmp.get("xmp:CreatorTool").toStringValue());
```

## ステップ 4: CreateDate 情報の抽出
`CreateDate` はドキュメントが最初に作成されたタイムスタンプを保持します。同じ `containsKey`/`get` パターンで読み取ります。  
```java
if (xmp.containsKey("xmp:CreateDate"))
    System.out.println("CreateDate: " + xmp.get("xmp:CreateDate").toStringValue());
```

## ステップ 5: サムネイル幅の取得
サムネイルが存在する場合、`xmp:Thumbnails` 配列に 1 つ以上のエントリが格納されます。各エントリは `width`、`height`、バイナリデータを含みます。例では最初のサムネイルの幅を抽出しています。  
```java
if (xmp.containsKey("xmp:Thumbnails") && xmp.get("xmp:Thumbnails").isArray()) {
    XmpValue val = xmp.get("xmp:Thumbnails").toArray()[0];
    if (val.isNamedValues() && val.toNamedValues().containsKey("xmpGImg:width"))
        System.out.println("Thumbnail Width: " + val.toNamedValues().get("xmpGImg:width").toInteger());
}
```

## ステップ 6: フォーマット情報の抽出
`format` キーは元のファイル形式（例: “application/postscript”）を示します。ソースタイプのログ記録や検証が必要なときに便利です。  
```java
if (xmp.containsKey("dc:format"))
    System.out.println("Format: " + xmp.get("dc:format").toStringValue());
```

## ステップ 7: DocumentID の取得
`DocumentID` は作成アプリケーションが割り当てる一意の識別子です。大規模なアセットライブラリで重複排除に使用できます。  
```java
if (xmp.containsKey("xmpMM:DocumentID"))
    System.out.println("DocumentID: " + xmp.get("xmpMM:DocumentID").toStringValue());
```

## なぜこれが重要か
Aspose.Page は **20 以上** のファイル形式から XMP を読み取ることができ、**500 MB** までのドキュメントをメモリに全体をロードせずに処理します。これにより、重要なメタデータへの高速かつ低オーバーヘッドなアクセスが可能になります。この機能は、バッチ処理パイプライン、デジタルアセット管理システム、検索可能で機械可読なドキュメント属性に依存するあらゆるソリューションにとって重要です。

## 一般的な落とし穴とヒント
- **XMP が欠如している場合:** 一部の EPS ファイルには XMP が含まれていないことがあります。`getXmpMetadata()` 呼び出しは既存の PS コメントに基づいて最小限のセットを合成しますが、埋め込まれていない限り完全なメタデータは取得できません。  
- **サムネイル配列:** `xmp:Thumbnails` キーは複数のエントリを保持できます。例では最初のエントリだけを抽出しています。すべてのサムネイルが必要な場合は配列を反復処理してください。  
- **名前空間の認識:** XMP キーは名前空間（例: `xmp:`、`dc:`）を使用します。正確なキー名を参照してください。そうしないと `containsKey` は false を返します。  

## よくある質問
### 他のプログラミング言語でも Aspose.Page for Java を使用できますか？
はい、Aspose.Page は Java、.NET、その他いくつかの言語をサポートしています。完全なリストは[ドキュメント](https://reference.aspose.com/page/java/)をご覧ください。

### Aspose.Page for Java の無料トライアルは利用可能ですか？
はい、無料トライアルは[here](https://releases.aspose.com/)からアクセスできます。

### Aspose.Page for Java のサポートはどこで見つけられますか？
コミュニティの支援と公式サポートは[Aspose.Page フォーラム](https://forum.aspose.com/c/page/39)をご覧ください。

### Aspose.Page for Java の一時ライセンスはどう取得しますか？
一時ライセンスは[here](https://purchase.aspose.com/temporary-license/)から取得できます。

### Aspose.Page for Java の追加リソースはありますか？
完全な[ドキュメント](https://reference.aspose.com/page/java/)を確認し、ライブラリは[here](https://releases.aspose.com/page/java/)からダウンロードしてください。

## 追加 FAQ
**Q: このアプローチは XMP を含む PDF ファイルでも機能しますか？**  
A: はい、Aspose.Page は PDF、EPS、いくつかの画像形式から XMP を読み取れます。

**Q: 読み取った後に XMP メタデータを変更できますか？**  
A: もちろんです。`XmpMetadata` オブジェクトは可変で、キーの追加、更新、削除が可能で、ドキュメントを保存できます。

**Q: サイズだけでなく、すべてのサムネイル画像を抽出する方法はありますか？**  
A: `xmpGImg:data` プロパティから各サムネイルエントリのバイナリデータを取得し、ファイルに書き出すことができます。

## 結論
これで Java と Aspose.Page を使用した **XMP の読み取り** メタデータの方法を習得しました。これらの手順に従うことで、作成ツール、タイムスタンプ、サムネイル、フォーマット情報、DocumentID を抽出でき、EPS ファイルに埋め込まれたメタデータを完全に把握できます。さらに、追加の XMP 名前空間を試して、アプリケーション向けによりリッチなデータを取得してください。

---

**最終更新日:** 2026-05-25  
**テスト環境:** Aspose.Page for Java 24.12 (latest)  
**作者:** Aspose

## 関連チュートリアル

- [Aspose Page Java チュートリアル – EPS ファイルに XMP メタデータを追加](/page/java/xmp-metadata-manipulation/add-metadata/)
- [aspose.page XMP チュートリアル – Java で XMP に名前空間を追加](/page/java/xmp-metadata-manipulation/add-namespace/)
- [aspose page XMP チュートリアル – Java で XMP の名前付き値を変更](/page/java/xmp-metadata-manipulation/change-named-value/)

{{< /blocks/products/pf/tutorial-page-section >}}
{{< /blocks/products/pf/main-container >}}
{{< blocks/products/products-backtop-button >}}
{{< /blocks/products/pf/main-wrap-class >}}