---
date: 2026-01-20
description: Aspose.Page for .NET を使用して、XPS ドキュメントを高品質な PDF に結合しながら、ページ番号を簡単に追加できます。XPS
  を PDF に変換するステップバイステップのガイドに従ってください。
linktitle: Merge XPS Documents into PDF
second_title: Aspose.Page .NET API
title: PDFにページ番号を追加 – Aspose.Pageを使用してXPSをPDFに結合
url: /ja/net/document-merging/merge-xps-documents-into-pdf/
weight: 11
---

{{< blocks/products/pf/main-wrap-class >}}
{{< blocks/products/pf/main-container >}}
{{< blocks/products/pf/tutorial-page-section >}}

# PDFにページ番号を追加 – Aspose.Page を使用して XPS を PDF に結合

## Introduction

XPS ファイルを結合しながら **PDF にページ番号を追加** する必要がある場合、Aspose.Page for .NET が手間なく処理を行います。このチュートリアルでは、XPS ドキュメントを高品質 PDF に変換し、画像圧縮を制御し、最終 PDF に自動的にページ番号を挿入する完全な本番対応サンプルを順を追って解説します。最後まで読むと、任意の C# プロジェクトに組み込める再利用可能なコードスニペットが手に入ります。

## Quick Answers
- **Can I add page numbers when merging XPS to PDF?** Yes – the `PdfSaveOptions.PageNumbers` property does exactly that.  
- **Which library handles the conversion?** Aspose.Page for .NET.  
- **Do I need a license for production use?** A valid Aspose.Page license is required; a temporary license is available for testing.  
- **What .NET versions are supported?** .NET Framework 4.5+, .NET Core 3.1+, and .NET 5/6+.  
- **Is high‑quality image output possible?** Absolutely – set `JpegQualityLevel` to 100 and choose `PdfImageCompression.Jpeg`.

## Prerequisites

チュートリアルに入る前に、以下の前提条件が整っていることをご確認ください。

