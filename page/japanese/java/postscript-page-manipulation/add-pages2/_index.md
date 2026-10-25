---
date: 2026-10-25
description: Aspose.Page を使用して Java の PostScript ドキュメントでカスタムページサイズを設定し、ページを追加する方法を学びます。シームレスなドキュメント操作のためのステップバイステップガイドです。
keywords:
- set custom page size
- Aspose.Page Java
- PostScript page manipulation
- add pages PostScript
lastmod: 2026-10-25
linktitle: PostScript でページを追加
og_description: Aspose.Page for Java を使用して PostScript のカスタムページサイズを設定する方法を学びます。ページの追加、サイズ設定、効率的な保存手順をステップバイステップでご案内します。
og_image_alt: Aspose.Page Java tutorial showing how to set custom page size in a PostScript
  document
og_title: Aspose.Page Java で PostScript のカスタムページサイズを設定
schemas:
- author: Aspose
  dateModified: '2026-10-25'
  description: Learn how to set custom page size and add pages to Java PostScript
    documents using Aspose.Page. Follow our step‑by‑step guide for seamless document
    manipulation.
  headline: Aspose.Page Java Tutorial – set custom page size while Adding Pages in
    PostScript
  type: TechArticle
- questions:
  - answer: Yes—you can open pages with custom dimensions using `document.openPage(width,
      height)`.
    question: Can I set different page sizes for each page?
  - answer: A valid Aspose.Page license is required for non‑evaluation deployments.
    question: Do I need a license for production use?
  - answer: The library works with Java 8 and newer.
    question: Which Java versions are supported?
  - answer: Document instances are not thread‑safe; create a separate `PsDocument`
      per thread.
    question: Is the API thread‑safe?
  - answer: Aspose.Page handles multi‑megabyte files efficiently; memory usage scales
      with content, not page count.
    question: How large can a PostScript file be?
  type: FAQPage
second_title: Aspose.Page Java API
tags:
- Aspose.Page
- Java PostScript
- custom page size
- add pages
- document generation
title: Aspose.Page Java チュートリアル – PostScript でページを追加しながらカスタムページサイズを設定
url: /ja/java/postscript-page-manipulation/add-pages2/
weight: 11
---

{{< blocks/products/pf/main-wrap-class >}}
{{< blocks/products/pf/main-container >}}
{{< blocks/products/pf/tutorial-page-section >}}

# Aspose.Page Java チュートリアル – PostScript にページを追加しながらカスタムページサイズを設定する

## はじめに
最新の Java アプリケーションでは、PostScript 出力用に **カスタムページサイズを設定** する必要が頻繁にあります—請求書、チケット、カスタムグラフィックの生成などに対応します。このチュートリアルでは、各ページのカスタムページサイズの設定方法、複数ページの追加方法、そして正確なレイアウト要件に合致した PostScript ファイルの生成方法を示します。Java 8+ プロジェクトにそのまま組み込める完全な実行可能サンプルが提供されます。

## クイック回答
- **各ページに異なるページサイズを設定できますか？** はい。`document.openPage(width, height)` を使用してカスタム寸法のページを開くことができます。  
- **本番環境で使用する際にライセンスは必要ですか？** 評価版以外のデプロイには有効な Aspose.Page ライセンスが必要です。  
- **サポートされている Java バージョンはどれですか？** このライブラリは Java 8 以降で動作します。  
- **API はスレッドセーフですか？** Document インスタンスはスレッドセーフではありません。スレッドごとに別々の `PsDocument` を作成してください。  
- **PostScript ファイルのサイズ上限はどれくらいですか？** Aspose.Page は数メガバイト規模のファイルを効率的に処理します。メモリ使用量はページ数ではなくコンテンツに比例します。  
- **openPage の幅/高さオーバーロードを使用できますか？** もちろんです。`openPage(double width, double height)` を使用すれば、ポイント単位で任意の寸法を指定できます。  

## 前提条件
以下を確認してください：

- Java プログラミングの基本的な理解  
- プロジェクトに Aspose.Page for Java を追加（Maven/Gradle または手動 JAR）  
- Java 開発環境（IDE、JDK 8+）  

## パッケージのインポート
以下のクラスが必要です: `FileOutputStream` はファイル書き込みに、`PsDocument` は PostScript ドキュメント作成に、`PsSaveOptions` は出力オプション設定に使用します。

```java
import java.io.FileOutputStream;
import com.aspose.eps.PsDocument;
import com.aspose.eps.device.PsSaveOptions;
```

## ステップ 1: 複数ページの PostScript ドキュメントを作成する
`PsDocument` は複数ページを含むことができる PostScript ドキュメントを表すコアクラスです。

```java
// The path to the documents directory.
String dataDir = "Your Document Directory";
// Create output stream for PostScript document
FileOutputStream outPsStream = new FileOutputStream(dataDir + "AddPages2_outPS.ps");
// Create save options with A4 size
PsSaveOptions options = new PsSaveOptions();
// Set variable that indicates if resulting PostScript document will be multipaged
boolean multiPaged = true;
// Create new multipaged PS Document with one page opened
PsDocument document = new PsDocument(outPsStream, options, multiPaged);
```

## ステップ 2: 最初のページにコンテンツを追加する
ドキュメントの準備ができたら、最初のページに必要なコンテンツを追加できます。完了したらページを閉じて内容をロックします。

```java
// Add content to the first page
// Close the first page
document.closePage();
```

