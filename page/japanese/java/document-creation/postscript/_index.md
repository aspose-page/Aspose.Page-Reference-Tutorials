---
date: 2026-06-20
description: Java で A4 ページサイズを設定し、PostScript ファイルを作成し、Aspose.Page を使用してカスタムフォントを追加する方法を学びましょう。無料トライアルを今すぐお試しください！
keywords:
- set a4 page size
- add custom fonts java
- java create postscript
linktitle: Java で PostScript を使用してドキュメントを作成する
schemas:
- author: Aspose
  dateModified: '2026-06-20'
  description: Learn how to set A4 page size, create PostScript files in Java, and
    add custom fonts using Aspose.Page. Try the free trial today!
  headline: How to set A4 page size and create PostScript in Java with Aspose.Page
  type: TechArticle
- description: Learn how to set A4 page size, create PostScript files in Java, and
    add custom fonts using Aspose.Page. Try the free trial today!
  name: How to set A4 page size and create PostScript in Java with Aspose.Page
  steps:
  - name: Set Document Directory
    text: The `OUTPUT_DIR` constant tells the library where to write the generated
      file.
  - name: Define Fonts Folder
    text: '`FONTS_FOLDER` points to the directory that holds your custom TrueType
      or OpenType fonts.'
  - name: Create Output Stream for PostScript Document
    text: '`FileOutputStream` opens a stream that will receive the final PostScript
      A4 output.'
  - name: Create Save Options with A4 Size
    text: '`PsSaveOptions` lets you specify the target page size. **Definition:**
      `PsPageSize` is an enumeration that contains standard page‑size constants such
      as A4, Letter, and Legal. Setting `options.setPageSize(PsPageSize.A4)` configures
      the document for standard A4 dimensions.'
  - name: Set Page Margins and Add Custom Fonts Folder
    text: '`options.setMargins(0, 0, 0, 0)` removes all margins for a full‑bleed page,
      and `options.setAdditionalFontsFolder(FONTS_FOLDER)` registers your custom fonts.'
  - name: Create a Multipaged or Single‑Paged PS Document
    text: '`PsDocument document = new PsDocument(outputStream, options)` creates the
      document. `PsDocument` represents a PostScript document that can contain one
      or many pages. Set `multiPaged` to `true` for multi‑page output.'
  - name: Close Current Page and Save Document
    text: Calling `document.close()` finalises the file and writes the **PostScript
      A4 size** output to disk.
  type: HowTo
