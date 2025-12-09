---
date: 2025-11-29
description: Aspose.Page Java を使用して、Java で XPS を PDF に保存する方法を学びましょう。効率的な XPS から PDF
  への変換と PDF 圧縮設定のためのステップバイステップガイドに従ってください。
linktitle: Convert XPS to PDF in Java using Aspose.Page Java
second_title: Aspose.Page Java API
title: Aspose.Page Java を使用して Java で XPS を PDF に変換する
url: /ja/java/file-merging/xps-to-pdf/
weight: 11
---

{{< blocks/products/pf/main-wrap-class >}}
{{< blocks/products/pf/main-container >}}
{{< blocks/products/pf/tutorial-page-section >}}

# JavaでAspose.Page Javaを使用してXPSをPDFに変換する

## Introduction
このチュートリアルでは、Java用の強力なドキュメント変換ライブラリである Aspose.Page Java を使用して、XPS を PDF に変換する方法を学びます。請求書のバッチ処理、印刷可能なレポートの生成、またはレガシー XPS ファイルの単純な移行が必要な場合でも、Aspose.Page Java は高速で信頼性が高く、完全に構成可能です。

## Quick Answers
- **どのライブラリが XPS から PDF への変換を処理しますか？** Aspose.Page Java  
- **基本的な変換にかかる時間はどれくらいですか？** 通常、単一ページの XPS ファイルで 1 秒未満です。  
- **開発にライセンスは必要ですか？** 無料トライアルで評価は可能ですが、本番環境ではライセンスが必要です。  
- **PDF の圧縮を制御できますか？** はい – `PdfSaveOptions` を使用して画像とテキストの圧縮を設定します。  
- **必要な Java バージョンは何ですか？** Java 8 以降 (JDK 11+ 推奨)。

## What is Aspose.Page Java?
Aspose.Page Java は、開発者が XPS ドキュメントをプログラムで作成、編集、変換できる **高性能 API** です。XPS を PDF、PNG、JPEG などの形式にレンダリングでき、**PDF 圧縮の設定** など出力設定を細かく制御できます。

## Why use Aspose.Page Java for XPS‑to‑PDF conversion?
- **ゼロ依存のレンダリング** – ネイティブライブラリや外部ツールが不要です。  
- **正確なレイアウト保持** – PDF 出力は元の XPS の外観を忠実に再現します。  
- **PDF 出力の完全な制御** – 画像品質の調整、圧縮アルゴリズムの選択、特定ページのレンダリングが可能です。  
- **クロスプラットフォーム** – 任意の標準 JDK で Windows、Linux、macOS 上で動作します。

## Prerequisites
開始する前に、以下を確認してください：