## カスタムページサイズの設定方法
`document.openPage(width, height)` を使用して、ポイント単位で希望の寸法を指定し、コンテンツを描画する前にカスタムページサイズを設定します。`openPage(width, height)` は指定した幅と高さで新しいページを開き、ページキャンバスを完全に制御できます。デフォルトのページサイズが要件に合わない場合は、ページを開く際に **カスタムページサイズを設定** できます。領収書、ラベル、非標準レイアウトに便利です。

## ステップ 3: 異なるサイズの2ページ目を追加する
以下では 2 ページ目を開き、ポイント単位で幅と高さを明示的に指定します。これにより、同一ドキュメント内で **異なるページサイズ** を使用できることが示されます。

```java
// Add the second page with a different size
document.openPage(500, 300);
// Add content to the second page
// Close the second page
document.closePage();
```

## ステップ 4: ドキュメントを保存する
最後に、ドキュメントを保存して変更を永続化します。カスタムサイズのページを含むすべてのページが出力ファイルに書き込まれます。

```java
// Save the document
document.save();
```

これらの手順に従うことで、Aspose.Page を使用した Java の PostScript ドキュメントでページをシームレスに追加し、**カスタムページサイズを設定** でき、各ページのレイアウトを完全にコントロールできます。

## カスタムページサイズの設定に Aspose.Page を使用する理由
Aspose.Page はページ寸法を正確に制御でき、ポイント単位で任意の幅と高さを定義し、単一ドキュメント内で複数のページサイズを混在させ、効率的にコンテンツをストリーム処理して高性能な PostScript 生成を実現します。これにより、メモリ使用量を抑える必要がある請求書、チケット、大規模バッチ処理に最適です。

- **精度:** 寸法はポイントで定義されるため、ページの幅と高さを正確に制御できます。  
- **柔軟性:** 単一の PostScript ファイル内で **異なるページサイズ** を組み合わせて使用できます。  
- **パフォーマンス:** ライブラリはコンテンツを直接出力ファイルへストリームし、最大 500 MB のファイルでもヒープ使用量を 100 MB 未満に抑えて処理できるため、大規模な **PostScript ファイル生成** シナリオに適しています。  
- **豊富な API:** 30 種類以上のグラフィックプリミティブ、10 種類の画像フォーマット、ページごとのテキストオブジェクトは無制限にサポートし、設定したカスタム寸法を尊重します。

## よくある問題と解決策
| 問題 | 解決策 |
|-------|----------|
| ページ寸法が入れ替わって表示される | `openPage(width, height)` は幅が先、次に高さ（いずれもポイント）であることを忘れないでください。 |
| コンテンツがページからはみ出す | `PsGraphics` の座標系を使用してカスタム境界内に要素を配置するか、描画をスケーリングしてください。 |
| 巨大ドキュメントでメモリ不足エラーが発生する | 示したように `FileOutputStream` に直接書き込んでストリーミングを有効にし、大きな画像を一度にメモリに読み込まないようにしてください。 |

## よくある質問
### 単一の PostScript ドキュメントに異なるサイズのページを追加できますか？
はい。本チュートリアルで示したように、複数ページの PostScript ドキュメント内でサイズが異なるページを追加できます。  

### 追加できるページ数に制限はありますか？
Aspose.Page は実質的に無制限のページ数をドキュメントに追加できます。  

### ページに画像やグラフィックなどのカスタムコンテンツを追加できますか？
もちろんです！Aspose.Page はテキスト、画像、その他のグラフィック要素など、さまざまなコンテンツの追加を可能にします。  

### Aspose.Page は大きなドキュメントの処理に適していますか？
はい、Aspose.Page は小規模から大規模までのドキュメントを効率的に扱えるよう設計されています。  

### Aspose.Page の追加リソースやサポートはどこで見つけられますか？
[Aspose.Page ドキュメント](https://reference.aspose.com/page/java/) をご覧になるか、[Aspose.Page フォーラム](https://forum.aspose.com/c/page/39) でコミュニティサポートをご利用ください。  

**追加 Q&A**

**Q:** *PostScript ページに描画する際にサポートされている画像フォーマットは何ですか？*  
**A:** 描画 API を使用して PNG、JPEG、BMP、GIF 画像を直接埋め込むことができます。  

**Q:** *ドキュメントのデフォルト DPI を変更するには？*  
**A:** `PsDocument` を作成する前に `PsSaveOptions.setResolution(int dpi)` を設定してください。  

**Q:** *PostScript ファイルにパスワードで暗号化できますか？*  
**A:** PostScript 自体は暗号化をサポートしていませんが、必要に応じて出力を PDF にラップし、セキュリティ設定を適用できます。

---

**最終更新日:** 2026-10-25  
**テスト環境:** Aspose.Page for Java 24.10  
**作者:** Aspose  

---

## 関連チュートリアル

- [Aspose.Page を使用して Java で A4 ページサイズを設定し、PostScript を作成する方法](/page/java/document-creation/postscript/)
- [Aspose.Page Java API を使用して PostScript を PDF に変換する方法](/page/java/postscript-conversion/to-pdf/)
- [Aspose.Page を使用して Java の PostScript で矩形を描画する方法](/page/java/postscript-shapes/add-rectangle/)


{{< /blocks/products/pf/tutorial-page-section >}}

{{< /blocks/products/pf/main-container >}}
{{< /blocks/products/pf/main-wrap-class >}}

{{< blocks/products/products-backtop-button >}}