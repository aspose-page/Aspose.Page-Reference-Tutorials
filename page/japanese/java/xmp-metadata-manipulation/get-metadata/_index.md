---
date: 2025-12-21
description: Aspose.Page を使用して Java で XMP メタデータの読み取り方法を学びましょう。このステップバイステップガイドでは、ドキュメント形式の
  XMP を読み取り、主要なプロパティを抽出する方法を示します。
linktitle: How to Read XMP Metadata using Java
second_title: Aspose.Page Java API
title: JavaでXMPメタデータを読む方法 – Aspose.Pageガイド
url: /ja/java/xmp-metadata-manipulation/get-metadata/
weight: 18
---

{{< blocks/products/pf/main-wrap-class >}}
{{< blocks/products/pf/main-container >}}
{{< blocks/products/pf/tutorial-page-section >}}

# Java を使用した XMP メタデータの取得

## Java を使用した XMP メタデータの読み取り方法

Java と Aspose.Page ライブラリを使用して **XMP を読み取る** 方法をステップバイステップで紹介するチュートリアルへようこそ。XMP（Extensible Metadata Platform）は、ドキュメント内にリッチなメタデータを埋め込むために広く採用されている標準です。このガイドを終える頃には、ドキュメント形式の XMP を読み取り、作成者情報、タイムスタンプ、サムネイルなどを取得できるようになり、よりスマートなドキュメント分析ソリューションを構築できるようになります。

## クイック回答
- **“how to read xmp” とは何ですか？** ファイルからプログラムで XMP メタデータを抽出することを指します。  
- **必要なライブラリはどれですか？** Aspose.Page for Java（Aspose のダウンロードページから入手可能）。  
- **ライセンスは必要ですか？** 本番環境で使用するには一時ライセンスまたはフルライセンスが必要です。無料トライアルも利用可能です。  
- **サポートされている Java バージョンは？** Java 8 以上。  
- **他の形式から XMP を読み取れますか？** はい、Aspose.Page は EPS、PDF、そして XMP を埋め込んだ複数の画像形式に対応しています。

## 前提条件
コードに入る前に、以下が揃っていることを確認してください：