- questions:
  - answer: Yes, set the additional fonts folder in the save options (see Step 5)
      and Aspose.Page will embed the fonts automatically.
    question: Can I use custom fonts in my PostScript document?
  - answer: Yes, you can get a free trial [here](https://releases.aspose.com/).
    question: Is there a trial version available for Aspose.Page for Java?
  - answer: Refer to the documentation [here](https://reference.aspose.com/page/java/).
    question: How can I access the full API reference?
  - answer: You can buy a license [here](https://purchase.aspose.com/buy).
    question: Where do I purchase a license for Aspose.Page for Java?
  - answer: Visit the Aspose.Page forum [forum](https://forum.aspose.com/c/page/39).
    question: Where can I ask the community for help?
  type: FAQPage
second_title: Aspose.Page Java API
title: Java と Aspose.Page を使用して A4 ページサイズを設定し、PostScript を作成する方法
url: /ja/java/document-creation/postscript/
weight: 10
---

{{< blocks/products/pf/main-wrap-class >}}
{{< blocks/products/pf/main-container >}}
{{< blocks/products/pf/tutorial-page-section >}}

# Java と Aspose.Page で A4 ページサイズを設定し、PostScript を作成する方法

## はじめに
Java から PostScript ファイルを生成する際に **A4 ページサイズを設定** する必要がある場合、Aspose.Page は低レベルの詳細を隠蔽した高速で信頼性の高い API を提供します。このチュートリアルでは、PostScript ドキュメントの作成、A4 ページ寸法の設定、必要に応じた **カスタムフォントの追加** の全工程を解説します。最後まで読むと、任意の Java プロジェクトに組み込めるすぐに使えるコードスニペットが手に入ります。

## 簡単な回答
- **Java で PostScript を作成するライブラリは何ですか？** Aspose.Page for Java.  
- **このガイドの対象ページサイズはどれですか？** A4 (210 mm × 297 mm).  
- **独自のフォントを埋め込むことはできますか？** はい – 保存オプションで追加フォントフォルダーを設定します。  
- **本番環境でライセンスは必要ですか？** 商用ライセンスが必要です。無料トライアルも利用可能です。  
- **サポートされている Java バージョンはどれですか？** Java 8 以降。

## Java で A4 ページサイズを設定し、PostScript を作成する方法
Aspose.Page ライブラリをロードし、`PsSaveOptions` に A4 定数を設定してドキュメントをファイルに書き出します – すべて 10 行未満のコードで実現できます。この直接的なアプローチにより、正しいページ寸法が保証され、余分な設定なしでカスタムフォントを追加できます。

## PostScript の A4 サイズとは？
PostScript の A4 サイズは、ISO 216 標準 (210 mm × 297 mm) を PostScript ページ記述言語で表したものです。プリンターやビューアが解釈する印刷可能領域を定義し、プラットフォーム間で一貫したレイアウトを保証します。PostScript がデバイスに依存しない方式でページ内容を記述するため、A4 サイズを使用すれば、世界中の A4 対応プリンターやビューアで同じように文書が表示されます。

## PostScript ページサイズを設定するために Aspose.Page を使用する理由
Aspose.Page は **30 以上の PostScript 演算子** をサポートし、ドキュメント全体をメモリに読み込むことなく **500 MB** までのファイルを生成できます。これにより、大規模なワークロードを効率的に処理しながら、ページ寸法を正確に制御できます。また、ライブラリは複雑な PostScript 構文を抽象化し、リソースを自動的に管理し、高性能ストリーミングを提供するため、シンプルな 1 ページのチラシから複雑なマルチページレポートまで幅広く適しています。

## Java でカスタムフォントを追加する方法
独自のフォントを埋め込むことで、生成された文書が任意のプリンターやビューアで設計通りに表示されます。Aspose.Page は指定フォルダーに配置されたフォントを自動的に検出します。追加フォントフォルダーを登録すれば、TrueType や OpenType フォントを自由に使用でき、フォールバック置換を回避し、すべての出力デバイスでブランドの一貫性を保てます。

## 前提条件
- Java プログラミングの実務知識。  
- Aspose.Page for Java がインストールされていること。ダウンロードは [here](https://releases.aspose.com/page/java/) から。  
- カスタムフォントを埋め込みたい場合は、`necessary_fonts`（任意の名前でも可）というフォルダーを作成し、そこにフォントを配置します。

## パッケージのインポート
Java プロジェクトで、必要な Aspose.Page クラスをインポートします：

```java
import java.io.FileOutputStream;
import com.aspose.eps.PageConstants;
import com.aspose.eps.PsDocument;
import com.aspose.eps.device.PsSaveOptions;
```

それでは、例を明確な番号付きステップに分解しましょう。

### ステップ 1: ドキュメントディレクトリの設定
`OUTPUT_DIR` 定数は、生成されたファイルを書き込む場所をライブラリに指示します。

```java
import java.io.FileOutputStream;
import com.aspose.eps.PageConstants;
import com.aspose.eps.PsDocument;
import com.aspose.eps.device.PsSaveOptions;
```

### ステップ 2: フォントフォルダーの定義
`FONTS_FOLDER` は、カスタム TrueType または OpenType フォントが格納されたディレクトリを指します。

```java
// The path to the documents directory.
String dataDir = "Your Document Directory";
```

### ステップ 3: PostScript ドキュメント用の出力ストリームを作成
`FileOutputStream` は、最終的な PostScript A4 出力を受け取るストリームを開きます。

```java
String FONTS_FOLDER = dataDir + "necessary_fonts/";
```

### ステップ 4: A4 サイズで保存オプションを作成
`PsSaveOptions` で対象ページサイズを指定できます。  
**定義:** `PsPageSize` は A4、Letter、Legal などの標準ページサイズ定数を含む列挙型です。  
`options.setPageSize(PsPageSize.A4)` を設定すると、文書は標準的な A4 寸法に構成されます。

```java
// Create output stream for PostScript document
FileOutputStream outPsStream = new FileOutputStream(dataDir + "CreateDocument_outPS.ps");
```

### ステップ 5: ページ余白を設定し、カスタムフォントフォルダーを追加
`options.setMargins(0, 0, 0, 0)` は、フルブリードページのためにすべての余白を削除し、`options.setAdditionalFontsFolder(FONTS_FOLDER)` はカスタムフォントを登録します。

```java
// Create save options with A4 size
PsSaveOptions options = new PsSaveOptions();
options.setPageSize(PageConstants.getSize(PageConstants.SIZE_A4, PageConstants.ORIENTATION_PORTRAIT));
```

### ステップ 6: マルチページまたはシングルページの PS ドキュメントを作成
`PsDocument document = new PsDocument(outputStream, options)` でドキュメントを作成します。`PsDocument` は 1 ページまたは複数ページを含むことができる PostScript ドキュメントを表します。マルチページ出力の場合は `multiPaged` を `true` に設定します。

```java
options.setMargins(PageConstants.getMargins(PageConstants.MARGINS_ZERO));
options.setAdditionalFontsFolders(new String[] { FONTS_FOLDER });
```

### ステップ 7: 現在のページを閉じてドキュメントを保存
`document.close()` を呼び出すと、ファイルが確定し、**PostScript A4 サイズ** の出力がディスクに書き込まれます。

```java
boolean multiPaged = false;
PsDocument document = new PsDocument(outPsStream, options, multiPaged);
```

## 一般的な問題とヒント
- **フォントが表示されない場合**? フォントファイルがサポートされている TrueType または OpenType 形式であること、そして `FONTS_FOLDER` がスラッシュ (`/`) で終わっていることを確認してください。  
- **余白がまだ表示される場合**? `PsDocument` を構築する **前に** `options.setMargins(...)` を呼び出してください。  
- **マルチページ出力が空白になる場合**? 必要な追加ページごとに `document.newPage()` を呼び出すことを忘れないでください。

## よくある質問

**Q: PostScript ドキュメントでカスタムフォントを使用できますか？**  
A: はい、保存オプションで追加フォントフォルダーを設定すれば（ステップ 5 参照）、Aspose.Page が自動的にフォントを埋め込みます。

**Q: Aspose.Page for Java のトライアル版はありますか？**  
A: はい、無料トライアルは [here](https://releases.aspose.com/) から取得できます。

**Q: 完全な API リファレンスはどこで確認できますか？**  
A: ドキュメントは [here](https://reference.aspose.com/page/java/) を参照してください。

**Q: Aspose.Page for Java のライセンスはどこで購入できますか？**  
A: ライセンスは [here](https://purchase.aspose.com/buy) から購入できます。

**Q: コミュニティに質問したい場合はどこですか？**  
A: Aspose.Page フォーラムは [forum](https://forum.aspose.com/c/page/39) をご覧ください。

**Q: マルチページの PostScript ファイルを生成できますか？**  
A: もちろんです。ステップ 6 で `multiPaged` を `true` に設定し、追加ページごとに `document.newPage()` を呼び出してください。

## 結論
これらの手順に従うことで、Java と Aspose.Page を使用して **A4 ページサイズを設定** し、**PostScript** ファイルを作成する方法、さらに **Java でカスタムフォントを追加** してページサイズオプションを制御できるようになりました。Aspose.Page が重い処理を担当するため、文書の内容に集中できます。

---

**最終更新日:** 2026-06-20  
**テスト環境:** Aspose.Page for Java 24.11  
**作者:** Aspose  

{{< blocks/products/products-backtop-button >}}

## 関連チュートリアル

- [Aspose.Page Java チュートリアル – PostScript でページを追加しながらカスタムページサイズを設定](/page/java/postscript-page-manipulation/add-pages2/)
- [Aspose.Page for Java を使用した PostScript へのテキスト追加方法](/page/java/postscript-text-manipulation/)
- [Aspose Page Java チュートリアル - PostScript を PDF に変換](/page/java/postscript-conversion/to-pdf/)


{{< /blocks/products/pf/tutorial-page-section >}}
{{< /blocks/products/pf/main-container >}}
{{< /blocks/products/pf/main-wrap-class >}}

```java
document.closePage();
document.save();
```