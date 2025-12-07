---
date: 2025-12-07
description: 強力なグラフィックと印刷用ライブラリである Aspose.Page を使用して、Java で画像を EPS として保存する方法を学びましょう。
language: ja
linktitle: Save Image as EPS in Java
second_title: Aspose.Page Java API
title: Aspose.Page を使用した Java で画像を EPS として保存
url: /java/postscript-conversion/save-image-as-eps/
weight: 12
---

{{< blocks/products/pf/main-wrap-class >}}
{{< blocks/products/pf/main-container >}}
{{< blocks/products/pf/tutorial-page-section >}}

# Java で Aspose.Page を使用して画像を EPS として保存する方法

## Introduction
Java プログラミングの世界では、**Aspose.Page** for Java が画像をさまざまな形式で操作・保存するための強力なツールとして登場します。その中でも特に有用なのが、画像を Encapsulated PostScript (EPS) ファイルとして保存できる機能です。EPS はプロフェッショナルなグラフィックや高解像度印刷ワークフローで広く採用されているフォーマットです。  
このチュートリアルでは、JPEG（またはサポートされている任意のラスタ画像）を Aspose.Page を使って EPS ファイルに変換する手順を、コードの各行を丁寧に解説しながら学びます。

## Quick Answers
- **必要なライブラリは？** Aspose.Page for Java  
- **サポートされているソース形式は？** JPEG、PNG、BMP、GIF、TIFF など  
- **変換にかかる時間は？** 標準サイズの画像で通常 1 秒未満  
- **開発時にライセンスは必要？** 評価用に無料トライアルが利用可能。商用利用にはライセンスが必要です。  
- **EPS 出力をカスタマイズできる？** はい – `PsSaveOptions` で圧縮やカラーモードなどを設定可能です。

## What is Aspose.Page?
Aspose.Page は、開発者がネイティブのグラフィックライブラリに依存せずにベクターおよびラスタ画像を作成、編集、変換できる Java API です。PDF、EPS、SVG、そして多数のラスタ形式をサポートしており、サーバーサイドの文書処理や印刷パイプラインに最適です。

## Why Save Images as EPS?
- **Scalable Vector Output:** EPS はデバイスに依存しない形式で保存され、任意の解像度で品質が保たれます。  
- **Print‑Ready:** 多くのプロフェッショナルプリンターや出版ツールが EPS をネイティブに受け入れます。  
- **Cross‑Platform Compatibility:** EPS ファイルは Adobe Illustrator、CorelDRAW、そして多数のオープンソースエディタで開くことができます。

## Prerequisites
コードに取り掛かる前に、以下の環境を準備してください。

1. **Java Development Kit (JDK)** – マシンにインストールされた動作する JDK。最新バージョンは [here](https://www.oracle.com/java/technologies/javase-downloads.html) からダウンロードできます。  
2. **Aspose.Page for Java Library** – Aspose.Page の最新 JAR を [release page](https://releases.aspose.com/page/java/) から取得し、プロジェクトのクラスパスに追加します。

## Import Packages
Java ソースファイルに必要なインポート文を追加します。これらのステートメントは EPS 変換に必要なコアクラスを取り込みます。

```java
import com.aspose.eps.PsDocument;
import com.aspose.eps.device.PsSaveOptions;

// The path to the documents directory.
String dataDir = "Your Document Directory";
// Create default options
PsSaveOptions options = new PsSaveOptions();
```

これらの行はドキュメントディレクトリを設定し、画像を EPS として保存するためのデフォルトオプションを作成します。

それでは、プロセスを明確で管理しやすいステップに分解していきましょう。

## Step 1: Set Document Directory
```java
// The path to the documents directory.
String dataDir = "Your Document Directory";
```
`"Your Document Directory"` を、出力 EPS ファイルを書き込みたい絶対パスに置き換えてください。絶対パスを使用することで、アプリケーションが異なる作業ディレクトリから実行された場合でも曖昧さを回避できます。

## Step 2: Create Save Options
```java
// Create default options
PsSaveOptions options = new PsSaveOptions();
```
`PsSaveOptions` は EPS 出力を細かく調整できるクラスです。デフォルトコンストラクタは妥当なオプションセットを生成しますが、後から `Compression`、`ColorMode`、`Resolution` などのプロパティを変更してワークフローに合わせることが可能です。

## Step 3: Save Image as EPS
```java
// Save JPEG image to EPS file
PsDocument.saveImageAsEps(dataDir + "input1.jpg", dataDir + "output1.eps", options);
```
この 1 行が変換を実行します。

- `dataDir + "input1.jpg"` – ソース JPEG（またはサポートされている任意のラスタ画像）へのパス。  
- `dataDir + "output1.eps"` – 生成された EPS ファイルの希望パスとファイル名。  
- `options` – 出力特性を制御する `PsSaveOptions` インスタンス。

プログラムを実行すると、指定ディレクトリに `output1.eps` が作成され、任意の EPS 対応アプリケーションで使用できるようになります。

## Common Issues and Solutions
| Issue | Reason | Fix |
|-------|--------|-----|
| **FileNotFoundException** | Incorrect `dataDir` path or missing source image | Verify the directory string and ensure the image file exists. |
| **OutOfMemoryError** on large images | Loading very high‑resolution raster files can exceed JVM heap | Increase the JVM heap size (`-Xmx`) or downscale the source image before conversion. |
| **EPS file appears blank** | Using an unsupported image format | Convert the source to a supported format (e.g., JPEG, PNG) before calling `saveImageAsEps`. |

## Frequently Asked Questions
### Is Aspose.Page for Java compatible with all image formats?
Yes, Aspose.Page for Java supports a wide range of image formats, making it versatile for various applications.

### Can I customize the EPS save options?
Absolutely! The tutorial introduces default options, but you can modify them based on your specific needs.

### Where can I find additional support and discussions about Aspose.Page for Java?
Visit the [Aspose.Page forum](https://forum.aspose.com/c/page/39) to engage with the community and seek assistance.

### Is there a free trial available for Aspose.Page for Java?
Yes, you can explore a free trial [here](https://releases.aspose.com/).

### How can I obtain a temporary license for Aspose.Page for Java?
Acquire a temporary license [here](https://purchase.aspose.com/temporary-license/).

## Conclusion
Congratulations! You’ve successfully learned how to save an image as EPS in Java using **Aspose.Page**. This capability opens doors to advanced graphics and printing workflows, allowing you to generate high‑quality, print‑ready files directly from your Java applications.  

Feel free to explore more features of Aspose.Page for Java by referring to the official [documentation](https://reference.aspose.com/page/java/). When you’re ready, try experimenting with `PsSaveOptions` to control compression, color depth, and other EPS parameters.

---

**Last Updated:** 2025-12-07  
**Tested With:** Aspose.Page 24.12 for Java  
**Author:** Aspose  

{{< /blocks/products/pf/tutorial-page-section >}}

{{< /blocks/products/pf/main-container >}}
{{< /blocks/products/pf/main-wrap-class >}}

{{< blocks/products/products-backtop-button >}}