- **Java Development Kit (JDK)** – マシンに Java 8 以上がインストールされ、設定されていること。  
- **Aspose.Page for Java** – 公式サイトからライブラリをダウンロードしてください [here](https://releases.aspose.com/page/java/)。  
- XMP メタデータを含む EPS ファイル（例: `xmp1.eps`）。

## パッケージのインポート
Java プロジェクトで必要なパッケージをインポートします：

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
EPS ファイルから XMP メタデータを取得します。ファイルに XMP メタデータが無い場合は、PS メタデータコメントから値を取得して新しいメタデータが生成されます。

```java
XmpMetadata xmp = document.getXmpMetadata();
```

## ステップ 3: CreatorTool 情報の抽出
XMP メタデータから "CreatorTool" の値を確認し、出力します。

```java
if (xmp.containsKey("xmp:CreatorTool"))
    System.out.println("CreatorTool: " + xmp.get("xmp:CreatorTool").toStringValue());
```

## ステップ 4: CreateDate 情報の抽出
XMP メタデータから "CreateDate" の値を確認し、出力します。

```java
if (xmp.containsKey("xmp:CreateDate"))
    System.out.println("CreateDate: " + xmp.get("xmp:CreateDate").toStringValue());
```

## ステップ 5: サムネイル幅の取得
サムネイルが存在する場合、最初のサムネイルの幅を抽出して出力します。

```java
if (xmp.containsKey("xmp:Thumbnails") && xmp.get("xmp:Thumbnails").isArray()) {
    XmpValue val = xmp.get("xmp:Thumbnails").toArray()[0];
    if (val.isNamedValues() && val.toNamedValues().containsKey("xmpGImg:width"))
        System.out.println("Thumbnail Width: " + val.toNamedValues().get("xmpGImg:width").toInteger());
}
```

## ステップ 6: フォーマット情報の抽出
XMP メタデータから "format" の値を確認し、出力します。

```java
if (xmp.containsKey("dc:format"))
    System.out.println("Format: " + xmp.get("dc:format").toStringValue());
```

## ステップ 7: DocumentID の取得
XMP メタデータから "DocumentID" の値を確認し、出力します。

```java
if (xmp.containsKey("xmpMM:DocumentID"))
    System.out.println("DocumentID: " + xmp.get("xmpMM:DocumentID").toStringValue());
```

## なぜ重要か
XMP メタデータを読み取ることで、ビューアで開かずにドキュメントの出所、作成日、その他重要な属性をプログラムから取得できます。これは、バッチ処理やコンテンツ管理システム、メタデータがインデックスや検索を駆動するデジタル資産パイプラインで特に有用です。

## よくある落とし穴とヒント
- **XMP が欠如している場合:** 一部の EPS ファイルには XMP が含まれていないことがあります。`getXmpMetadata()` 呼び出しは既存の PS コメントに基づいて最小限のセットを合成しますが、埋め込まれていない限り完全なメタデータは取得できません。  
- **サムネイル配列:** `xmp:Thumbnails` キーは複数のエントリを保持できます。例では最初のものだけを抽出しています。すべてのサムネイルが必要な場合は配列を反復処理してください。  
- **名前空間の認識:** XMP キーは名前空間（例: `xmp:`, `dc:`）を使用します。正確なキー名を参照してください。そうしないと `containsKey` は false を返します。

## よくある質問
### Aspose.Page for Java を他のプログラミング言語と併用できますか？
はい、Aspose.Page は Java、.NET など複数の言語をサポートしています。詳細は [documentation](https://reference.aspose.com/page/java/) をご確認ください。

### Aspose.Page for Java の無料トライアルは利用できますか？
はい、無料トライアルは [here](https://releases.aspose.com/) から利用できます。

### Aspose.Page for Java のサポートはどこで得られますか？
コミュニティサポートは [Aspose.Page forum](https://forum.aspose.com/c/page/39) をご覧ください。

### Aspose.Page for Java の一時ライセンスはどう取得しますか？
一時ライセンスは [here](https://purchase.aspose.com/temporary-license/) から取得できます。

### Aspose.Page for Java の追加リソースはありますか？
完全な [documentation](https://reference.aspose.com/page/java/) を確認し、ライブラリは [here](https://releases.aspose.com/page/java/) からダウンロードしてください。

## 追加 FAQ
**Q: XMP を含む PDF ファイルでもこの方法は機能しますか？**  
A: はい、Aspose.Page は PDF、EPS、そしていくつかの画像形式から XMP を読み取ることができます。

**Q: 読み取った後に XMP メタデータを変更できますか？**  
A: もちろんです。`XmpMetadata` オブジェクトは可変で、キーの追加、更新、削除が可能で、ドキュメントを保存できます。

**Q: サムネイルのサイズだけでなく、すべてのサムネイル画像を抽出する方法はありますか？**  
A: 各サムネイルエントリの `xmpGImg:data` プロパティからバイナリデータを取得し、ファイルに書き出すことができます。

## 結論
これで **XMP を読み取る** 方法を Java と Aspose.Page を使って習得しました。これらの手順に従うことで、作成ツール、タイムスタンプ、サムネイル、フォーマット情報、Document ID を抽出でき、EPS ファイルに埋め込まれたメタデータを完全に把握できます。さらに XMP の名前空間を活用して、アプリケーション向けにより豊富なデータを取得することにも挑戦してみてください。

{{< /blocks/products/pf/tutorial-page-section >}}

{{< /blocks/products/pf/main-container >}}
{{< /blocks/products/pf/main-wrap-class >}}

{{< blocks/products/products-backtop-button >}}

---

**最終更新日:** 2025-12-21  
**テスト環境:** Aspose.Page for Java 24.12（最新）  
**作者:** Aspose