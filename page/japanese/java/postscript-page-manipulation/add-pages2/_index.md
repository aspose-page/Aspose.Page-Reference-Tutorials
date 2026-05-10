---
date: 2026-02-18
description: Aspose.Page を使用して、Java の PostScript ドキュメントでカスタムページサイズを設定し、ページを追加する方法を学びましょう。シームレスなドキュメント操作のためのステップバイステップガイドをご覧ください。
linktitle: Adding Pages in PostScript
second_title: Aspose.Page Java API
title: Aspose.Page Java チュートリアル – PostScript でページを追加する際にカスタムページサイズを設定する
url: /ja/java/postscript-page-manipulation/add-pages2/
weight: 11
---

{{< blocks/products/pf/main-wrap-class >}}
{{< blocks/products/pf/main-container >}}
{{< blocks/products/pf/tutorial-page-section >}}

# Aspose.Page Java チュートリアル – PostScript にページを追加しながらカスタムページサイズを設定する

## Introduction
最新の Java アプリケーションでは、PostScript 出力の **カスタムページサイズの設定** が頻繁に求められます—請求書、チケット、カスタムグラフィックの生成などです。このチュートリアルでは、各ページに **カスタムページサイズを設定** し、複数ページを追加し、最終的に **PostScript ファイルを生成** して正確なレイアウト要件を満たす方法を学びます。コードをステップバイステップで解説するので、すぐに自分のプロジェクトに適用できます。

## Quick Answers
- **各ページに異なるページサイズを設定できますか？** はい、`document.openPage(width, height)` を使用してカスタム寸法でページを開くことができます。  
- **本番環境で使用する際にライセンスは必要ですか？** 評価版以外のデプロイには有効な Aspose.Page ライセンスが必要です。  
- **サポートされている Java バージョンは？** ライブラリは Java 8 以降で動作します。  
- **API はスレッドセーフですか？** Document インスタンスはスレッドセーフではありません。スレッドごとに別々の `PsDocument` を作成してください。  
- **PostScript ファイルのサイズ上限は？** Aspose.Page はマルチメガバイトのファイルを効率的に処理します。メモリ使用量はページ数ではなくコンテンツに比例します。  
- **openPage の幅/高さオーバーロードは使用できますか？** もちろんです。`openPage(double width, double height)` を使えば、ポイント単位で任意の寸法を指定できます。  

## Prerequisites
始める前に、以下が揃っていることを確認してください：

- Java プログラミングの基本的な理解  
- プロジェクトに Aspose.Page for Java を追加（Maven/Gradle または手動 JAR）  
- Java 開発環境（IDE、JDK 8 以上）  

## Import Packages
まず、Aspose.Page ライブラリから必要なクラスをインポートします。

```java
import java.io.FileOutputStream;
import com.aspose.eps.PsDocument;
import com.aspose.eps.device.PsSaveOptions;
```

## Step 1: Create a Multipaged PostScript Document
まず、複数ページ用に設定された新しい `PsDocument` を作成します。これにより出力ストリームが設定され、ライブラリにマルチページファイルを扱うことを指示します。

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

## Step 2: Add Content to the First Page
ドキュメントの準備ができたら、最初のページに必要なコンテンツを追加できます。完了したら、ページを閉じて内容を確定します。

```java
// Add content to the first page
// Close the first page
document.closePage();
```

## How to set custom page size
デフォルトのページサイズが要件に合わない場合は、新しいページを開く際に **カスタムページサイズを設定** できます。領収書、ラベル、その他の非標準レイアウトに便利です。

## Step 3: Add a Second Page with Different Size
以下では、2 番目のページを開き、カスタム幅と高さ（ポイント単位）を明示的に指定します。これにより、個々のページにカスタムページサイズを設定する方法を示し、同一ドキュメント内で **異なるページサイズ** を扱えるようになります。

```java
// Add the second page with a different size
document.openPage(500, 300);
// Add content to the second page
// Close the second page
document.closePage();
```

## Step 4: Save the Document
最後に、ドキュメントを保存して変更を永続化します。カスタムサイズのページを含むすべてのページが出力ファイルに書き込まれます。

```java
// Save the document
document.save();
```

これらの手順に従うことで、Aspose.Page を使用した Java の PostScript ドキュメントでページをシームレスに追加し、 **カスタムページサイズを設定** でき、各ページのレイアウトを完全にコントロールできます。

## Why use Aspose.Page to set custom page size?
- **精度:** 寸法はポイントで定義されるため、ページの幅と高さを正確に制御できます。  
- **柔軟性:** 単一の PostScript ファイル内で **異なるページサイズ** を組み合わせて使用できます。  
- **パフォーマンス:** ライブラリはコンテンツを直接出力ファイルにストリーミングするため、大規模な **PostScript ファイル生成** シナリオに適しています。  
- **豊富な API:** グラフィック描画、画像埋め込み、テキスト追加をサポートし、設定したカスタム寸法を尊重します。  

## Common Issues and Solutions
| 問題 | 解決策 |
|-------|----------|
| **ページ寸法が逆になっている** | `openPage(width, height)` は幅が先、次に高さ（いずれもポイント）であることを忘れないでください。 |
| **コンテンツがページからはみ出す** | `PsGraphics` の座標系を使用して要素をカスタム境界内に配置するか、描画をスケーリングしてください。 |
| **大容量ドキュメントでのメモリ不足エラー** | 示したように `FileOutputStream` に直接書き込んでストリーミングを有効にし、大きな画像を一度にメモリに読み込むのを避けてください。 |

## Frequently Asked Questions
### Can I add pages of different sizes in a single PostScript document?
はい、このチュートリアルで示したように、マルチページの PostScript ドキュメント内でサイズが異なるページを追加できます。  

### Are there any limitations on the number of pages I can add?
Aspose.Page は実質的に無制限のページ数をドキュメントに追加できるようサポートしています。  

### Can I add custom content, such as images or graphics, to the pages?
もちろんです！Aspose.Page はテキスト、画像、その他のグラフィック要素など、幅広いコンテンツの追加を可能にします。  

### Is Aspose.Page suitable for handling large documents?
はい、Aspose.Page は小規模から大規模なドキュメントまで効率的に扱えるよう設計されています。  

### Where can I find additional resources and support for Aspose.Page?
追加のリソースやサポートは、[Aspose.Page ドキュメント](https://reference.aspose.com/page/java/) をご覧いただくか、[Aspose.Page フォーラム](https://forum.aspose.com/c/page/39) でコミュニティサポートをご利用ください。  

**Additional Q&A**

**Q:** *PostScript ページに描画する際にサポートされている画像形式は何ですか？*  
**A:** 描画 API を使用して PNG、JPEG、BMP、GIF 画像を直接埋め込むことができます。  

**Q:** *ドキュメントのデフォルト DPI を変更するには？*  
**A:** `PsDocument` を作成する前に `PsSaveOptions.setResolution(int dpi)` を設定してください。  

**Q:** *PostScript ファイルにパスワードで暗号化できますか？*  
**A:** PostScript 自体は暗号化をサポートしていませんが、必要に応じて出力を PDF にラップし、セキュリティ設定を適用することは可能です。  

---

**最終更新日:** 2026-02-18  
**テスト環境:** Aspose.Page for Java 24.10  
**作者:** Aspose  

---

{{< /blocks/products/pf/tutorial-page-section >}}

{{< /blocks/products/pf/main-container >}}
{{< /blocks/products/pf/main-wrap-class >}}

{{< blocks/products/products-backtop-button >}}