- Aspose.Page for .NET: Aspose.Page ライブラリがインストールされていることを確認してください。ダウンロードは [here](https://releases.aspose.com/page/net/) から行えます。

- Document Files: 指定ディレクトリに XPS ドキュメント（`input.xps`）が用意されていること。

## Import Namespaces

.NET プロジェクトで Aspose.Page を使用するために、必要な名前空間をインクルードします。

```csharp
using Aspose.Page.XPS;
```

この手順により、ドキュメント変換に必要なクラスやメソッドへアクセスできるようになります。

## How to add page numbers PDF when merging XPS documents

`PdfSaveOptions.PageNumbers` コレクションを使用すると、出力 PDF に含めるページ（またはページ範囲）を正確に指定できます。希望するページ番号を設定するだけで、Aspose.Page が自動的に正しい番号付けを行います。

### Step 1: Initialize Streams

```csharp
// ExStart:3
// The path to the documents directory.
string dataDir = "Your Document Directory";
// Initialize PDF output stream
using (System.IO.Stream pdfStream = System.IO.File.Open(dataDir + "XPStoPDF_out.pdf", System.IO.FileMode.OpenOrCreate, System.IO.FileAccess.Write))
// Initialize XPS input stream
using (System.IO.Stream xpsStream = System.IO.File.Open(dataDir + "input.xps", System.IO.FileMode.Open))
{
    // ...
}
// ExEnd:3
```

このステップでは、XPS と PDF の入力・出力ストリームを設定します。正しいパスとファイル名が使用されていることを確認してください。

### Step 2: Load XPS Document

```csharp
// ExStart:4
// Load XPS document form the stream
XpsDocument document = new XpsDocument(xpsStream, new XpsLoadOptions());
// or load XPS document directly from file. No xpsStream is needed then.
// XpsDocument document = new XpsDocument(inputFileName, new XpsLoadOptions());
// ExEnd:4
```

ここで XPS ドキュメントを `XpsDocument` オブジェクトに読み込み、以降の処理に備えます。

### Step 3: Initialize Save Options (merge xps to pdf)

```csharp
// ExStart:5
// Initialize options object with necessary parameters.
PdfSaveOptions options = new PdfSaveOptions()
{
    JpegQualityLevel = 100,
    ImageCompression = PdfImageCompression.Jpeg,
    TextCompression = PdfTextCompression.Flate,
    PageNumbers = new int[] { 1, 2, 6 }   // <-- adds page numbers PDF
};
// ExEnd:5
```

`PdfSaveOptions` オブジェクトを好みに合わせてカスタマイズします。画像圧縮、テキスト圧縮、そして最終 PDF に表示させたい **ページ番号** などのパラメータを指定します。`JpegQualityLevel` を 100 に設定すると **高品質 PDF 画像** が得られます。

### Step 4: Create Rendering Device

```csharp
// ExStart:6
// Create rendering device for PDF format
PdfDevice device = new PdfDevice(pdfStream);
// ExEnd:6
```

`PdfDevice` は XPS ドキュメントを PDF 形式にレンダリングするためのツールです。

### Step 5: Save the Document (c# xps to pdf)

```csharp
// ExStart:7
document.Save(device, options);
// ExEnd:7
```

最後に、レンダリングデバイスと指定したオプションでドキュメントを保存します。出力 PDF には選択したページが自動的にページ番号付きで含まれます。

## Why use Aspose.Page for this conversion?

- **Reliability** – Handles complex XPS features without loss of fidelity.  
- **Performance** – Stream‑based processing avoids loading entire files into memory.  
- **Flexibility** – Fine‑grained control over image quality, compression, and page numbering.  
- **Cross‑platform** – Works on Windows, Linux, and macOS with .NET Core.

## Common Issues and Solutions

| Issue | Solution |
|-------|----------|
| **Output PDF is blank** | Verify that the XPS file path is correct and that the file is not corrupted. |
| **Page numbers not appearing** | Ensure `PageNumbers` is set to the correct zero‑based page indices (e.g., `new int[] {1,2,6}`). |
| **Low‑quality images** | Increase `JpegQualityLevel` and choose `PdfImageCompression.Jpeg`. |
| **Large XPS files cause memory pressure** | Process the XPS in smaller chunks or increase the application’s memory limit. |

## Frequently Asked Questions

### Q1: Can I merge multiple XPS files into a single PDF?

A1: Yes, you can. Simply adjust the `PageNumbers` parameter in the `PdfSaveOptions` to include the desired pages from different XPS files, or load each XPS sequentially and call `document.Save` on the same `PdfDevice`.

### Q2: Is a temporary license available for Aspose.Page for .NET?

A2: Yes, you can obtain a temporary license [here](https://purchase.aspose.com/temporary-license/) for testing purposes.

### Q3: Are there any limitations on file size when using Aspose.Page for document conversion?

A3: Aspose.Page for .NET does not impose strict limitations on file size, but optimal performance is achieved with reasonably sized files. For very large XPS documents, consider processing them in streams to reduce memory consumption.

### Q4: Can I customize the output PDF further, such as adding watermarks or annotations?

A4: Yes, Aspose.Page for .NET provides extensive features for PDF manipulation. After conversion, you can use the Aspose.PDF library to add watermarks, annotations, or other enhancements.

### Q5: Does Aspose.Page for .NET support cross‑platform development?

A5: Yes, Aspose.Page for .NET is designed to work seamlessly across various platforms, including Windows, Linux, and macOS, when used with .NET Core or .NET 5/6.

---

**Last Updated:** 2026-01-20  
**Tested With:** Aspose.Page 24.11 for .NET  
**Author:** Aspose  

{{< /blocks/products/pf/tutorial-page-section >}}

{{< /blocks/products/pf/main-container >}}
{{< /blocks/products/pf/main-wrap-class >}}

{{< blocks/products/products-backtop-button >}}