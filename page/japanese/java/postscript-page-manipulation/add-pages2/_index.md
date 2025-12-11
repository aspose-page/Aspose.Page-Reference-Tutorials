---
date: 2025-12-11
description: Aspose.Page を使用して、Java の PostScript ドキュメントでカスタムページサイズを設定し、ページを追加する方法を学びましょう。シームレスなドキュメント操作のためのステップバイステップガイドをご覧ください。
linktitle: Adding Pages in PostScript
second_title: Aspose.Page Java API
title: Aspose.Page Java チュートリアル – PostScriptでページを追加する際にカスタムページサイズを設定する
url: /ja/java/postscript-page-manipulation/add-pages2/
weight: 11
---

{{< blocks/products/pf/main-wrap-class >}}
{{< blocks/products/pf/main-container >}}
{{< blocks/products/pf/tutorial-page-section >}}

# Aspose.Page Java チュートリアル – PostScript にページを追加しながらカスタムページサイズを設定する方法

## はじめに
最新の Java アプリケーションでは、**カスタムページサイズの設定**が PostScript 出力で頻繁に求められます。請求書、チケット、カスタムグラフィックの生成などが典型的な例です。Aspose.Page for Java を使用すれば、この作業は非常にシンプルになります。本チュートリアルでは、PostScript ドキュメントにページを追加し、カスタムページサイズを設定する手順をステップバイステップで解説します。これにより、毎回正確なレイアウトを実現できます。

## クイック回答
- **ページごとに異なるサイズを設定できますか？** はい、`document.openPage(width, height)` を使用してカスタム寸法のページを開くことができます。  
- **本番環境での使用にライセンスは必要ですか？** 評価版以外でのデプロイには有効な Aspose.Page ライセンスが必要です。  
- **対応している Java バージョンは？** Java 8 以降で動作します。  
- **API はスレッドセーフですか？** `PsDocument` インスタンスはスレッドセーフではありません。スレッドごとに別々のインスタンスを作成してください。  
- **PostScript ファイルのサイズ上限は？** Aspose.Page はマルチメガバイトのファイルを効率的に処理します。メモリ使用量はページ数ではなくコンテンツ量に比例します。

## 前提条件
以下を事前に準備してください。

- Java プログラミングの基本的な知識。  
- プロジェクトに Aspose.Page for Java を追加（Maven/Gradle または手動で JAR を配置）。  
- Java 開発環境（IDE、JDK 8 以上）。

## パッケージのインポート
まず、Aspose.Page ライブラリから必要なクラスをインポートします。

```java
import java.io.FileOutputStream;
import com.aspose.eps.PsDocument;
import com.aspose.eps.device.PsSaveOptions;
```

## 手順 1: 複数ページの PostScript ドキュメントを作成する
新しい `PsDocument` を作成し、複数ページ用に設定します。これにより出力ストリームが初期化され、マルチページファイルとして扱うことをライブラリに指示します。

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

## 手順 2: 最初のページにコンテンツを追加する
ドキュメントの準備ができたら、最初のページに必要なコンテンツを追加します。作業が完了したら、ページを閉じて内容を確定させます。

```java
// Add content to the first page
// Close the first page
document.closePage();
```

## カスタムページサイズの設定方法
デフォルトのページサイズが要件に合わない場合は、新しいページを開く際に **カスタムページサイズ** を指定できます。領収書、ラベル、その他標準外のレイアウトに便利です。

## 手順 3: 異なるサイズの 2 ページ目を追加する
以下の例では、2 ページ目を開く際に幅と高さ（ポイント単位）を明示的に指定しています。これにより、個別ページごとにカスタムサイズを設定できることが分かります。

```java
// Add the second page with a different size
document.openPage(500, 300);
// Add content to the second page
// Close the second page
document.closePage();
```

## 手順 4: ドキュメントを保存する
最後に、変更内容を保存します。カスタムサイズのページを含むすべてのページが出力ファイルに書き込まれます。

```java
// Save the document
document.save();
```

これらの手順に従うことで、Aspose.Page を使用した Java の PostScript ドキュメントでページをシームレスに追加し、**カスタムページサイズを設定**できるようになります。各ページのレイアウトを完全にコントロールできます。

## 結論
Aspose.Page for Java は、PostScript ドキュメントを扱うための堅牢で開発者に優しい API を提供します。複数ページの追加、カスタム寸法の適用、そして保存までの一連の流れを習得したことで、あらゆる Java ベースのソリューションで正確にフォーマットされた出力を生成できるようになりました。

## よくある質問
### 1. 1 つの PostScript ドキュメントに異なるサイズのページを追加できますか？
はい。本チュートリアルで示したように、マルチページ PostScript ドキュメント内でサイズが異なるページを追加できます。  

### 2. 追加できるページ数に制限はありますか？
Aspose.Page は実質的に無制限のページ数をサポートしています。  

### 3. ページに画像やグラフィックなどのカスタムコンテンツを追加できますか？
もちろんです！テキスト、画像、その他のグラフィック要素を自由に追加できます。  

### 4. 大規模なドキュメントの取り扱いは可能ですか？
はい。Aspose.Page は小規模から大規模までのドキュメントを効率的に処理できるよう設計されています。  

### 5. Aspose.Page の追加リソースやサポートはどこで入手できますか？
[Aspose.Page ドキュメント](https://reference.aspose.com/page/java/) を参照するか、[Aspose.Page フォーラム](https://forum.aspose.com/c/page/39) でコミュニティサポートをご利用ください。  

**追加 Q&A**

**Q:** *PostScript ページに描画できる画像形式は何ですか？*  
**A:** PNG、JPEG、BMP、GIF の各形式を描画 API で直接埋め込むことができます。  

**Q:** *ドキュメントのデフォルト DPI を変更するには？*  
**A:** `PsDocument` を作成する前に `PsSaveOptions.setResolution(int dpi)` を設定してください。  

**Q:** *PostScript ファイルにパスワードで暗号化できますか？*  
**A:** PostScript 自体は暗号化をサポートしていませんが、出力を PDF にラップし、必要に応じてセキュリティ設定を適用することが可能です。

{{< /blocks/products/pf/tutorial-page-section >}}

{{< /blocks/products/pf/main-container >}}
{{< /blocks/products/pf/main-wrap-class >}}

{{< blocks/products/products-backtop-button >}}

---

**最終更新日:** 2025-12-11  
**テスト環境:** Aspose.Page for Java 24.10  
**作成者:** Aspose  

---