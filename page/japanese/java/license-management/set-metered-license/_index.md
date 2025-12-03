---
date: 2025-12-03
description: Aspose.Page for Java を使用して EPS を PNG に保存する方法を、メーター制ライセンスの設定とともに学びます。ステップバイステップのガイドと完全なコード例付き。
language: ja
linktitle: Set Metered License in Java
second_title: Aspose.Page Java API
title: Aspose.Page JavaでEPSをPNGとして保存（メータードライセンス）
url: /java/license-management/set-metered-license/
weight: 10
---

{{< blocks/products/pf/main-wrap-class >}}
{{< blocks/products/pf/main-container >}}
{{< blocks/products/pf/tutorial-page-section >}}

# Aspose.Page Java（Metered License）で EPS を PNG に保存する

## Introduction
Java アプリケーションで **EPS を PNG に保存** したい場合、ライセンス管理が簡単な方法を探しているならここが最適です。このチュートリアルでは、Aspose.Page の従量課金ライセンスを設定し、PostScript（EPS）ファイルを読み込み、PNG 画像に変換する手順を、すぐに実行できるシンプルなステップで解説します。

## Quick Answers
- **「EPS を PNG に保存する」とは何ですか？** ベクタ形式の EPS ファイルをラスタ画像の PNG に変換します。  
- **なぜ従量課金ライセンスを使用するのですか？** 処理したページ数に応じて支払うだけなので、変動するワークロードに最適です。  
- **インターネット接続は必要ですか？** いいえ、従量課金キーはローカルで検証されます。  
- **必要な Java バージョンは？** Java 8 以上。  
- **セットアップにどれくらい時間がかかりますか？** 基本的な実装で約 10 分です。

## What is “save EPS as PNG”?
EPS を PNG に保存することは、拡張可能な Encapsulated PostScript ドキュメントを、広くサポートされているビットマップ形式に変換することです。PNG は透過性を保持し、ロスレス圧縮を提供するため、ウェブグラフィック、サムネイル、印刷プレビューに最適です。

## Why use Aspose.Page for this task?
- **Pure Java API** – ネイティブ依存がありません。  
- **High fidelity** – ベクタ画像が正確にレンダリングされます。  
- **Metered licensing** – 変換した分だけ支払います。  
- **Support for multiple output formats** – PNG、JPEG、TIFF などに対応。

## Prerequisites
開始する前に、以下を確認してください。

- Java プログラミングの基本的な知識。  
- Aspose.Page ライブラリがインストール済み – [こちら](https://releases.aspose.com/page/java/) からダウンロード。  
- Aspose アカウントで取得できる従量課金用の公開キーとプライベートキー。

## Import Packages
まず、必要なクラスをインポートします。コードが変更なくコンパイルできるよう、インポートブロックは以下の通りそのまま保持してください。

```java
import java.io.FileInputStream;
import java.io.FileOutputStream;
import java.io.IOException;
import com.aspose.eps.ImageFormat;
import com.aspose.eps.PsDocument;
import com.aspose.eps.device.ImageSaveOptions;
```

## Step 1: Initialize Document and Image Format
ここでは従量課金キーを設定し、出力フォーマット（PNG）を定義します。これが **EPS を PNG に保存** する操作の基盤となります。

```java
// set metered public and private keys
com.aspose.page.Metered metered = new com.aspose.page.Metered();
// Access the setMeteredKey property and pass public and private keys as parameters
metered.setMeteredKey(
    "<type public key here>",
    "<type private key here>");
// The path to the documents directory.
String dataDir = "Your Document Directory";
ImageFormat imageFormat = ImageFormat.PNG;
```

## Step 2: Initialize PostScript Input Stream
変換したい EPS ファイルを開きます。ストリームはドキュメントを Aspose.Page に渡す役割を果たします。

```java
// Initialize PostScript input stream
FileInputStream psStream = new FileInputStream(dataDir + "input.ps");
PsDocument document = new PsDocument(psStream);
```

## Step 3: Check Document License
処理を開始する前に、従量課金ライセンスが正しく適用されているか必ず確認してください。

```java
// Check if the document is licensed
if (document.isLicensed())
    System.out.println("Metered License is set successfully.");
else
    System.out.println("Metered License is not set.");
```

## Step 4: Initialize Options and Image Device
変換設定を制御するオプションオブジェクトと、レンダリングされた画像を受け取るデバイスを作成します。

```java
// Initialize options object with default parameters.
ImageSaveOptions options = new ImageSaveOptions();
// Initialize ImageDevice object with default parameters.
com.aspose.eps.device.ImageDevice device = new com.aspose.eps.device.ImageDevice();
```

## Step 5: Save EPS File as Image
これがコアとなる **EPS を PNG に保存** の呼び出しです。ドキュメントは設定したオプションを使用して画像デバイスにレンダリングされます。

```java
// Save EPS file as image
try {
    document.save(device, options);
} finally {
    psStream.close();
}
```

## Step 6: Get and Save Image Bytes
デバイスから PNG バイト列を取得し、ディスク上のファイルに書き込みます。

```java
// Get images bytes. One bytes array for one page. In our case, we have one page.
byte[][] imagesBytes = device.getImagesBytes();
// Save image bytes to file
FileOutputStream fs = new FileOutputStream(dataDir + "eps_out." + imageFormat.toString().toLowerCase());
try {
    fs.write(imagesBytes[0], 0, imagesBytes[0].length);
} catch (IOException ex) {
    System.out.println(ex.getMessage());
} finally {
    fs.close();
}
```

## Common Issues and Solutions
| Issue | Why it Happens | Fix |
|-------|----------------|-----|
| **License not recognized** | Keys are incorrect or placed in the wrong order. | Double‑check the public/private key strings and ensure `setMeteredKey` is called before any document processing. |
| **Output file is empty** | `device.getImagesBytes()` returned `null`. | Verify that the EPS file is valid and that the `ImageSaveOptions` are not set to a zero‑size canvas. |
| **OutOfMemoryError on large EPS** | Rendering large vector files consumes a lot of memory. | Process pages one‑at‑a‑time or increase JVM heap (`-Xmx2g`). |

## Frequently Asked Questions

**Q: How do I obtain metered public and private keys?**  
A: You can obtain these keys through your Aspose account.

**Q: Is the Aspose.Page library free?**  
A: Aspose.Page offers both free trial and paid versions. Visit [here](https://releases.aspose.com/) for a free trial.

**Q: Can I use Aspose.Page for commercial projects?**  
A: Yes, Aspose.Page offers commercial licenses. You can purchase them [here](https://purchase.aspose.com/buy).

**Q: Where can I find additional documentation?**  
A: Refer to the documentation [here](https://reference.aspose.com/page/java/).

**Q: How can I get temporary licenses?**  
A: Temporary licenses can be obtained [here](https://purchase.aspose.com/temporary-license/).

{{< /blocks/products/pf/tutorial-page-section >}}

{{< /blocks/products/pf/main-container >}}
{{< /blocks/products/pf/main-wrap-class >}}

{{< blocks/products/products-backtop-button >}}

---

**最終更新日:** 2025-12-03  
**テスト環境:** Aspose.Page 24.12 for Java  
**作成者:** Aspose  

---