1. **Java Development Kit (JDK) 8+** – パフォーマンスとセキュリティのために最新の JDK を推奨します。  
2. **Aspose.Page for Java ライブラリ** – 公式の [Aspose.Page Java documentation](https://reference.aspose.com/page/java/) から JAR をダウンロードしてください。  
3. IDE (IntelliJ IDEA、Eclipse、VS Code) またはシンプルなテキストエディタとコマンドラインビルドツール (Maven/Gradle)。

## Import Packages
Java クラスに必要なインポートを追加して、XPS ドキュメントと PDF 出力を扱えるようにします。

```java
import com.aspose.xps.XpsDocument;
import com.aspose.xps.rendering.pdf.PdfDevice;
import com.aspose.xps.rendering.pdf.PdfSaveOptions;
import com.aspose.xps.rendering.pdf.PdfImageCompression;
import com.aspose.xps.rendering.pdf.PdfTextCompression;
import java.io.FileOutputStream;
```

## Step‑by‑Step Guide

### Step 1: Set Document Directory Path
ソース XPS ファイルが格納され、PDF が保存されるフォルダーを定義します。

```java
String dataDir = "C:/MyDocuments/XpsFiles/";   // <-- replace with your actual path
```

### Step 2: Initialize PDF Output Stream
`FileOutputStream` を作成し、出力先 PDF ファイルを指すようにします。

```java
FileOutputStream pdfStream = new FileOutputStream(dataDir + "XPStoPDF.pdf");
```

> **プロのコツ:** `try‑with‑resources` を使用してストリームを自動的に閉じ、リソースリークを防止します。

### Step 3: Load XPS Document
`XpsDocument` オブジェクトをインスタンス化し、ソース XPS ファイルをロードします。

```java
XpsDocument document = new XpsDocument(dataDir + "input.xps");
```

### Step 4: Initialize PDF Save Options (Set PDF Compression)
PDF の圧縮方法を設定します。この手順で画像やテキストの **PDF 圧縮** を設定でき、品質を犠牲にせずファイルサイズを削減できます。

```java
PdfSaveOptions options = new PdfSaveOptions();
options.setJpegQualityLevel(100);                         // maximum JPEG quality
options.setImageCompression(PdfImageCompression.Jpeg);   // compress images as JPEG
options.setTextCompression(PdfTextCompression.Flate);    // compress text streams
options.setPageNumbers(new int[] { 1, 2, 6 });            // optional: export only selected pages
```

> **なぜ重要か:** JPEG 品質と圧縮タイプを調整することで、10 MB の PDF を 2 MB 未満に縮小でき、必要な視覚的忠実度を保てます。

### Step 5: Create Rendering Device for PDF Format
`PdfDevice` はレンダリングされたページを PDF 出力ストリームに流します。

```java
PdfDevice device = new PdfDevice(pdfStream);
```

### Step 6: Save the Document
最後に、設定したオプションを使用して XPS コンテンツを PDF にレンダリングします。

```java
document.save(device, options);
```

> **結果:** 実行後、`XPStoPDF.pdf` が `dataDir` フォルダーに作成され、指定した圧縮設定が適用された変換ページが含まれます。

## Common Issues & Solutions
| 問題 | 原因 | 解決策 |
|------|------|--------|
| **`FileNotFoundException`** | `dataDir` パスが間違っている | ディレクトリが存在し、アプリケーションに読み書き権限があることを確認してください。 |
| **Blank PDF pages** | `PdfDevice` の初期化が欠如している | 出力に使用したのと同じ `FileOutputStream` で `PdfDevice` が作成されていることを確認してください。 |
| **Large PDF size** | デフォルトの圧縮が低い | `setJpegQualityLevel` を上げるか、低品質レベルの `PdfImageCompression.Jpeg` に切り替えてください。 |
| **Only some pages appear** | `setPageNumbers` フィルタがページを除外している | 必要なすべてのページ番号を含むよう配列を調整するか、すべてのページをエクスポートするために呼び出しを削除してください。 |

## Frequently Asked Questions

**Q: Aspose.Page Java はさまざまな Java バージョンに対応していますか？**  
A: はい、Aspose.Page Java は Java 8 から Java 21 まで、Oracle と OpenJDK の両方のディストリビューションをサポートしています。

**Q: 変換された PDF の圧縮設定をカスタマイズできますか？**  
A: もちろんです。Step 4 の例のように `PdfSaveOptions` を使用して JPEG 品質、画像圧縮タイプ、テキスト圧縮を設定できます。

**Q: 追加のサポートやコミュニティの議論はどこで見つけられますか？**  
A: コミュニティの支援、コードサンプル、トラブルシューティングのヒントは [Aspose.Page Forum](https://forum.aspose.com/c/page/39) をご覧ください。

**Q: Aspose.Page の無料トライアルはありますか？**  
A: はい、[Aspose ダウンロードページ](https://releases.aspose.com/) から完全機能のトライアルをダウンロードできます。

**Q: Aspose.Page の一時ライセンスはどのように取得できますか？**  
A: 一時ライセンスは [こちら](https://purchase.aspose.com/temporary-license/) からリクエストできます。

## Conclusion
**Aspose.Page Java** を活用すれば、XPS を PDF として簡単に保存でき、ページ選択から圧縮まで出力のあらゆる側面を制御できます。このチュートリアルでは、Java アプリケーションに XPS‑to‑PDF 変換を組み込むために必要なすべてをカバーしました。ユーティリティとしての単体使用でも、大規模なドキュメント処理パイプラインでも活用できます。

---

**Last Updated:** 2025-11-29  
**Tested With:** Aspose.Page for Java 24.10  
**Author:** Aspose  

{{< /blocks/products/pf/tutorial-page-section >}}

{{< /blocks/products/pf/main-container >}}
{{< /blocks/products/pf/main-wrap-class >}}

{{< blocks/products/products-backtop-button >}}